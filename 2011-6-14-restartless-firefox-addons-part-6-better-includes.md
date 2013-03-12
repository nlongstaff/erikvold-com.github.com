---
title: Restartless Firefox Add-ons, Part 6: Better Includes
short URL: http://r.evold.ca/rrffap6
tags: Firefox Add-ons, Firefox
---
I just wanted to make a quick update on <a title="Restartless Firefox Add-ons Part 2: Includes" href="http://r.evold.ca/rrffap2">part 2: includes</a>, because I've written a better include() function. This one will allow you to include files at any point in your bootstrap.js file; so you no longer need to wait for the startup function to run, and you no longer need to use the AddonManager.jsm file. This is just much more simple.
</p>

<script src="https://gist.github.com/1024242.js?file=include.js"></script><link href="https://gist.github.com/assets/embed-0af287a4b5c981db301049e56f06e5d3.css" media="screen" rel="stylesheet"><div id="gist1024242" class="gist">
      <div class="gist-file">
        <div class="gist-data gist-syntax">



  <div class="file-data">
    <table class="lines highlight" cellpadding="0" cellspacing="0">
      <tbody><tr>
        <td class="line-numbers">
          <span class="line-number" id="file-include-js-L1" rel="file-include-js-L1">1</span>
          <span class="line-number" id="file-include-js-L2" rel="file-include-js-L2">2</span>
          <span class="line-number" id="file-include-js-L3" rel="file-include-js-L3">3</span>
          <span class="line-number" id="file-include-js-L4" rel="file-include-js-L4">4</span>
          <span class="line-number" id="file-include-js-L5" rel="file-include-js-L5">5</span>
          <span class="line-number" id="file-include-js-L6" rel="file-include-js-L6">6</span>
          <span class="line-number" id="file-include-js-L7" rel="file-include-js-L7">7</span>
          <span class="line-number" id="file-include-js-L8" rel="file-include-js-L8">8</span>
          <span class="line-number" id="file-include-js-L9" rel="file-include-js-L9">9</span>
          <span class="line-number" id="file-include-js-L10" rel="file-include-js-L10">10</span>
          <span class="line-number" id="file-include-js-L11" rel="file-include-js-L11">11</span>
          <span class="line-number" id="file-include-js-L12" rel="file-include-js-L12">12</span>
          <span class="line-number" id="file-include-js-L13" rel="file-include-js-L13">13</span>
        </td>
        <td class="line-data">
          <pre class="line-pre"><div class="line" id="file-include-js-LC1"><span class="cm">/* Includes a javascript file with loadSubScript</span></div><div class="line" id="file-include-js-LC2"><span class="cm"> * By Erik Vold &lt;erikvvold@gmail.com&gt; http://erikvold.com/</span></div><div class="line" id="file-include-js-LC3"><span class="cm"> *</span></div><div class="line" id="file-include-js-LC4"><span class="cm"> * @param src (String)</span></div><div class="line" id="file-include-js-LC5"><span class="cm"> * The url of a javascript file to include.</span></div><div class="line" id="file-include-js-LC6"><span class="cm"> */</span></div><div class="line" id="file-include-js-LC7"><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">global</span><span class="p">)</span> <span class="nx">global</span><span class="p">.</span><span class="nx">include</span> <span class="o">=</span> <span class="kd">function</span> <span class="nx">include</span><span class="p">(</span><span class="nx">src</span><span class="p">)</span> <span class="p">{</span></div><div class="line" id="file-include-js-LC8">  <span class="kd">var</span> <span class="nx">o</span> <span class="o">=</span> <span class="p">{};</span></div><div class="line" id="file-include-js-LC9">  <span class="nx">Components</span><span class="p">.</span><span class="nx">utils</span><span class="p">.</span><span class="kr">import</span><span class="p">(</span><span class="s2">"resource://gre/modules/Services.jsm"</span><span class="p">,</span> <span class="nx">o</span><span class="p">);</span></div><div class="line" id="file-include-js-LC10">  <span class="kd">var</span> <span class="nx">uri</span> <span class="o">=</span> <span class="nx">o</span><span class="p">.</span><span class="nx">Services</span><span class="p">.</span><span class="nx">io</span><span class="p">.</span><span class="nx">newURI</span><span class="p">(</span></div><div class="line" id="file-include-js-LC11">      <span class="nx">src</span><span class="p">,</span> <span class="kc">null</span><span class="p">,</span> <span class="nx">o</span><span class="p">.</span><span class="nx">Services</span><span class="p">.</span><span class="nx">io</span><span class="p">.</span><span class="nx">newURI</span><span class="p">(</span><span class="nx">__SCRIPT_URI_SPEC__</span><span class="p">,</span> <span class="kc">null</span><span class="p">,</span> <span class="kc">null</span><span class="p">));</span></div><div class="line" id="file-include-js-LC12">  <span class="nx">o</span><span class="p">.</span><span class="nx">Services</span><span class="p">.</span><span class="nx">scriptloader</span><span class="p">.</span><span class="nx">loadSubScript</span><span class="p">(</span><span class="nx">uri</span><span class="p">.</span><span class="nx">spec</span><span class="p">,</span> <span class="nx">global</span><span class="p">);</span></div><div class="line" id="file-include-js-LC13"><span class="p">})(</span><span class="k">this</span><span class="p">);</span></div></pre>
        </td>
      </tr>
    </tbody></table>
  </div>

        </div>

        <div class="gist-meta">
          <a href="https://gist.github.com/erikvold/1024242/raw/7f41d5051ac1821f993cee0cc8cd73c16036c9c2/include.js" style="float:right">view raw</a>
          <a href="https://gist.github.com/erikvold/1024242#file-include-js" style="float:right; margin-right:10px; color:#666;">include.js</a>
          <a href="https://gist.github.com/erikvold/1024242">This Gist</a> brought to you by <a href="http://github.com">GitHub</a>.
        </div>
      </div>
</div>

<noscript>
<div class="code">/* Includes a javascript file with loadSubScript<br />
*<br />
* @param src (String)<br />
* The url of a javascript file to include.<br />
*/<br />
(function(global) global.include = function include(src) {<br />
  var o = {};<br />
  Components.utils.import("<a target="_blank" href="resource://gre/modules/Services.jsm">resource://gre/modules/Services.jsm</a>", o);<br />
  var uri = o.Services.io.newURI(<br />
      src, null, o.Services.io.newURI(__SCRIPT_URI_SPEC__, null, null));<br />
  o.Services.scriptloader.loadSubScript(uri.spec, global);<br />
})(this);</div>
</noscript>

<p>
Just copy &amp; paste the script above into your bootstrap.js file and then any code executed after it can use it immediately, <strong>and with relative urls</strong>. This is why you no longer need to use the AddonManager.jsm file, and that is why you no longer need to wait to use the startup method before including helper files.
</p>
