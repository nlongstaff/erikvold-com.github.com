---
title: Status Update: Week 40
short URL: http://r.evold.ca/2010w40
tags: Status Update, GitHub, Scriptish
---
<h2>Done</h2>
<h3>Scriptish</h3>
<ul>
<li><a title="evalInSandbox improvements - Scriptish" rel="external" target="_blank" href="http://github.com/erikvold/scriptish/commit/17f1c13491d84f68a86cb4b0a3faf2a734ad0835">Merged</a> in some changes to how scripts are evaluated by Kris Maglione. This allows Scriptish to provide much better error reporting. Also <a title="@unwrap is no longer supported - Scriptish" rel="external" target="_blank" href="http://github.com/erikvold/scriptish/commit/d82b7e006b1c4a4276a59d8c5b7fcdcaa82a16d6">@unwrap is no longer supported</a>.</li>
<li><a title="Staging Build - Scriptish" rel="external nofollow" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/69">Created a staging/beta build/channel</a> with updates enabled, you can find these releases on <a title="Scriptish Downloads" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/scriptish/downloads">the github downloads page for Scriptish</a>. After Scriptish 0.1 is released I will only release non-betas and non-alphas (ie: "stable" releases) to <a title="Addons.Mozilla.Org" rel="external nofollow" rev="vote-for" target="_blank" href="http://addons.mozilla.org/">AMO</a>, and all stable/beta/alphas will be released thru this staging channel.
</li>
<li><a rel="external" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/71">Supporting thumbs for @screenshot</a>.</li>
<li><a title="Implement update feature for user scripts - Scriptish" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/8">Supporting @updateURL</a>; Scriptish now updates user scripts I also had a chance to write <a title="Scriptish 0.1b4 Can Update Your User Scripts" rev="vote-for" target="_blank" href="http://erikvold.com/blog/index.cfm/2010/10/10/scriptish-01b4-can-update-your-user-scripts">a blog post that talks all about this earlier today</a> while I was watching some football.
</li><li><a title="Issue #62 - Scriptish" rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/62">Fixed a bug that froze Firefox when pressing the "options" button</a>. Greasemonkey has <a title="Issue #1203 - Greasemonkey" rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/greasemonkey/greasemonkey/issues/issue/1203">the same issue</a>, so I made a <a rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/erikvold/greasemonkey/commit/97e5542c5f17d10ad3ca28d663a6ebd82acfa6ef">patch for Greasemonkey</a> as well.</li>
<li><a title="Issue #76" rel="external nofollow" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/76">Auto-generating homepage URLs for user scripts downloaded from userscripts.org</a> (when not in private mode).</li>
</ul>

<h3>GitHub Flavored Markdown</h3>
<p>
Made a <a title="Don't add GFM to code blocks" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/github-flavored-markdown/compare/github:gh-pages...erikvold:issue-5">patch</a> for <a title="Issue #5" rel="external" rev="vote-for" target="_blank" href="http://github.com/github/github-flavored-markdown/issues#issue/5">issue 5</a>, which is basically that GitHub spice is being added to code blocks.
</p>


  	<a href="http://erikvold.com/blog/index.cfm/2010/10/10/status-update-week-40#more" name="more" rel="nofollow"></a>
		
<h2>Next</h2>
<p>
Next week I hope to tackle some more issues with the GitHub flavored markdown script, start planning user script communication some more or maybe get some work started on that, complete <a title="Scriptish Issues" rel="external" target="_blank" href="http://github.com/erikvold/scriptish/issues">the "0.1" issues</a> for Scriptish, and give some time to reviewing <a href="http://github.com/mozilla/ubiquity">Ubiquity</a>'s source code.
</p>
