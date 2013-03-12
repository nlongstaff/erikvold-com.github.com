---
title: Greasemonkey Optimization: Convert2RegExp
short URL: http://r.evold.ca/gm-c2re
tags: Learning, Javascript, Troubleshooting, Daily UserScript, Greasemonkey, Programming, Productivity, Firefox
---
Over the last week I've been spending a great deal of time looking over the 
<a title="Greasemonkey - GitHub" rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/greasemonkey/greasemonkey">Greasemonkey</a> 
and 
<a title="Webmonkey - GitHub" rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/ocornu/webmonkey">Webmonkey</a> 
source code,
both because I want to understand both code bases more, but also because I'm interested in Firefox extension 
internals in general. While looking through these two code bases I saw a common file which could be optimized. 
This file was the <a title="convert2RegExp - Greasemonkey - GitHub" rel="external nofollow" target="_blank" href="http://github.com/greasemonkey/greasemonkey/blob/master/content/convert2RegExp.js"><em>convert2RegExp.js</em></a> file, which looks like it came from Adblock at some point, at least in part. 
In fact I saw a number of changes that I could try in order to speed up the function, so I decided to time them all.
</p>

<h2>Test Factors</h2>
<h3>Factor I: Check for /\.[^\.ld]*t[^\.td]*l[^\.lt]*d/ in pattern string character loop</h3>
<p>
<strong>The first thing I noticed was that the regular expression that checks the pattern string for a ".tld" string 
was being run on every pattern input, this seemed obviously bad to me since there was a loop prior 
to the regular expression which runs through the pattern string's characters, so why didn't that loop at least check 
for the ".tld" substring first?</strong> the check could be as simple as making sure all of the required letters 
exist in the string first, or make sure that the ".tld" substring, exactly, is in the pattern string, or 
what I found to be the best way was to make sure the regular expression /\.[^\.ld]*t[^\.td]*l[^\.lt]*d/ matched the 
pattern string via the character loop through the pattern string. <strong>The average cases and best cases 
will go much faster</strong> despite the fact that the latter case would be 
matching some pattern strings that following tld regular expression (that is already in convert2regexp) would not match, 
thus just adding work in this case, and making the worst possible case even slower.
</p>


<h3>Factor II: Cache tldStr and tldRegExp</h3>
<p>
The convert2RegExp( pattern ) function creates the tldRegExp and tldStr from literals on every execution! 
that might be a faster operation I thought, but I expected it to be slower than simply looking up the value of a variable when I timed it, and even though I 
haven't figured out how to test the memory consumption yet, I expect creating a large string from a string literal over and over again would increase 
the peak memory usage, and thus the garbage collector pause time as well. So, caching the tldStr and tldRegExp seemed like it would be a small win.
</p>


<h3>Factor III: Use array.push()/array.unshift() and array.join() instead of +=</h3>
<p>
From what I've read about Firefox 3.6 the += operator in loops is optimized to use a single StringBuffer, but there were a few += outside of the loop, 
and I figured some people will probably use versions of Firefox &lt; 3.5 for some time to come still, and using an array there would certainly improve/decrease 
the peak memory usage. I didn't know what the affect on performance would be, but this change is commonly said to be the better approach for JavaScript in the 
past to present, mainly because of the memory issue. Furthermore, the more memory that is used, the more work there is for the garbage collector to deal with, 
which means your computer is even slower, and that time is hard to measure. I do know that a new feature to Firefox 3.6 is that the garbage collector frees the memory in a new thread, 
which means that older versions of Firefox did not, and that means that the chances of pauses were even greater. For more reading on these changes I am mentioning 
in Firefox 3.6 please <a title="Firefox 3.6 Speedups" rel="external" rev="vote-for" target="_blank" href="http://hacks.mozilla.org/2010/01/javascript-speedups-in-firefox-3-6/">read this article</a>.
</p>


<h2>The Tests</h2>

<h3>Description</h3>

<p>In order to test the factors listed above I knew I needed a number of different versions of the convert2RegExp function, but the other piece I needed 
was a collection of pattern strings to test. I made the different versions of convert2RegExp easily, but when it came to making the pattern set(s) to test 
I had to do some more thinking.</p>

<h3>Test Pattern Sets</h3>
<p>
I may not have made the best choice, but I decided to use two pattern sets:
</p><ol>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/patterns.js">Pattern Set 0</a>: 3/50 patterns use the magic tld expression, 2/50 do not use the tld expression, but match /\.[^\.ld]*t[^\.td]*l[^\.lt]*d/</li>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/patterns1.js">Pattern Set 1</a>: 2/50 patterns use the magic tld expression</li>
</ol>
In retrospect I think testing an even worse case might be advantages, although I don't suspect the tld expression is 
used very often. It's hard to say however, I would like to see an audit of userscripts.org, but even with that it'd 
hard to know what the average case is for all Greasemonkey users, even when you take the install counts from 
userscripts.org into account, although all of that perspective would be nice to have.
<p></p>
<p>
I am an avid user of Greasemonkey and I write quite a few userscripts, and I find that in practice that there are 
very few times when I would need to userscript to use the magic tld expression, so my feeling is that the ratio is probably closer to 
1 tld pattern per 100 or more.
</p>

