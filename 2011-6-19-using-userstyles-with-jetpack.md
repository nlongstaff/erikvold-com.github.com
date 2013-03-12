---
title: Using UserStyles with Jetpack
short URL: http://r.evold.ca/userstylesjp
tags: UserStyles, Firefox Add-ons, CSS, Jetpack
---
This morning I created a Jetpack module which makes it dead simple to include userstyles in a addon.
</p>
<h2>How to use</h2>
<p>
Here's a example:
</p>

<script src="https://gist.github.com/1033799.js?file=black-google.jetpack.example.js"></script><link href="https://gist.github.com/assets/embed-0af287a4b5c981db301049e56f06e5d3.css" media="screen" rel="stylesheet"><div id="gist1033799" class="gist">
      <div class="gist-file">
        <div class="gist-data gist-syntax">



  <div class="file-data">
    <table class="lines highlight" cellpadding="0" cellspacing="0">
      <tbody><tr>
        <td class="line-numbers">
          <span class="line-number" id="file-black-google-jetpack-example-js-L1" rel="file-black-google-jetpack-example-js-L1">1</span>
          <span class="line-number" id="file-black-google-jetpack-example-js-L2" rel="file-black-google-jetpack-example-js-L2">2</span>
          <span class="line-number" id="file-black-google-jetpack-example-js-L3" rel="file-black-google-jetpack-example-js-L3">3</span>
          <span class="line-number" id="file-black-google-jetpack-example-js-L4" rel="file-black-google-jetpack-example-js-L4">4</span>
          <span class="line-number" id="file-black-google-jetpack-example-js-L5" rel="file-black-google-jetpack-example-js-L5">5</span>
          <span class="line-number" id="file-black-google-jetpack-example-js-L6" rel="file-black-google-jetpack-example-js-L6">6</span>
          <span class="line-number" id="file-black-google-jetpack-example-js-L7" rel="file-black-google-jetpack-example-js-L7">7</span>
          <span class="line-number" id="file-black-google-jetpack-example-js-L8" rel="file-black-google-jetpack-example-js-L8">8</span>
        </td>
        <td class="line-data">
          <pre class="line-pre"><div class="line" id="file-black-google-jetpack-example-js-LC1">&nbsp;</div><div class="line" id="file-black-google-jetpack-example-js-LC2"><span class="kd">var</span> <span class="nx">self</span> <span class="o">=</span> <span class="nx">require</span><span class="p">(</span><span class="s2">"self"</span><span class="p">);</span></div><div class="line" id="file-black-google-jetpack-example-js-LC3"><span class="kd">var</span> <span class="nx">us</span> <span class="o">=</span> <span class="nx">require</span><span class="p">(</span><span class="s2">"userstyles"</span><span class="p">);</span></div><div class="line" id="file-black-google-jetpack-example-js-LC4">&nbsp;</div><div class="line" id="file-black-google-jetpack-example-js-LC5"><span class="nx">exports</span><span class="p">.</span><span class="nx">main</span> <span class="o">=</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span></div><div class="line" id="file-black-google-jetpack-example-js-LC6">  <span class="kd">var</span> <span class="nx">url</span> <span class="o">=</span> <span class="nx">self</span><span class="p">.</span><span class="nx">data</span><span class="p">.</span><span class="nx">url</span><span class="p">(</span><span class="s2">"black-google.css"</span><span class="p">);</span></div><div class="line" id="file-black-google-jetpack-example-js-LC7">  <span class="nx">us</span><span class="p">.</span><span class="nx">load</span><span class="p">(</span><span class="nx">url</span><span class="p">);</span></div><div class="line" id="file-black-google-jetpack-example-js-LC8"><span class="p">};</span></div></pre>
        </td>
      </tr>
    </tbody></table>
  </div>

        </div>

        <div class="gist-meta">
          <a href="https://gist.github.com/erikvold/1033799/raw/fe8a4ce463c77deeb4d93d326a2076cf18522b09/black-google.jetpack.example.js" style="float:right">view raw</a>
          <a href="https://gist.github.com/erikvold/1033799#file-black-google-jetpack-example-js" style="float:right; margin-right:10px; color:#666;">black-google.jetpack.example.js</a>
          <a href="https://gist.github.com/erikvold/1033799">This Gist</a> brought to you by <a href="http://github.com">GitHub</a>.
        </div>
      </div>
</div>

<p>
<a href="https://gist.github.com/1033799">In this example</a>, the addon is loading a userstyle/css file located within it's "data" folder.
</p>

<p>
If you'd like to use this module, then <a href="https://github.com/erikvold/userstyles-jplib">it is available on github here</a> for those of you that know how to use the addon-sdk. Otherwise, the module is also <a href="https://builder.addons.mozilla.org/library/1004754/latest/">available on the Addon Builder here</a>, and I have <a href="https://builder.addons.mozilla.org/addon/1004755/latest/">a example of how to use the module in the Addon Builder here</a>. So give it a try!
</p>

<h2>UserStyles</h2>
<p>For those of you that don't already know, a userstyle can be used to modify the css of any webpage (aka content) or Firefox window (aka chrome), and has been made popular by <a target="_blank" title="Stylish" rel="external nofollow" rev="vote-for" href="https://addons.mozilla.org/en-US/firefox/addon/stylish/">Stylish add-on for Firefox</a> for which there is a site, <a title="UserStyles.org" rel="external nofollow" rev="vote-for" href="userstyles.org">userstyles.org</a>, where thousands of userstyles can be found.
</p>
