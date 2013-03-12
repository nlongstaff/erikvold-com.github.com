---
title: Making All Internal Link Clicks a Conversion
tags: Javascript, Programming, Troubleshooting, Productivity, Automation, Analytics, Google Website Optimizer
---
A common use case of Google Website Optimizer (GWO) is to test (in order to optimize) a page's ability to have a user click an internal link, I like to call this the 
<strong>internal pass thru rate</strong> of a page. 
Meaning the click event of any internal link on a test page will count as a conversion for the test. 
This is not the opposite of the <a title="external nofollow" target="_blank" href="http://en.wikipedia.org/wiki/Bounce_rate">bounce rate</a> 
which it is sometimes mistaken for, because the pass thru rate is oblivious to the difference between first time visits and other visits. 
The pass thru rate is not the same as the <a title="Click Thru Rate" rel="external nofollow" target="_blank" href="http://en.wikipedia.org/wiki/Click-through_rate">click thru rate</a> either, because 
the pass thru rate relates to visits and the click thru rate relates to impressions.
This is usually desired either because you have no other conversion to track -- although time on page is always another option, but the results typically take longer to acquire -- or 
because you wish to optimize the bounce rate, and this is as close as you can get at the moment. 
</p>

<p>
Google doesn't have any documentation on how to track all internal links on a page, but <a title="Counting a conversion when a link is clicked" rel="external nofollow" target="_blank" href="http://www.google.com/support/websiteoptimizer/bin/answer.py?hl=en&amp;answer=93181">they do provide a page on how to track an individual link</a>, which any novice JavaScript programmer can 
follow in order to track all of the internal links, by simply repeating the process for every internal link on the test page(s). 
The main problem here is that Google's process requires that the onclick attribute of every link be set to "return false", albeit this can be done via JavaScript, it is not desirable. 
Google Website Optimizer's Technical Lead Engineer, Eric Vasilik, explained Google's method in a blog post from August 2009, called "<a title="Tracking Outbound Links -- The Right Way" rel="external nofollow" target="_blank" href="http://www.gwotricks.com/2009/07/tracking-outbound-links-right-way.html">Tracking Outbound Links -- The Right Way</a>", 
and I wrote a follow up post in December 2009, called "<a title="Tracking Outbound Links - The Really Right Way" target="_blank" href="http://erikvold.com/blog/index.cfm/2009/12/17/tracking-outbound-links--the-really-right-way">Tracking Outbound Links - The Really Right Way</a>" in which I describe a better method which is slightly harder to implement but does not require any use of the <em>onclick</em> attribute.
</p>
<p> 
If you are at least a novice JavaScript programmer that wants to measure the pass thru rate of a page, then you can probably implement Google's method or mine with relative ease after reading the blog posts I mentioned.
</p>

<p>
If you are not a novice JavaScript programmer, or simply want to save some time implementing this type of conversion over and over again, then I would suggest you take a look at the 
<a title="Click Tracking JavaScript Library - Erik Vold's Blog" rev="vote-for" target="_blank" href="http://erikvold.com/blog/index.cfm/2009/12/11/click-tracking-javascript-library-now-available">JavaScript click track library that I released in early December '09</a>, 
because with this javascript library you could simply add the following code to your page:
</p>
<div class="code">clickTrackingLib.addMatches([{<br>
    match: clickTrackingLib.getMatchPreset( "all-internal" ),<br>
    trackingFunc: function(e, link){<br>
        var gwoTracker=_gat._getTracker("UA-XXXXXXX-X");<br>
        gwoTracker._trackPageview("/YYYYYYYYYY/goal");<br>
    }<br>
}]);<br>
clickTrackingLib.attachTrackingFunctions(null,99);</div>
<p>
The above code will tag all non-rel-external links or links with the internal hostname on the page; for just internal hostname links replace "all-internal" with "internal-hostname". 
I would recommend that you wrap the above into a function though, to be run on the DOM ready event or page loaded event, with jQuery that would look like:
</p>
<div class="code">$(document).ready(function(){<br>
    clickTrackingLib.addMatches([{<br>
        match: clickTrackingLib.getMatchPreset( "all-internal" ),<br>
        trackingFunc: function(e, link){<br>
            var gwoTracker=_gat._getTracker("UA-XXXXXXX-X");<br>
            gwoTracker._trackPageview("/YYYYYYYYYY/goal");<br>
        }<br>
    }]);<br>
    clickTrackingLib.attachTrackingFunctions(null,99);<br>
});</div>
<p>
The first line in the code above will setup a function to be executed when the DOM is ready, and all of the page's links have been added. 
The second line is the first of the function the be executed on DOM ready, and it is adding an array of match objects to the global clickTrackingLib object provided by the click tracking library that I wrote. 
The following 5 lines define a single match object for the input array, which consists of a preset match function to match internal links (as I said already this preset can be changed, and you can also define 
a custom match function), and a simple tracking function. 
When <em>clickTrackingLib.attachTrackingFunctions(null,99);</em> is executed, links are tested against the match functions in the clickTrackingLib object's match object array, and where there is a match 
the associated trackingFunc function is made in to a onclick event listener for the matched link. As for the two inputs, the null means try all links, and the 99 means use a 99 millisecond delay. 
</p>

<p>
At this point you might be wondering, what if the page has dynamic content, which is changed via ajax, well in that case you can round up the new link(s) in to an array and run the 
<em>clickTrackingLib.attachTrackingFunctions(links, delay)</em> function again like so:
</p>
<div class="code">clickTrackingLib.attachTrackingFunctions(newLinksArray,99);</div>
<p><em>clickTrackingLib.attachTrackingFunctions(links, delay)</em> will also accept a single link.</p>
