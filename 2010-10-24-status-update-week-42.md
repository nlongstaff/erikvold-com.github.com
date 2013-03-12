---
title: Status Update: Week 42
short URL: http://r.evold.ca/2010w42
tags: Status Update, UX, Internet, Firefox, Usability, GitHub, Productivity, Scriptish, Regular Expressions
---
<p>Well I started this week working on Scriptish, but I felt that I needed a break after working on it nearly every day for the past few weeks, so I spent about half the week working on a few other things.</p>
<p>
Mozilla Lab's Prospector add-ons, <a title="Mozilla Lab's presents Prospector" rel="external" rev="vote-for" target="_blank" href="https://mozillalabs.com/blog/2010/10/exploring-search-in-the-context-of-the-browser-with-prospector/">which they announced two weeks ago</a>, caught my attention and I started doing a little hacking on one of them; after spending some time using 2 of the currently 4 prospector add-ons I can tell you that I really like them, because they each focus on solving a single, particular, searching UX/usability issue in the context of the browser, and they're restartless!
</p>
<h2>Done</h2>
<h3>Scriptish</h3>
<ul>
<li>Released Scriptish 0.1b5 on the 19th.</li>
<li>Replacing the status bar icon with a frequently requested toolbar menu-button (It's a button &amp; a drop-down menu), which is added to the add-on bar when Scriptish is installed for the first-time, or when Scriptish is upgraded from a version less than or equal to Scriptish 0.1b5.</li>
<li>Added a ID field to the new script window.</li>
</ul>

<h3>GitHub Flavored Markdown</h3>
<ul>
<li>Created some <a rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/erikvold/github-flavored-markdown/commit/934e19dbb4470d36b72d7a4996a52c9086517562">GitHub spice for compare urls</a> (issue <a target="_blank" title="GFM Issue #9 - GitHub" rel="external nofollow" rev="vote-for" href="http://github.com/github/github-flavored-markdown/issues/issue/9">#9</a>).</li>
</ul>

<h3>MDC</h3>
<p>I noticed that there wasn't any documentation on em:bootstrap on the page describing install manifests, so <a title="Install Manifests - MDC" rel="external nofollow" target="_blank" href="https://developer.mozilla.org/en/Install_Manifests#bootstrap">I added something basic with a link to more information</a>.</p>

<h3>Mozilla Labs: Prospector - Find Suggest</h3>
<ul>
<li>Performance tweaks.</li>
<li>Bug fix when using the find bar on a blank page, which causes an error to be thrown (issue <a rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/mozilla/prospector/issues/issue/1">#1</a>).</li>
<li>Sorting words with equal frequency alphabetically (issue <a rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/mozilla/prospector/issues/issue/3">#3</a>).</li>
<li>Changing the regular expression used to split words (issue <a rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/mozilla/prospector/issues/issue/4">#4</a>).</li>
<li>Requiring words to be 3 characters or longer (issue <a rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/mozilla/prospector/issues/issue/2">#2</a>).</li>
<li>Making the suggestion limit a user preference (issue <a rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/mozilla/prospector/issues/issue/7">#7</a>).</li>
</ul>


  	<a href="http://erikvold.com/blog/index.cfm/2010/10/24/status-update-week-42#more" name="more" rel="nofollow"></a>
		
<h2>Next</h2>
<p>Well I still want to get Scriptish 0.1 out the door soon, but I've decided not to rush it, I'll probably have another beta out in a week or so without many more changes than those that I have already made on top of 0.1b5 (like adding the toolbar button), let that swirl for another week or so, then release Scriptish 0.1.</p>

<p>
The Prospector add-ons have caught my interest so I'll spend some time this week contributing what I can.
</p>
