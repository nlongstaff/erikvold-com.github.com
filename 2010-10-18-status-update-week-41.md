---
title: Status Update: Week 41
short URL: http://r.evold.ca/2010w41
tags: UX, Status Update, UserScripts, Projects, Scriptish
---
Well I blame <a title="evalInSandbox crashes" rel="external nofollow" rev="vote-for" target="_blank" href="https://bugzilla.mozilla.org/show_bug.cgi?id=604368">bug 604368</a> for bogging me down a bit this week. I lost some time dealing with crashes and trying to determine the cause at first, until I finally came across #604368. Oh well though, no hard feelings, it is called Minefield, and the changes are meant to improve performance, so I'm not upset at all. I was able to get some progress done on Scriptish still by installing the latest Firefox beta and Seamonkey beta and using those.</p>
<h2>Done</h2>
<h3>Scriptish</h3>
<ul>
<li>Seamonkey is now supported (<a title="Issue #52 - Support Seamonkey - Scriptish" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/52">issue #52</a>).</li>
<li>Auto generating homepage URLs from download URLs when @homepageURL is not defined for user scripts installed from <a title="UserScripts.org" rel="external nofollow" rev="vote-for" target="_blank" href="http://userscripts.org/">userscripts.org</a> (<a title="Issue #76 - Scriptish" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/76">issue #76</a>), <a title="Gist.GitHub" rel="external nofollow" rev="vote-for" target="_blank" href="http://gist.github.com/">gist.github.com</a> (<a title="Issue #77 - Scriptish" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/77">issue #77</a>), or <a title="GitHub" rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/">github.com</a> (<a title="Issue #85 - Scriptish" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/85">issue #85</a>).</li>
<li>Updated GM_notification(msg) api to now be GM_notification(msg, title, img, callback).</li>
<li>Added a new default user script icon.</li>
<li>Fixed <a target="_blank" rev="vote-for" rel="external nofollow" href="http://github.com/erikvold/scriptish/commit/a5b25fd53968ea7031cb786b2199b1e45bc42eb0">a bug</a> for scripts that attempt to overwrite a global variable, like scrollTo.</li>
<li>Fixed <a title="Issue #84 - Scriptish" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/84">a bug</a> where the uninstall state of a user script was forgotten when returning to the user script list view from a user script detail view.</li>
<li><a target="_blank" href="http://github.com/erikvold/scriptish/commit/ac9ffe79cda74c06072be242a8ca7402603f7e1d">Closing GM_worker threads</a> when a window closes now.</li>
<li>Fixed <a target="_blank" href="http://github.com/erikvold/scriptish/commit/0fa4ca80c0fea16677f30db9fdcb48b18763a800">a small bug</a> where content pages could have detected Scritpish on the user's browser by checking for the presence of some resource: url files which Scriptish provides. Now afaik Scriptish cannot be detected, and <a target="_blank" rel="external nofollow" href="http://groups.google.com/group/greasemonkey-dev/browse_thread/thread/59f7ba455fa17a92">Greasemonkey can be detected</a>.</li>
<li>Made <a target="_blank" href="http://github.com/erikvold/scriptish/commit/2c7a6e8d05d3fa963d5a7324446344089d9445d5">a small UX change</a> to the status bar menu, when enabling or disabling a script the menu no longer automatically closes, so that you can easily enable/disable multiple scripts and it's still easy to close the menu by clicking anywhere else.</li>
</ul>
<p>
I also got some progress made on implementing @run-at document-start, it isn't going to be part of 0.1 I think at this point, but so far it looks promising, nothing pushed online yet though. 
</p>


  	<a href="http://erikvold.com/blog/index.cfm/2010/10/18/status-update-week-41#more" name="more" rel="nofollow"></a>
		
<h2>Next</h2>
<p>
Finish Scriptish 0.1 and submit it for review at <a title="Addons.Mozilla.Org" rel="external nofollow" rev="vote-for" target="_blank" href="http://addons.mozilla.org/">AMO</a> (depends on state of bug 604368). Continue effort on implementing @run-at document-start
