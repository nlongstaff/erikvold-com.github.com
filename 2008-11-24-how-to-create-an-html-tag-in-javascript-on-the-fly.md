---
title: How to Create an HTML Tag in JavaScript on the Fly
tags: Javascript, HTML, Programming
---
<p>If you want to create an html tag in JavaScript on the fly, the good way (ie: without using document.write and innerHTML). Then this is how you do it, use:</p>
<div class="code">document.createElement("tagName");</div>
<p>Where 'tagName' is the tag name (for example: a, script, style, p, h1, h2, h3, input, select, etc...). This will create a tag node that you can then attach to the DOM tree of your document with the following functions:
</p>
<ul>
<li><a title="DOM Level 1 - Method appendChild" rev="vote-for" target="_blank" href="http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#method-appendChild">appendChild</a>()</li>
<li><a title="DOM Level 1 - Method appendChild" rev="vote-for" target="_blank" href="http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#method-insertBefore">insertBefore</a>()</li>
<li><a title="DOM Level 1 - Method appendChild" rev="vote-for" target="_blank" href="http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#method-replaceChild">replaceChild</a>()</li>
