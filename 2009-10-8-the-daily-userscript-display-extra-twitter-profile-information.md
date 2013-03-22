---
title: The Daily UserScript: Display Extra Twitter Profile Information
short URL: http://r.evold.ca/dailyus54
tags: Usability, Readability, UserScripts, Twitter, Daily UserScript, Automation, Productivity
---
Today's userscript adds three additional pieces of information to <a title="Twitter" rel="external nofollow" target="_blank" href="http://twitter.com/">Twitter</a> profiles, which are the user's id, date created, and time zone.
</p>

<h2>The Unpleasantry:</h2>
<p>
Currently some of a Twitter user's profile information, namely the user's id, date created, and timezone are all not displayed on their profile pages.
</p>

<h2>The Alleviation:</h2>
<p>
Once you install the <a href="http://userscripts.org/scripts/show/59215" title="Twitter Display Extra Profile Information" rel="external nofollow" target="_blank" rev="vote-for">"Twitter Display Extra Profile Information" UserScript</a> all three of the missing pieces of profile information are displayed.
</p>

<h2>Notes</h2>
<ul>
<li>Some users have not selected their time zone, so the time zone information obviously cannot be displayed for them.</li>
<li>I've added commas to the ID as it is initially displayed so that it is easier to read, but for those that want to copy the number without the commas I have added an onClick event that removes them when the span containing the id is clicked.</li>
<li>This userscript takes a second to kick in, so that it will leverage <a title="The Daily UserScript: Display Favorites Count On Twitter Profiles" rel="external nofollow" rev="vote-for" target="_blank" href="http://erikvold.com/blog/index.cfm/2009/10/7/the-daily-userscript-twitter-display-favorites-count">a previous userscript I wrote</a>, and avoid making two identical ajax requests.</li>
