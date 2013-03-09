---
tite: Restartless Firefox Add-ons, Part 7: CSS
short URL: http://r.evold.ca/rrffap7
tags: UserStyles, Firefox Add-ons, CSS
---
If you want to use css in your restartless addon, then you have wondered what the best way to do so is. There are many options, you could create xul/html elements to inject css, or you could simply alter the style attribute of elements you care about, but the other option (and the best one imo) is to use the <a target="_blank" title="nsIStyleSheetService - MDN" rel="external" rev="vote-for" href="https://developer.mozilla.org/En/NsIStyleSheetService">nsIStyleSheetService</a> to load css.
</p>

<h3>Loading and unloading</h3>
<p>
Use the <a target="_blank" title="loadAndRegisterSheet() - MDN" rel="external" href="https://developer.mozilla.org/En/NsIStyleSheetService#loadAndRegisterSheet()">loadAndRegisterSheet()</a> method to load css at startup, and then use <a target="_blank" title="unregisterSheet() - MDN" rel="external" href="https://developer.mozilla.org/En/NsIStyleSheetService#unregisterSheet()">unregisterSheet()</a> to unload the file during shutdown.
</p>

<h3>Getting CSS URL</h3>
<p>
You can use the bootstrap.js's "__SCRIPT_URI_SPEC__" constant to find the url of your css. For example, if you named your css file main.css and it was in a 'skin' folder in the root of your addon, then the url of the css file will be:
</p><div class="code">var cssURL = __SCRIPT_URI_SPEC__ + "../skin/main.css";</div>
<p></p>

<h3>@-moz-document</h3>
<p>
You must use <a target="_blank" title="@-moz-document - MDN" rel="external" rev="vote-for" href="https://developer.mozilla.org/en/CSS/@-moz-document">@-moz-document</a> however to define which content or chrome page(s) the css rules that you are defining should run on.  <a target="_blank" title="UserStyles Coding" rel="external nofollow" rev="vote-for" href="http://userstyles.org/help/coding">Userstyles have the same requirements</a>.
</p>

<h2>Example</h2>
<p>
<a target="_blank" rel="external nofollow" href="https://github.com/Mardak/searchTabs/commit/b1e021d154bd2013caaa8e3453ad0053afb6de02">Here is a example</a> where I separated the css from the bootstrap.js file for a addon called <a target="_blank" title="Search Tabs for Firefox - Github" rel="external nofollow" href="https://github.com/Mardak/searchTabs">Search Tabs</a>.
</p>

  	<a href="http://erikvold.com/blog/index.cfm/2011/6/19/restartless-firefox-addons-part-7-css#more" name="more" rel="nofollow"></a>
		
	</div>
	
<script type="text/javascript">
google_ad_client = "pub-5964377618444056";
google_ad_slot = "9885673634";
google_ad_width = 468;
google_ad_height = 60;
</script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"></script><ins style="display:inline-table;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px">
