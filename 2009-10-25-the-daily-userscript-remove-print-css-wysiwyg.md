---
title: The Daily UserScript: Remove Print CSS (WYSIWYG)
short URL: http://r.evold.ca/dailyus67
tags: Usability, Internet, Readability, Daily UserScript, UserScripts, CSS, Automation, Productivity
---
This userscript removes all <a title="Cascading Style Sheets" rel="external" rev="" target="_blank" href="http://www.w3.org/Style/CSS/">CSS</a> that is only for media="print", and makes the media="..screen.." into media="...screen..., print" so that what you see on the screen is what you will get for your print out of the page.
</p>

<h2>The Unpleasantry:</h2>
<p>
Currently if you print a webpage (or go to print preview) you may notice that most sites do not look the same as they do on the screen when you try to print one of their pages. This is because the page has CSS specifically designated for media="screen" which is different than the CSS they use for media="print".
</p>

<h2>The Alleviation:</h2>
<p>
Once you install the <a href="http://userscripts.org/scripts/show/60514" title="Remove Print CSS (WYSIWYG)" rel="external" target="_blank" rev="vote-for">"Remove Print CSS (WYSIWYG)" UserScript</a> there will be a Greasemonkey menu command that you can use called 'Remove Print CSS' which removes the media="print" CSS and makes the media="...screen..." CSS media="...screen..., print" CSS, which means that the same CSS used for your screen will be used when you try to print a page.
</p>

  	<a href="http://erikvold.com/blog/index.cfm/2009/10/25/the-daily-userscript-remove-print-css-wysiwyg#more" name="more" rel="nofollow"></a>
		
<h3>Greasemonkey Ubiquity Command Method</h3>
<p>
<a href="http://erikvold.com/blog/index.cfm/2009/7/16/greasemonkey-command-with-input-string-for-ubiquity-05" title="Greasemonkey Command With Input String For Ubiquity 0.5" rel="external nofollow" rev="vote-for" target="_blank">I previously released a <i>Greasemonkey</i> Ubiquity command</a> which you can use with this userscript.
</p><ol>
<li>Hit your Ubiquity hotkey</li>
<li>Type "gm Remove Print CSS" in the Ubiquity command prompt.</li>
</ol>
<p></p>

<h2>Screen Shot</h2>
<img title="Screen shot of 'Remove Print CSS' UserScript" src="http://s3.amazonaws.com/uso_ss/3518/large.png">

<h2>Notes</h2>
<p>
Firefox does not print background colors or images by default, so you must change this manually if you wish to print backgrounds, in order do to so:
</p><ol>
<li>Go to the "File" menu in Firefox, and then "Page Setup".</li>
<li>When the "Page Setup" multiple tabbed dialog box appears, go to the "Format &amp; Options" tab.</li>
<li>In the the "Options" section towards the bottom, check the "Print Background (colors &amp; images)" option.</li>
</ol>
<p></p>
	</div>
	
<script type="text/javascript">
google_ad_client = "pub-5964377618444056";
google_ad_slot = "9885673634";
google_ad_width = 468;
google_ad_height = 60;
</script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"></script><ins style="display:inline-table;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px"><ins id="aswift_0_anchor" style="display:block;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px"><iframe marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" onload="var i=this.id,s=window.google_iframe_oncopy,H=s&amp;&amp;s.handlers,h=H&amp;&amp;H[i],w=this.contentWindow,d;try{d=w.document}catch(e){}if(h&amp;&amp;d&amp;&amp;(!d.body||!d.body.firstChild)){if(h.call){setTimeout(h,0)}else if(h.match){w.location.replace(h)}}" id="aswift_0" name="aswift_0" style="left:0;position:absolute;top:0;" frameborder="0" height="60" scrolling="no" width="468"></iframe></ins></ins>

	<div class="byline" id="bottomByline">
