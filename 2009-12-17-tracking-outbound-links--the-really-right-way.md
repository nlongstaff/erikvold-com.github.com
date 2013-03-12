---
title: Tracking Outbound Links - The Really Right Way
short URL: http://r.evold.ca/outtrac
tags: Javascript, Productivity, Google Website Optimizer, Analytics, Google Analytics
---
About 5 months ago Eric Vasilik wrote a post on his <a title="GWO Tricks Blog" rel="external nofollow" target="_blank" href="http://gwotricks.com/">GWO Tricks</a> blog about <a title="Tracking Outbound Links -- The Right Way" rel="external nofollow" rev="vote-against" target="_blank" href="http://www.gwotricks.com/2009/07/tracking-outbound-links-right-way.html">Tracking Outbound Links -- The Right Way</a> which was ment to point out a solution for the problem with <a title="How do I manually track clicks on outbound links?" rel="external nofollow" rev="vote-against" target="_blank" href="http://www.google.com/support/analytics/bin/answer.py?hl=en&amp;answer=55527">the technique outlined in the Analytics Help Center article called "How do I manually track clicks on outbound links?"</a>, is that it suffers from a <a title="Race Condition - Wikipedia" rel="external nofollow info" data-source="Wikipedia" target="_blank" href="http://en.wikipedia.org/wiki/Race_condition">Race Condition</a> which may mean the tracking doesn't take place. If you haven't read Eric's article, please do.
</p>
<p>
Well as readers of my blog would know, I recently wrote a <a title="Click Tracking JavaScript Library Now Available" rev="vote-for" target="_blank" href="http://erikvold.com/blog/index.cfm/2009/12/11/click-tracking-javascript-library-now-available">JavaScript click tracking library</a> which can be <a title="erikvold / click-tracking-js-lib" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/click-tracking-js-lib">found at GitHub here</a>. In <a title="Click Tracking JavaScript Library Now Available" rev="vote-for" target="_blank" href="http://erikvold.com/blog/index.cfm/2009/12/11/click-tracking-javascript-library-now-available">the blog post</a> I mention that I implemented Eric Vasilik's "Right Way" to track links, but today I started thinking about this some more.
</p>
<p>
I decided to do some searching on how to cancel a click event, and I found <a title="Event.stop()" rel="external nofollow" target="_blank" href="http://particletree.com/notebook/eventstop/">a great old blog post from 2006 by Ryan Campbell pretty quickly which mentions a method implemented by Prototype called Event.stop()</a>. So I decided to dig in to the Prototype code to see what Event.stop() did exactly, so I could extract it, and I found that it does two things, one is to stop the event propagation, and the second is to stop the default behavior for the event. At the end of the post Ryan said that it not work for Safari 2.0.3, which is why it could not be relied on at the time, but today Safari 2.0.3 is dead, and I tested Safari 3 out which works. In fact I decided to do some PPK style testing and try test cases on every browser I could.
</p>
<p>
After seeing that Event.stop() had two purposes I wanted to find out why this was done, and found <a title="Event.stop() - Prototype JS" rel="external nofollow" target="_blank" href="http://www.prototypejs.org/api/event/stop">this documentation page for Event.stop()</a>, which says this was done "because stopping one of those aspects means, in 99.9% of the cases, preventing the other one as well", but in the case of simply click tracking we don't really want to stop the event propagation, we just want to stop the default action from being triggered eventually. So here is what my update to Eric's example looks like:
</p>
<div class="code">&lt;a id="example" href="<a target="_blank" href="http://www.example.com">http://www.example.com</a>"&gt;Click me&lt;/a&gt;<br>
&lt;script type="text/javascript"&gt;<br>
function doGoal(e){<br>
  if(!e) var e = window.event;<br>
<br>
  var targ;<br>
  if ( e.target ) targ = e.target;<br>
  else if ( e.srcElement ) targ = e.srcElement;<br>
  // Safari..<br>
  if ( targ.nodeType == 3 ) targ = targ.parentNode;<br>
<br>
  setTimeout('document.location = "' + targ .href + '"', 100);<br>
<br>
  try{<br>
    var pageTracker=_gat._getTracker("UA-123456-1");<br>
    pageTracker._trackPageview("<a target="_blank" href="http://www.example.com">http://www.example.com</a>");<br>
  }<br>
  catch(err){}<br>
<br>
  if (e.preventDefault) e.preventDefault(); // w3c<br>
  else e.returnValue  = false; // for ie<br>
}<br>
if ( document.body.addEventListener ) {<br>
  // w3c<br>
  document.getElementById('example').addEventListener( "click", doGoal, false );<br>
}<br>
else if ( document.body.attachEvent ) {<br>
  // ie<br>
  document.getElementById('example').attachEvent( "onclick", doGoal );<br>
}<br>
&lt;/script&gt;</div>
<p>
To try the code above see the <a rel="external nofollow" href="http://erikvold.com/tests/javascript/gwoReallyRightClickTracking.html">test page here</a>. I have tested this out on IE6+, FF2+, Opera9+, Safari for the iPhone OS 3.0, Google Chrome, and Safari3+ on MacOSX and WindowsXP and they all work, so I am pretty confident that this is going to work for something like ~99% of web users today, and since it would not error even for a user using Safari 2 (which I wasn't able to test), and Safari 2 is so slow, there is a good chance the user would still be tracked anyhow.
</p>
<p>
If anyone else could try this out on some other browsers at let me know what they find good or bad that would be nice so that I can add them to the list above. The best way to test the test page is to comment out the setTimeout line, and make sure that clicking the link doesn't do anything.
</p>
<p>
The beautiful part about this method is that it is totally unobtrusive JavaScript code, and will work even if you are using the onclick attribute for other site functionality (even though you shouldn't ever use the onclick attribute).
</p>
<p>
Merry Clicking!
</p>
<p>
P.S. The <a title="erikvold / click-tracking-js-lib" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/click-tracking-js-lib">Click Tracking JavaScript Library</a> has been updated to use this really right method, check it out if you haven't already!
</p>
