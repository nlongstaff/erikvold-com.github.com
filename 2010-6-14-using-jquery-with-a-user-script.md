---
title: User Script Tip: Using jQuery
short URL: http://r.evold.ca/jquery4us
tags: UserScripts, Troubleshooting, Greasemonkey, Programming
---
A very common question that I see asked on <a title="StackOverflow" rel="external" rev="vote-for" target="_blank" href="http://stackoverflow.com/">stackoverflow.com</a>, the <a title="greasemonkey-users" rel="external" rev="vote-for" target="_blank" href="http://groups.google.com/group/greasemonkey-users">greasemonkey-users mailing list</a>, and in #greasemonkey on freenode, is <a title="Third-Party Libraries" rel="external" rev="vote-for" target="_blank" href="http://wiki.greasespot.net/Third-Party_Libraries">how to use third party libraries with a user script</a>.
</p>

<p>
The common response is to use <a title="@require - Metadata block - Greasemonkey" rel="external" rev="vote-for" target="_blank" href="http://wiki.greasespot.net/Metadata_Block#.40require">@require</a>, but these days people want their user scripts to work on Google Chrome too, and unfortunately <a title="Google Chrome User Scripts" rel="external nofollow" rev="vote-against" target="_blank" href="http://www.chromium.org/developers/design-documents/user-scripts">Google Chrome user scripts</a> do not support a lot of <a title="Metadata block - Greasemonkey" rel="external" rev="vote-for" target="_blank" href="http://wiki.greasespot.net/Metadata_Block">the Greasemonkey metadata block</a>, including @require.. so another method is required.
</p>
<h2>Cross Browser Solutions</h2>
<h3>Use script element &amp; setTimeouts</h3>
<p>
One method that <a rel="external nofollow" rev="vote-against" target="_blank" href="http://joanpiedra.com/jquery/greasemonkey/">has been mentioned elsewhere</a> is to create a script element and add it to the page, and use setTimeout's to wait until the third party js, in this example jQuery, is loaded. The example in the link I provided is for Greasemonkey, but with little effort it can be made to work with Google Chrome.
</p>

<h3>Use script element &amp; associated onload event</h3>
<p>
This method creates script element for jQuery (or some other third party script), and appends it to the body element, and listens to the load event to figure out when the library is loaded and ready to be used.
</p>

<p>
Google Chrome does not allow user scripts to access javascript objects in the page scope from the user script's scope, so in order to use jQuery at all on Google Chrome you must load jQuery into the page scope and inject your script into the page scope. So this is what my example below does essentially, more specifically it stringifys a callback function which is called when jQuery is done loading.
</p>

