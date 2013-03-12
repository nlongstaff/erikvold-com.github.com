---
title: Using Web Workers Today
short URL: http://r.evold.ca/jscbww
tags: UX, Javascript, Programming, WebDev
---
I did a little reading on <a title="Web Workers Specification - WHATWG" rel="external" target="_blank" rev="vote-for" href="http://www.whatwg.org/specs/web-workers/current-work/">Web Workers</a> a few months ago, and I recently used them in a little test I was asked to perform, so I thought I would share what I've discovered since I don't see much in Google search results about how to use Web Workers in a cross browser fashion with graceful degradation.
</p>

<h2>Web Workers</h2>
<p>
For those of you that do not know what Web Workers are I suggest you read the <a title="Web Workers Specification - WHATWG" rel="external" target="_blank" rev="vote-for" href="http://www.whatwg.org/specs/web-workers/current-work/">Web Workers Draft Recommendation</a>, but in brief they provide web developers with the ability to create thread-like operations.</p>

<p>
This is obviously useful for long operations. The standard way of dealing with laborious tasks like these in the past was to split up the work with multiple <a title="setTimeout - MDC" rel="external nofollow" rev="vote-for" target="_blank" href="https://developer.mozilla.org/en/DOM/window.setTimeout">setTimeout()</a> calls.
</p>

<h2>setTimeout</h2>

<p>
Before Web Workers, <a title="setTimeout - MDC" rel="external nofollow" rev="vote-for" target="_blank" href="https://developer.mozilla.org/en/DOM/window.setTimeout">setTimeout()</a> had to be used to split up long operations in to multiple small operations, because you only had a single thread, so this had to be done in order to avoid having an unresponsive UI or triggering a <a title="Unresponsive Script Warning" rel="external nofollow" rev="vote-for" target="_blank" href="http://kb.mozillazine.org/Unresponsive_Script_Warning">unresponsive script warning</a>.
</p>

<h2>Current Browser Support For Web Workers</h2>
<p>
Currently the latest versions of <a title="Firefox" rel="external nofollow" rev="vote-for" href="www.mozilla.com/firefox/">Firefox</a>, Chrome, and Safari all support Web Workers; IE and Opera do not support Web Workers.
</p>

<p>
So how do you detect if a browser supports Web Workers programmatically? this is how:
</p><div class="code">if( Worker /*check for support*/ )<br>
  // Web Workers are supported<br>
else<br>
  // Web Workers are not supported</div>
<p></p>

<h3>Minor Note For Safari</h3>

<p>
While Safari supports Web Workers it requires that strings be used when passing messages, which is something that Firefox and Chrome do not require. Firefox and Chrome both stringify anything not already a string that is crossing the bridge to or from a Web Worker, but Safari does not do this, so you must. This is a simple thing to do, but one that you must remember, always use <a title="JSON - MDC" rel="external" rev="vote-for" target="_blank" href="https://developer.mozilla.org/en/JSON">the JSON object</a> to JSON.stringify when sending a message and JSON.parse when receiving a message (if web workers are supported, then so will the JSON object be).
</p>

<h2>Supporting Browsers That Do Not Support Web Workers</h2>
<p>
The biggest hurdle for most to implement Web Workers today is the fact that not all browsers support them, but the fact is that it is simple to degrade gracefully, thus allowing those users that are using browsers that support web workers to start reaping the rewards, and allowing you to improve your site and be prepared for when IE and Opera finally come around.
</p>
<p>
So what is the best way to handle the browsers that do not support Web Workers? well I see two options:
</p><ol>
<li>Maintain a secondary script to be used when Web Workers cannot be, and add it to the page by creating a script element and appending it to the document.body.</li>
<li>Make the Web Worker friendly to being used in a window scope instead of a Web Worker's scope so that it can be simply added to page like I describe in option 1.</li>
</ol>
<p></p>
<p>
<b>Option 2 will be the better approach in most cases I suspect, because it means that two separate files with two slightly different methods of achieving the same task do not need to be maintained.</b> In order to implement option 2 two there are some things to consider:
</p><ul>
<li>
You cannot use functions like postMessage, onmessage, or importScripts while in the window scope.
</li>
<li>
You will need to split the work up with setTimeout (which is available in the Web Worker scope as well) to avoid an unresponsive UI and unresponsive script warnings.
</li>
<li>
You should assume that your Web Worker will be used in the window scope, so do not pollute your global scope.
</li>
</ul>
<p></p>
<p>
There are a couple of ways to determine if you are not in a Web Worker's scope, as to avoid using the postMessage, onmessage, and importScripts functions (which are available to Web Workers) when your script is run in the window scope (<a title="window.postMessage - MDC" rel="external nofollow" target="_blank" href="https://developer.mozilla.org/en/DOM/window.postMessage">postMessage</a> has another purpose in the window scope). The first method is this:</p>
<div class="code">if(typeof importScripts == "function") {<br>
 // web worker scope<br>
}<br>
else {<br>
  // not web worker scope, assume window scope<br>
}</div><p>
The other method is to check if you are in the window scope:</p>
<div class="code">if(typeof window != "undefined") {<br>
  // window scope<br>
}<br>
else {<br>
  // not window scope, assume web worker scope<br>
}</div><p>
Or, combining the two methods above:</p>
<div class="code">if(typeof window == "undefined" &amp;&amp; typeof importScripts == "function") {<br>
  // web worker scope<br>
}<br>
else {<br>
  // another scope<br>
}</div><p>
These methods will allow us to avoid using postMessage, onmessage, or other methods we use while in the scope of a Web Worker.
</p>
<p>
To avoid polluting the global space normal tactics apply, I would simply suggest wrapping all of the code in an anonymous automatically executed function, like so:</p>
<div class="code">(function(){<br>
  // this is an anonymous automatically executed function<br>
})()</div>
<p>
Putting these methods together, we would get web workers like so:</p>
<div class="code">(function(){<br>
  var winScope = true;<br>
  if(typeof window == "undefined" &amp;&amp; typeof importScripts == "function") {<br>
    // web worker scope<br>
    winScope = false;<br>
  }<br>
  <br>
  if(!winScope) {<br>
    onmessage = function() {<br>
      postMessage("blah");<br>
    }<br>
  }<br>
  else {<br>
    alert("blah");<br>
  }<br>
})()</div><p>
Except that real Web Workers would do interesting things, and use setTimeout.
</p>
