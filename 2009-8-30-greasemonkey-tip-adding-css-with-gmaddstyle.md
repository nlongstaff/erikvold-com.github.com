---
title: Greasemonkey Tip: Adding CSS With GM_addStyle
short URL: http://r.evold.ca/ustipaddcss
tags: Javascript, Daily UserScript, Greasemonkey, CSS, Programming
---
Adding style to a webpage with <a title="Greasespot" rel="external nofllow" rev="vote-for" target="_blank" href="http://www.greasespot.net/">Greasemonkey</a> is extremely easy, but I have noticed a lot of userscript code that either ignores the <a title="Greasemonkey Wiki: GM_addStyle(css)" rel="external nofllow" rev="vote-for" target="_blank" href="http://wiki.greasespot.net/GM_addStyle">GM_addStyle( css ) api method</a>, or doesn't use <a title="Wikipedia: ECMAScript for XML" rel="external nofollow" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/ECMAScript_for_XML">E4X</a> which would save the author's time typing, and save the reader's time reading.
So the following are some tips when adding <a title="Wikipedia: Cascading Style Sheets" rel="external nofllow" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Css">CSS</a> to a webpage with <a title="Greasespot" rel="external nofllow" rev="vote-for" target="_blank" href="http://www.greasespot.net/">Greasemonkey</a>.
</p>
<h2>Tip 1: Use GM_addStyle( css )</h2>
<p>
Don't add multiple style attributes, don't use that code you have that adds a style tag to the page, use the built-in <a title="Greasemonkey Wiki: GM_addStyle(css)" rel="external nofllow" rev="vote-for" target="_blank" href="http://wiki.greasespot.net/GM_addStyle">GM_addStyle( css ) api method</a>; usually you should only need to call this method it once.
</p>
<h2>Tip 2: Use E4X</h2>
<p>
Typically when your adding <a title="Wikipedia: Cascading Style Sheets" rel="external nofllow" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Css">css</a> to a page, there are quite a few lines, and you don't want to escape every newline character, or join a bunch of partial strings together; the simplest way to go is to use <a title="Wikipedia: ECMAScript for XML" rel="external nofollow" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/ECMAScript_for_XML">E4X</a> like so:
</p>
<div class="code">GM_addStyle((&lt;&gt;&lt;![CDATA[<br>
&nbsp;&nbsp;&nbsp;body { color: white; background-color: black }<br>
&nbsp;&nbsp;&nbsp;img { border: 0 }<br>
&nbsp;&nbsp;&nbsp;.footer {width:875px;}<br>
]]&gt;&lt;/&gt;).toString());</div>
