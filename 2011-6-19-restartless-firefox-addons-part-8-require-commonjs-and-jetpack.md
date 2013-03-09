---
title: Restartless Firefox Add-ons, Part 8: Require, CommonJS, and Jetpack
short URL: http://r.evold.ca/rrffap8
tags: Firefox Add-ons, CommonJS, Jetpack
---
Jetpack is the future.  Give the old school add-ons up, it's over.  Because sooner or later everything will be possible with some <a target="_blank" title="CommonJS" rel="external" rev="vote-for" href="http://www.commonjs.org/">CommonJS</a> style module, which would mean you'd be a fool to ignore these modules.
</p>

<p>
At the moment, I see normal restartless add-ons as those that write their own bootstrap.js file, which is a method I've been trying to help people learn to do with this series, because I felt it would be a stepping stone to converting existing old school add-ons to Jetpacks which I needed, and that other developers might need as well.  Now, I can't explain why very well, but I feel that there is a freedom writing the bootstrap yourself which is very nice, and although it requires me to think about how to cleanup my code <strong>a lot more</strong>, that's something I needed.
</p>

<p>
There are serious drawbacks to building Jetpacks I think as well. Such as the file size of Jetpacks, a simple add-on which only uses a couple of the built-in modules is actually shipped with every module built-in to the add-on sdk, which means that anything you build will be at least ~250kb no matter what it does.  Now that just sucks for desktop users, but for mobile users it <strong>really</strong> sucks.
</p>

<p>
Now though, I'm starting to write some common includes for my restartless add-ons, and those which I contribute to, which I'd like to share, and I'm starting to see Jetpack modules/packages being written that I want to use in my restartless add-ons.  So I thought "it'd be nice to have a require() method for bootstrap.js", so I wrote a simple one:
</p>