<h4>Example</h4>
<script src="http://gist.github.com/437513.js"></script><link href="https://gist.github.com/assets/embed-0af287a4b5c981db301049e56f06e5d3.css" media="screen" rel="stylesheet"><div id="gist437513" class="gist">
      <div class="gist-file">
        <div class="gist-data gist-syntax">



  <div class="file-data">
    <table class="lines highlight" cellpadding="0" cellspacing="0">
      <tbody><tr>
        <td class="line-numbers">
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L1" rel="file-jqueryforchromeexample-user-js-L1">1</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L2" rel="file-jqueryforchromeexample-user-js-L2">2</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L3" rel="file-jqueryforchromeexample-user-js-L3">3</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L4" rel="file-jqueryforchromeexample-user-js-L4">4</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L5" rel="file-jqueryforchromeexample-user-js-L5">5</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L6" rel="file-jqueryforchromeexample-user-js-L6">6</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L7" rel="file-jqueryforchromeexample-user-js-L7">7</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L8" rel="file-jqueryforchromeexample-user-js-L8">8</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L9" rel="file-jqueryforchromeexample-user-js-L9">9</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L10" rel="file-jqueryforchromeexample-user-js-L10">10</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L11" rel="file-jqueryforchromeexample-user-js-L11">11</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L12" rel="file-jqueryforchromeexample-user-js-L12">12</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L13" rel="file-jqueryforchromeexample-user-js-L13">13</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L14" rel="file-jqueryforchromeexample-user-js-L14">14</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L15" rel="file-jqueryforchromeexample-user-js-L15">15</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L16" rel="file-jqueryforchromeexample-user-js-L16">16</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L17" rel="file-jqueryforchromeexample-user-js-L17">17</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L18" rel="file-jqueryforchromeexample-user-js-L18">18</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L19" rel="file-jqueryforchromeexample-user-js-L19">19</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L20" rel="file-jqueryforchromeexample-user-js-L20">20</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L21" rel="file-jqueryforchromeexample-user-js-L21">21</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L22" rel="file-jqueryforchromeexample-user-js-L22">22</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L23" rel="file-jqueryforchromeexample-user-js-L23">23</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L24" rel="file-jqueryforchromeexample-user-js-L24">24</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L25" rel="file-jqueryforchromeexample-user-js-L25">25</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L26" rel="file-jqueryforchromeexample-user-js-L26">26</span>
          <span class="line-number" id="file-jqueryforchromeexample-user-js-L27" rel="file-jqueryforchromeexample-user-js-L27">27</span>
        </td>
        <td class="line-data">
          <pre class="line-pre"><div class="line" id="file-jqueryforchromeexample-user-js-LC1"><span class="c1">// ==UserScript==</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC2"><span class="c1">// @name         jQuery For Chrome (A Cross Browser Example)</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC3"><span class="c1">// @namespace    jQueryForChromeExample</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC4"><span class="c1">// @include      *</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC5"><span class="c1">// @author       Erik Vergobbi Vold</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC6"><span class="c1">// @description  This userscript is meant to be an example on how to use jQuery in a userscript on Google Chrome.</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC7"><span class="c1">// ==/UserScript==</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC8">&nbsp;</div><div class="line" id="file-jqueryforchromeexample-user-js-LC9"><span class="c1">// a function that loads jQuery and calls a callback function when jQuery has finished loading</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC10"><span class="kd">function</span> <span class="nx">addJQuery</span><span class="p">(</span><span class="nx">callback</span><span class="p">)</span> <span class="p">{</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC11">  <span class="kd">var</span> <span class="nx">script</span> <span class="o">=</span> <span class="nb">document</span><span class="p">.</span><span class="nx">createElement</span><span class="p">(</span><span class="s2">"script"</span><span class="p">);</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC12">  <span class="nx">script</span><span class="p">.</span><span class="nx">setAttribute</span><span class="p">(</span><span class="s2">"src"</span><span class="p">,</span> <span class="s2">"http://ajax.googleapis.com/ajax/libs/jquery/1.4.2/jquery.min.js"</span><span class="p">);</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC13">  <span class="nx">script</span><span class="p">.</span><span class="nx">addEventListener</span><span class="p">(</span><span class="s1">'load'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC14">    <span class="kd">var</span> <span class="nx">script</span> <span class="o">=</span> <span class="nb">document</span><span class="p">.</span><span class="nx">createElement</span><span class="p">(</span><span class="s2">"script"</span><span class="p">);</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC15">    <span class="nx">script</span><span class="p">.</span><span class="nx">textContent</span> <span class="o">=</span> <span class="s2">"("</span> <span class="o">+</span> <span class="nx">callback</span><span class="p">.</span><span class="nx">toString</span><span class="p">()</span> <span class="o">+</span> <span class="s2">")();"</span><span class="p">;</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC16">    <span class="nb">document</span><span class="p">.</span><span class="nx">body</span><span class="p">.</span><span class="nx">appendChild</span><span class="p">(</span><span class="nx">script</span><span class="p">);</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC17">  <span class="p">},</span> <span class="kc">false</span><span class="p">);</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC18">  <span class="nb">document</span><span class="p">.</span><span class="nx">body</span><span class="p">.</span><span class="nx">appendChild</span><span class="p">(</span><span class="nx">script</span><span class="p">);</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC19"><span class="p">}</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC20">&nbsp;</div><div class="line" id="file-jqueryforchromeexample-user-js-LC21"><span class="c1">// the guts of this userscript</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC22"><span class="kd">function</span> <span class="nx">main</span><span class="p">()</span> <span class="p">{</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC23">  <span class="nx">alert</span><span class="p">(</span><span class="s2">"There are "</span> <span class="o">+</span> <span class="nx">$</span><span class="p">(</span><span class="s1">'a'</span><span class="p">).</span><span class="nx">length</span> <span class="o">+</span> <span class="s2">" links on this page."</span><span class="p">);</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC24"><span class="p">}</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC25">&nbsp;</div><div class="line" id="file-jqueryforchromeexample-user-js-LC26"><span class="c1">// load jQuery and execute the main function</span></div><div class="line" id="file-jqueryforchromeexample-user-js-LC27"><span class="nx">addJQuery</span><span class="p">(</span><span class="nx">main</span><span class="p">);</span></div></pre>
        </td>
      </tr>
    </tbody></table>
  </div>

        </div>

        <div class="gist-meta">
          <a href="https://gist.github.com/erikvold/437513/raw/cf83bfc4a2031ae17c8a480dc010ee19e04cf141/jQueryForChromeExample.user.js" style="float:right">view raw</a>
          <a href="https://gist.github.com/erikvold/437513#file-jqueryforchromeexample-user-js" style="float:right; margin-right:10px; color:#666;">jQueryForChromeExample.user.js</a>
          <a href="https://gist.github.com/erikvold/437513">This Gist</a> brought to you by <a href="http://github.com">GitHub</a>.
        </div>
