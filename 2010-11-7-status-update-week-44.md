---
title: Status Update: Week 44
short URL: http://r.evold.ca/2010w44
tags: Status Update, Firefox Add-ons, Scriptish, Firefox
---
<h2>Done</h2>
<h3>Restartless Restart</h3>
<p>
The main event for me this week was releasing <a title="Restartless Restart for Firefox and Seamonkey - AMO" rel="external" rev="vote-for" target="_blank" href="https://addons.mozilla.org/en-US/firefox/addon/249342/">Restartless Restart</a>, which is a very tiny and restartless add-on which adds a "Restart" menu item to the "File" menu and a restart hotkey (ctrl/cmd+alt+r) to Firefox or Seamonkey. I hope you like it!.
</p>
<p>
Thanks to <a title="supahgreg - GitHub" rel="external" rev="vote-for" target="_blank" href="https://github.com/supahgreg">supahgreg</a> for the Windows 7 patch!
</p>

<h3>Scriptish</h3>
<ul>
<li>Supporting various headers introduced by IE Scripts: @injectframes, @defaulticon, and @website.</li>
<li>Made a few bug fixes for Seamonkey related to the toolbar. I'm going to need to spend more time testing + planning this before the next release though, because I'm not sure if Seamonkey will be using a add-on bar or not yet, I assume they will and just haven't yet, but I'll plan for now as though they won't.</li>
<li>Implemented GM_safeHTMLParser(aHTMLStr) (issue <a title="Issue 113 - Scriptish" rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/erikvold/scriptish/issues/issue/113">#113</a>).</li>
<li>Reviewed and merged update from <a title="supahgreg - GitHub" rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/supahgreg">supahgreg</a> to add a optional "Copy Download URL" menu item to user scripts in about:addons (issue <a title="Issue 79 - Scriptish" rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/erikvold/scriptish/issues/issue/79">#79</a>).</li>
</ul>

<h3>Mozilla Labs: Prospector</h3>
<ul>
<li>Fixed a couple of things that caused warning messages.</li>
<li>Small patch for Instant Preview so that it doesn't check for url bar selections while the url bar suggestion pop up is closed (issue <a target="_blank" title="Issue 24 - Prospector" href="https://github.com/mozilla/prospector/issues/issue/24">#24</a>).</li>
<li>Changed the click handler for suggestions from Find Suggest so that if you click a suggestion that is the same as your query (which it is after the first time you click a suggestion), then that triggers the next button (issue <a title="Issue 32 - Prospector" rel="external nofollow" rev="vote-for" target="_target" href="https://github.com/mozilla/prospector/issues/issue/32">#32</a>).</li>
</ul>


  	<a href="http://erikvold.com/blog/index.cfm/2010/11/7/status-update-week-44#more" name="more" rel="nofollow"></a>
		
<h2>Next</h2>
<p>
Get Scriptish ready! and write part two of my Restartless Firefox add-ons series.
</p>
