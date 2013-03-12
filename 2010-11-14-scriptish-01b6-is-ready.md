---
title: Scriptish 0.1b6 is ready!
short URL: http://r.evold.ca/scriptish0.1b6
tags: Google Chrome, Firefox Add-ons, Scriptish
---
Well I've worked quite a few days working on this release of Scriptish, but <a title="Scriptish - AMO" rel="external nofollow" rev="vote-for" target="_blank" href="https://addons.mozilla.org/en-US/firefox/addon/231203/">Scriptish 0.1b6 is finally ready</a>. This release has two main highlights:
</p><ol>
<li>Support for @run-at which was introduced by Google Chrome <a rel="external nofollow" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/10">Issue #10</a>.</li>
<li>Replaces the old status bar icon with a toolbar menu-button which is put into the add-on bar by default <a rel="external nofollow" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/92">Issue #92</a>.</li>
</ol>
<p></p>
<p>
The release also has a few other more minor highlights:
</p><ol>
<li>Supporting @delay (<a rel="external nofollow" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/100">Issue #100</a>)</li>
<li>Added the ID input field to the new script window (<a rel="external nofollow" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/74">Issue #74</a>)</li>
<li>Implemented GM_safeHTMLParser (<a rel="external nofollow" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/113">Issue #113</a>)</li>
<li>Adding a opt-in "Copy Download URL" menu item to the context to user scripts listed in about:addons (<a rel="external nofollow" target="_blank" href="http://github.com/erikvold/scriptish/issues/issue/79">Issue #79</a>)</li>
</ol>
<p></p>

<h2>@run-at</h2>
<p>
I didn't think I'd get this ready in time for Scriptish 0.1 at first, but it turned out to be easier to implement than I had imagined it would be; it doesn't work for Seamonkey still however, it's some minor thing I'm sure, still working that out though.
</p>
<p>
A funny side note is that I think Scriptish is the first user script engine to actually support @run-at! <a rel="external" rev="vote-for" target="_blank" href="http://code.google.com/p/chromium/issues/detail?id=61856">Google Chrome never really support @run-at it turns out</a>. It should be implemented soon I hope though.
</p>

<h2>The toolbar menu-button</h2>
<img src="https://addons.mozilla.org/img/uploads/previews/full/50/50945.png">
<p>
This tool-bar menu-button was requested a <del>lot</del>ton. At first I foolishly tried to support a status bar icon and the toolbar button, but then I finally gave up on that idea and just decided to replace the status bar icon with this toolbar menu-button and auto insert it into the add-on bar the first time Scriptish is run. After this the user can move the toolbar menu-button any where they'd like, and even remove it by customizing their toolbar buttons.
</p>

<p>I hope you enjoy <a title="Scriptish - AMO" rel="external nofollow" rev="vote-for" target="_blank" href="https://addons.mozilla.org/en-US/firefox/addon/231203/">this release of Scriptish</a>, <a target="_blank" rel="external nofllow" href="http://github.com/erikvold/scriptish/issues">let me know if you find any bugs or have any suggestions here</a>.</p>

  	<a href="http://erikvold.com/blog/index.cfm/2010/11/14/scriptish-01b6-is-ready#more" name="more" rel="nofollow"></a>
		
	</div>
	
<script type="text/javascript">
google_ad_client = "pub-5964377618444056";
google_ad_slot = "9885673634";
google_ad_width = 468;
google_ad_height = 60;
</script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"></script><ins style="display:inline-table;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px">
