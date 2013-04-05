---
title: How to Create an HTML Tag in JavaScript on the Fly
tags: Javascript, HTML, Programming
---
If you want to create an html tag in JavaScript on the fly, the good way (ie: without using document.write and innerHTML). Then this is how you do it, use:
<div class="code">document.createElement("tagName");</div>
Where 'tagName' is the tag name (for example: a, script, style, p, h1, h2, h3, input, select, etc...). This will create a tag node that you can then attach to the DOM tree of your document with the following functions:

- [appendChild](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#method-appendChild)()
- [insertBefore](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#method-insertBefore)()
- [replaceChild](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#method-replaceChild)()