<script src="https://gist.github.com/1034614.js?file=require.js"></script><link href="https://gist.github.com/assets/embed-0af287a4b5c981db301049e56f06e5d3.css" media="screen" rel="stylesheet"><div id="gist1034614" class="gist">
      <div class="gist-file">
        <div class="gist-data gist-syntax">



  <div class="file-data">
    <table class="lines highlight" cellpadding="0" cellspacing="0">
      <tbody><tr>
        <td class="line-numbers">
          <span class="line-number" id="file-require-js-L1" rel="file-require-js-L1">1</span>
          <span class="line-number" id="file-require-js-L2" rel="file-require-js-L2">2</span>
          <span class="line-number" id="file-require-js-L3" rel="file-require-js-L3">3</span>
          <span class="line-number" id="file-require-js-L4" rel="file-require-js-L4">4</span>
          <span class="line-number" id="file-require-js-L5" rel="file-require-js-L5">5</span>
          <span class="line-number" id="file-require-js-L6" rel="file-require-js-L6">6</span>
          <span class="line-number" id="file-require-js-L7" rel="file-require-js-L7">7</span>
          <span class="line-number" id="file-require-js-L8" rel="file-require-js-L8">8</span>
          <span class="line-number" id="file-require-js-L9" rel="file-require-js-L9">9</span>
          <span class="line-number" id="file-require-js-L10" rel="file-require-js-L10">10</span>
          <span class="line-number" id="file-require-js-L11" rel="file-require-js-L11">11</span>
          <span class="line-number" id="file-require-js-L12" rel="file-require-js-L12">12</span>
          <span class="line-number" id="file-require-js-L13" rel="file-require-js-L13">13</span>
          <span class="line-number" id="file-require-js-L14" rel="file-require-js-L14">14</span>
          <span class="line-number" id="file-require-js-L15" rel="file-require-js-L15">15</span>
          <span class="line-number" id="file-require-js-L16" rel="file-require-js-L16">16</span>
          <span class="line-number" id="file-require-js-L17" rel="file-require-js-L17">17</span>
          <span class="line-number" id="file-require-js-L18" rel="file-require-js-L18">18</span>
          <span class="line-number" id="file-require-js-L19" rel="file-require-js-L19">19</span>
          <span class="line-number" id="file-require-js-L20" rel="file-require-js-L20">20</span>
          <span class="line-number" id="file-require-js-L21" rel="file-require-js-L21">21</span>
          <span class="line-number" id="file-require-js-L22" rel="file-require-js-L22">22</span>
          <span class="line-number" id="file-require-js-L23" rel="file-require-js-L23">23</span>
          <span class="line-number" id="file-require-js-L24" rel="file-require-js-L24">24</span>
          <span class="line-number" id="file-require-js-L25" rel="file-require-js-L25">25</span>
        </td>
        <td class="line-data">
          <pre class="line-pre"><div class="line" id="file-require-js-LC1"><span class="cm">/* Imports a commonjs style javascript file with loadSubScrpt</span></div><div class="line" id="file-require-js-LC2"><span class="cm"> * By Erik Vold &lt;erikvvold@gmail.com&gt; http://erikvold.com/</span></div><div class="line" id="file-require-js-LC3"><span class="cm"> * </span></div><div class="line" id="file-require-js-LC4"><span class="cm"> * @param src (String)</span></div><div class="line" id="file-require-js-LC5"><span class="cm"> * The url of a javascript file.</span></div><div class="line" id="file-require-js-LC6"><span class="cm"> */</span></div><div class="line" id="file-require-js-LC7"><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">global</span><span class="p">)</span> <span class="p">{</span></div><div class="line" id="file-require-js-LC8">  <span class="kd">var</span> <span class="nx">modules</span> <span class="o">=</span> <span class="p">{};</span></div><div class="line" id="file-require-js-LC9">  <span class="nx">global</span><span class="p">.</span><span class="nx">require</span> <span class="o">=</span> <span class="kd">function</span> <span class="nx">require</span><span class="p">(</span><span class="nx">src</span><span class="p">)</span> <span class="p">{</span></div><div class="line" id="file-require-js-LC10">    <span class="k">if</span> <span class="p">(</span><span class="nx">modules</span><span class="p">[</span><span class="nx">src</span><span class="p">])</span> <span class="k">return</span> <span class="nx">modules</span><span class="p">[</span><span class="nx">src</span><span class="p">];</span></div><div class="line" id="file-require-js-LC11">    <span class="kd">var</span> <span class="nx">scope</span> <span class="o">=</span> <span class="p">{</span><span class="nx">require</span><span class="o">:</span> <span class="nx">global</span><span class="p">.</span><span class="nx">require</span><span class="p">,</span> <span class="nx">exports</span><span class="o">:</span> <span class="p">{}};</span></div><div class="line" id="file-require-js-LC12">    <span class="kd">var</span> <span class="nx">tools</span> <span class="o">=</span> <span class="p">{};</span></div><div class="line" id="file-require-js-LC13">    <span class="nx">Components</span><span class="p">.</span><span class="nx">utils</span><span class="p">.</span><span class="kr">import</span><span class="p">(</span><span class="s2">"resource://gre/modules/Services.jsm"</span><span class="p">,</span> <span class="nx">tools</span><span class="p">);</span></div><div class="line" id="file-require-js-LC14">    <span class="kd">var</span> <span class="nx">baseURI</span> <span class="o">=</span> <span class="nx">tools</span><span class="p">.</span><span class="nx">Services</span><span class="p">.</span><span class="nx">io</span><span class="p">.</span><span class="nx">newURI</span><span class="p">(</span><span class="nx">__SCRIPT_URI_SPEC__</span><span class="p">,</span> <span class="kc">null</span><span class="p">,</span> <span class="kc">null</span><span class="p">);</span></div><div class="line" id="file-require-js-LC15">    <span class="k">try</span> <span class="p">{</span></div><div class="line" id="file-require-js-LC16">      <span class="kd">var</span> <span class="nx">uri</span> <span class="o">=</span> <span class="nx">tools</span><span class="p">.</span><span class="nx">Services</span><span class="p">.</span><span class="nx">io</span><span class="p">.</span><span class="nx">newURI</span><span class="p">(</span></div><div class="line" id="file-require-js-LC17">          <span class="s2">"packages/"</span> <span class="o">+</span> <span class="nx">src</span> <span class="o">+</span> <span class="s2">".js"</span><span class="p">,</span> <span class="kc">null</span><span class="p">,</span> <span class="nx">baseURI</span><span class="p">);</span></div><div class="line" id="file-require-js-LC18">      <span class="nx">tools</span><span class="p">.</span><span class="nx">Services</span><span class="p">.</span><span class="nx">scriptloader</span><span class="p">.</span><span class="nx">loadSubScript</span><span class="p">(</span><span class="nx">uri</span><span class="p">.</span><span class="nx">spec</span><span class="p">,</span> <span class="nx">scope</span><span class="p">);</span></div><div class="line" id="file-require-js-LC19">    <span class="p">}</span> <span class="k">catch</span> <span class="p">(</span><span class="nx">e</span><span class="p">)</span> <span class="p">{</span></div><div class="line" id="file-require-js-LC20">      <span class="kd">var</span> <span class="nx">uri</span> <span class="o">=</span> <span class="nx">tools</span><span class="p">.</span><span class="nx">Services</span><span class="p">.</span><span class="nx">io</span><span class="p">.</span><span class="nx">newURI</span><span class="p">(</span><span class="nx">src</span><span class="p">,</span> <span class="kc">null</span><span class="p">,</span> <span class="nx">baseURI</span><span class="p">);</span></div><div class="line" id="file-require-js-LC21">      <span class="nx">tools</span><span class="p">.</span><span class="nx">Services</span><span class="p">.</span><span class="nx">scriptloader</span><span class="p">.</span><span class="nx">loadSubScript</span><span class="p">(</span><span class="nx">uri</span><span class="p">.</span><span class="nx">spec</span><span class="p">,</span> <span class="nx">scope</span><span class="p">);</span></div><div class="line" id="file-require-js-LC22">    <span class="p">}</span></div><div class="line" id="file-require-js-LC23">    <span class="k">return</span> <span class="nx">modules</span><span class="p">[</span><span class="nx">src</span><span class="p">]</span> <span class="o">=</span> <span class="nx">scope</span><span class="p">.</span><span class="nx">exports</span><span class="p">;</span></div><div class="line" id="file-require-js-LC24">  <span class="p">}</span></div><div class="line" id="file-require-js-LC25"><span class="p">})(</span><span class="k">this</span><span class="p">);</span></div></pre>
        </td>
      </tr>
    </tbody></table>
  </div>

        </div>

        <div class="gist-meta">
          <a href="https://gist.github.com/erikvold/1034614/raw/1d4822c904eb3506ae44dd5ee1ca00d58a17e2b9/require.js" style="float:right">view raw</a>
          <a href="https://gist.github.com/erikvold/1034614#file-require-js" style="float:right; margin-right:10px; color:#666;">require.js</a>
          <a href="https://gist.github.com/erikvold/1034614">This Gist</a> brought to you by <a href="http://github.com">GitHub</a>.
        </div>
      </div>
</div>


<p>If you copy &amp; paste <a target="_blank" rel="external nofollow" href="https://gist.github.com/1034614">this code</a> into your bootstrap.js file somewhere near the top of the file then you will have a require() method which will look in your add-on's "packages" folder for a ".js" file with the name you provide, if a module is not found there then the name is assumed to be a relative url.</p>

<p>
With that you can start writing <a target="_blank" title="CommonJS Modules" rel="external" rev="vote-for" href="http://www.commonjs.org/specs/modules/1.0/">CommonJS modules</a> which can be used by Jetpacks and even NodeJS and the like, as well as for your lean mean restartless add-ons.  You can even start using Jetpack modules and other CommonJS style modules in your restartless add-on as well!
</p>

<p>
As always you can checkout <a title="Restartless Restart - A Firefox extension" rel="external nofollow" target="_blank" href="https://github.com/erikvold/restartless-restart-ffext">Restartless Restart</a> as a example.
</p>
