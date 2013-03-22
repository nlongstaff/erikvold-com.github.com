---
title: The Daily UserScript: OpenDNS Create New Shortcut Fix
short URL: http://r.evold.ca/dailyus36
tags: Usability, Internet, UserScripts, Daily UserScript, Automation, Productivity
---
If you don't use <a title="OpenDNS" rel="external nofollow" rev="vote-for" target="_blank" href="http://www.opendns.com/">OpenDNS</a> then stop reading and go sign up immediately.
Once you have OpenDNS, and have started using the shortcuts feature, then you will notice that the fastest way to create a new shortcut off the cuff is to just type it in to the location bar.
Once you do this, OpenDNS will realize that you did not provide a url, and then it will check if the provided string is an existing shortcut, if the string is not a shortcut, then you will be taken to a OpenDNS custom search page which provides a convenient form to create a new shortcut.
</p>

<h2>The Unpleasantry:</h2>
<p>
When you have tried a shortcut that does not exist, there is a "Create new shortcut for ..." link for the string that you are provided (if it is a valid shortcut string). When you click this link a form is displayed which you can use to create a new shortcut. The problem is that the form does not auto populate with the string that brought me to the page, which is the string I want to use for the new shortcut &gt; 99% of the time.
</p>

<h2>The Alleviation:</h2>
<p>
Once you install the <a href="http://userscripts.org/scripts/show/56857" title="OpenDNS Create New Shortcut Fix" rel="external nofollow" target="_blank" rev="vote-for">"OpenDNS Create New Shortcut Fix" UserScript</a> the shortcut string is auto populated in the create new shortcut form.
