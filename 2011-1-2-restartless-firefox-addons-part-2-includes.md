---
title: Restartless Firefox Add-ons, Part 2: Includes
short URL: http://r.evold.ca/rrffap2
tags: Firefox Add-ons, Programming, Firefox
---
Today I'm going to write about including files into your bootstrap.js file's scope. There are a few different types of files that you'll want to include, and I'm only going to talk about three of them today, importing javascript modules provided by Firefox or other extensions, and including (using loadSubScript) files packaged with your add-on, or any other.
</p>
<h2>Importing Modules</h2>
<p>
This is pretty simple, <em>Components</em> is available, so <em>Components.utils.import</em> is available. So import javascript modules like so:
</p>
<div class="code">Components.utils.import("<a target="_blank" href="resource://gre/modules/Services.jsm">resource://gre/modules/Services.jsm</a>");</div>
<p>
Note: I highly recommend reviewing the <a title="Services.jsm - MDC" target="_blank" rel="external" rev="vote-for" href="https://developer.mozilla.org/en/JavaScript_code_modules/Services.jsm">Services.jsm</a> module, it's a handy one.
</p>
<h2>Includes</h2>
<p>
There are many reasons why you'd want to access other files packaged with your add-on, one of them being if your bootstrap.js file starts getting large then you'll probably want to break that code up in to multiple files and include them in the bootstrap.js file. Another would be if your add-on needs to get the file location of a image or some other asset packaged with the add-on.
</p>
<p>
In order to figure out the location of files packaged with an add-on, the AddonManager.jsm &amp; Services.jsm module will be needed, import it with the following code:
</p>
<div class="code">Components.utils.import("<a target="_blank" href="resource://gre/modules/Services.jsm">resource://gre/modules/Services.jsm</a>");<br>
Components.utils.import("<a target="_blank" href="resource://gre/modules/AddonManager.jsm">resource://gre/modules/AddonManager.jsm</a>");</div>
<p>
Then add the following implementation of a <em>include</em> function:
</p>
<div class="code">/* Includes a javascript file with loadSubScript <br>
 * <br>
 * @param src (String)<br>
 *                 The url of a javascript file to include.<br>
 */<br>
(function(global) global.include = function include(src) (<br>
    Services.scriptloader.loadSubScript(src, global)))(this);</div>
<p>
Now in you'll want to call <a title="AddonManager.getAddonByID() - MDC" rel="external" target="_blank" href="https://developer.mozilla.org/en/Addons/Add-on_Manager/AddonManager#getAddonByID()"><em>AddonManager.getAddonByID()</em></a> with the add-on's id, which you can get from the bootstrap.js file's <em>startup</em> method's <em>data</em> param, like so:
</p>
<div class="code">var img;<br>
function startup(data) AddonManager.getAddonByID(data.id, function(addon) {<br>
  // Include some utility functions<br>
  include(addon.getResourceURI("includes/utils.js").spec);<br>
  // Remember some image's url<br>
  img = addon.getResourceURI("images/star.png").spec;<br>
});</div>
<p>
I should be blogging about some includes which'll make developing restartless add-ons much easier in following posts!
</p>
