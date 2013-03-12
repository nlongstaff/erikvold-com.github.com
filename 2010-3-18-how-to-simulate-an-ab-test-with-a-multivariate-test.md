---
title: How To Simulate An A/B Test With A Multivariate Test
short URL: http://r.evold.ca/ab2mvt
tags: Google Website Optimizer
---
A very common question I see on the <a title="GWO Help Forum" rel="external nofollow" target="_blank" href="http://www.google.com/support/forum/p/websiteoptimizer?hl=en">Google Website Optimizer (GWO) Help Forum</a> is how to perform an A/B test on page sets with dynamic urls. For example, if you want to perform an A/B test of different layouts across all of your product pages to determine which layout performs better, in which case the simple A/B test that GWO provides will not work, but you can achieve this by simulating an A/B test with a multivariate test (MVT) as I'll explain to you now.
</p>

<p>
First I want to explain how an A/B test works. When you setup an A/B test you provide Google with page A's url and page B's url, then Google will give you three tags/scripts: a control script, a tracking script, and a conversion script. The control script is what I want to focus your attention on, the difference between an A/B test's control script and a multivariate test's control script is a single line, the last line, which looks like this:
</p>
<div class="code">&lt;script&gt;utmx("url",'A/B');&lt;/script&gt;</div>
<p>
Now ask yourself what does this code do exactly? well if you were to grab the siteopt.js code, beautify it, and dig through it then you'll see that the code above uses the page B url that you provided to do the following when a visitor is meant to see page B.
</p>
<div class="code">&lt;script&gt;<br>
window.location.replace( pageBURL );<br>
&lt;/script&gt;</div>
<p>
Where <em>pageBURL</em> is the url for page B that you provided to Google in addition to any query string items and url hash that is in the url when your visitor hits page A.
</p>

<p>
This is how a GWO A/B test performs the redirection to page B. An important feature to notice here is that window.location.replace( ... ); is used and not window.location.href = ...; or window.location.assign( ... );. This is important because using the replace() method means that the user will not be able to use the back button to get back to page A. If GWO used window.location.href = pageBURL; then if the user pressed the back button they would be sent to page A which would redirect them to page B again, so they would have to go two pages back in order to get to the page they were at before landing on page A. This is obviously not desirable.
</p>

<p>
So now the question becomes how can one simulate a A/B test's redirection with a multivariate test? Well here are the steps that I give to anyone that asks:
</p><ol>
<li>Create a multivariate test.</li>
<ol>
<li>Provide Google with any url in the set of urls that your wish to test. Google asks you for the test page's url is for two reasons, the first is so that they can scan the page and verify that the page has been 'tagged' properly, and the second reason is so that they can show you a preview of the test.</li>
</ol>
<li>Tag your pages with the control script, tracking script and conversion script all as you normally would.</li>
<li>Now, put the section code directly below the control script and call the section whatever you want, let's call it "redirect" for example's sake. Make sure that the section code is surrounding nothing, white space, or blank space.</li>
<li>Verify your pages and move on to step 3: Create variations.</li>
<li>
<p>Create a new variation of your "redirect" section for each page variation that you desire (ie: if you just want a A/B test create one variation, if you want a A/B/C test make two variations, and so on). For each of these variations that you create, insert the following:
</p>
<div class="code">&lt;script&gt;<br>
window.location.replace( window.location.protocol + "//" + page + window.location.search + window.location.hash );<br>
&lt;/script&gt;</div>
<p>
Where <em>page</em> is something like www.yourdomain.com/product/123B.html, since you will likely be trying to implement a dynamic A/B test <em>page</em> will be dynamic, so it can either be a javascript variable that you define before/above the section code, or it can be derived from the window.location.href by using the replace() method. If <em>page</em> must contain a query string then you will want to modify the string above, which should be obvious. So I do not suggest that you copy and paste the code above, I suggest that you think about it to figure out how best to apply this principal to your use case. If your <em>page</em> variable must contain a query string then consider modifying window.location.search in the above code with window.location.search.replace(/^\?/,"&amp;"), which will replace the '?' with '&amp;' at the start of the string; this is likely be the only change you need to make, but in edge cases you may want to strip more data out of window.location.search, so think about it.
</p>
</li>
</ol>
<p></p>

<p>
I hope this helps, happy testing!
</p>