<h3>Test Pages/Versions</h3>
<p>
I decided to run my tests of the different factors listed above for FF3.5/FF3.6 on WinXP, OSX, and Ubuntu (only FF3.5). The test pages worth pointing out are:
</p><ul>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/original.cfm">Original</a></li>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/alternate3.cfm">Alternate 3</a>: test of only factor I</li>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/alternate5.cfm">Alternate 5</a>: test of only factor II</li>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/alternate6.cfm">Alternate 6</a>: test of factor II + minor change to return a value asap.</li>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/alternate11.cfm">Alternate 11</a>: test of factor I + II, uses array.unshift() and array.join(), and returns a value asap</li>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/alternate12.cfm">Alternate 12</a>: test of factor I + II, uses array.push() and array.join(), and returns a value asap</li>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/alternate13.cfm">Alternate 13</a>: test of factor I + II, and returns a value asap</li>
<li><a rel="nofollow" target="_blank" href="http://erikvold.com/tests/javascript/convert2regexp/alternate15.cfm">Alternate 15</a>: test using array.unshift() and array.join() as only change</li>
</ul>
<p></p>

<h3>Test Results</h3>
<p>
Here are the tests I ran and the results I record (the links are to published google docs spreadsheets, all values are in seconds):
</p><h4>AMD 2.21Ghz, DDR2, WindowsXP</h4>
<ul>
<li>FF3.6 Test: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=ta1SodwhpEDu84DGQFha4IQ&amp;output=html">http://spreadsheets.google.com/pub?key=ta1SodwhpEDu84DGQFha4IQ&amp;output=html</a></li>
<li>FF3.6 Test I: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tRfipvzCX5k_t5C6x3kNpbw&amp;output=html">http://spreadsheets.google.com/pub?key=tRfipvzCX5k_t5C6x3kNpbw&amp;output=html</a></li>
<li>FF3.5 Test: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tSLVJBH7QCS69KYKugQZJEg&amp;output=html">http://spreadsheets.google.com/pub?key=tSLVJBH7QCS69KYKugQZJEg&amp;output=html</a></li>
<li>FF3.5 Test I: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tiZ5WBFo3xyINA1UrVKBG8w&amp;output=html">http://spreadsheets.google.com/pub?key=tiZ5WBFo3xyINA1UrVKBG8w&amp;output=html</a></li>
</ul>
<h4>Intel Duo 2.0Ghz, DDR3, Mac OSX</h4>
<ul>
<li>FF3.6 Test: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tjunrmJDRMql9lraJluyNdw&amp;output=html">http://spreadsheets.google.com/pub?key=tjunrmJDRMql9lraJluyNdw&amp;output=html</a></li>
<li>FF3.6 Test I: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=t-L9k5rRF1WrEkXy0HiuJww&amp;output=html">http://spreadsheets.google.com/pub?key=t-L9k5rRF1WrEkXy0HiuJww&amp;output=html</a></li>
</ul>
<h4>Intel Duo 2.0Ghz, DDR3, Windows XP</h4>
<ul>
<li>FF3.5 Test: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tGdaL4e0NKxWfYewPfKEvvA&amp;output=html">http://spreadsheets.google.com/pub?key=tGdaL4e0NKxWfYewPfKEvvA&amp;output=html</a></li>
<li>FF3.5 Test I: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tSjVusVuI3B_y-77UXaWNjw&amp;output=html">http://spreadsheets.google.com/pub?key=tSjVusVuI3B_y-77UXaWNjw&amp;output=html</a></li>
<li>FF3.6 Test: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tMHASlMvO9MXJeKJgmecKzQ&amp;output=html">http://spreadsheets.google.com/pub?key=tMHASlMvO9MXJeKJgmecKzQ&amp;output=html</a></li>
<li>FF3.6 Test I: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tIwBb34GBojadWHiy_snxyw&amp;output=html">http://spreadsheets.google.com/pub?key=tIwBb34GBojadWHiy_snxyw&amp;output=html</a></li>
</ul>
<h4>Intel 2.0Ghz, DDR, Ubuntu</h4>
<ul>
<li>FF3.5 Test: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=t-zxUEHHGclQYuSYbhTroFA&amp;output=html">http://spreadsheets.google.com/pub?key=t-zxUEHHGclQYuSYbhTroFA&amp;output=html</a></li>
<li>FF3.5 Test I: <a rel="external nofollow" target="_blank" href="http://spreadsheets.google.com/pub?key=tRv04ytir3BkH9oGbUozUqA&amp;output=html">http://spreadsheets.google.com/pub?key=tRv04ytir3BkH9oGbUozUqA&amp;output=html</a></li>
</ul>
Each test was using a version of convert2RegExp, on a set of 50 patterns, 2500 times.
<p></p>


<h2>Results</h2>
<p>
</p><ul>
<li>In all cases alternate 3 was faster than the original.</li>
<li>In all cases alternate 5 and 6 were faster than the original.</li>
<li>In all cases alternate 6 seemed to be slightly faster than 5.</li>
<li>In all cases alternate 15 is much faster than the original for FF3.6, and slightly slower for FF3.5.</li>
<li>For FF3.5 alternate 13 &gt; alternate 12 ~= original ~&gt; alternate 11</li>
<li>For FF3.6 alternate 11 &gt; alternate 13 &gt; alternate 12 &gt; original.</li>
</ul>
Although for FF3.5 we know that alternate 13 is a bad choice because it uses the += operator which result in O(N^2) characters copied, so we can't use that in my opinion. The final choice has to be between alternate 11 and alternate 12. 
<p></p>
<p>
This is where I need your help, I have no idea why using array.unshift() is so much faster in Firefox 3.6, and taken that it is, and that the majority of Greasemonkey users will be using the latest version of Firefox, should we use array.unshift() and not array.push()? 
</p>
<p>
<a title="@erikvold = Twitter" rel="external nofollow" target="_blank" href="http://twitter.com/erikvold/">Tweet Me!</a>
