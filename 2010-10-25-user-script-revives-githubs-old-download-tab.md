---
title: User Script Revives GitHub's Old Download Tab
short URL: http://r.evold.ca/ghdltab
tags: Usability, UX, UserScripts, GitHub, Productivity
---
About three weeks ago GitHub removed a bunch of links to a repository's 'downloads' section replacing them with <a title="All your downloads. One Big Button - GitHub" rel="external nofollow" rev="vote-against" target="_blank" href="http://github.com/blog/729-all-of-your-downloads-one-big-button">one big downloads button</a>, which is only available to you on some pages, and instead of taking you directly to the 'downloads' page/section you now get a AJAXy popup that only displays some of the available downloads to you and provides a link to the 'downloads' section.
</p>

<p>
In my expert opinion this button sucks. It's hard to remember which pages it's available on, except for the source page so I always go there to find it, then I have to wait for a popup that I don't want to see inorder to get the link that I'm after.. another option is to correct the url in the location bar, which is the route I was taking before I finally decided to write a user script to bring the old tab back.
</p>
<h2>Sceenshots</h2>

<p>This is what the old 'Downloads' tab looked like:</p>
<img alt="GitHub's old 'Downloads' tab" src="http://farm2.static.flickr.com/1439/5113015889_8583f3225c.jpg" border="0">

<p>This is what their new button looks like:</p>
<img alt="GitHub's new 'Downloads' button" src="http://github-images.s3.amazonaws.com/blog/2010/downloads-button.png" border="0">

<h2>User Script</h2>

<p><a title="Use Old GitHub Downloads Button" rel="external" rev="vote-for" target="_blank" href="http://userscripts.org/scripts/show/88790">Find this user script at userscripts.org here</a>.</p>

<p>
I understand that they had too many links to the 'downloads' section before, but the only one I ever used was the 'downloads' tab, and it's the only one that I find myself wanting now that the old links have all been replaced with the big awful button. So I decided to write a user script to bring back the 'downloads' tab and remove the new button, here it is:
</p>

<script src="http://gist.github.com/644434.js"></script><link href="https://gist.github.com/assets/embed-0af287a4b5c981db301049e56f06e5d3.css" media="screen" rel="stylesheet"><div id="gist644434" class="gist">
      <div class="gist-file">
        <div class="gist-data gist-syntax">



  <div class="file-data">
    <table class="lines highlight" cellpadding="0" cellspacing="0">
      <tbody><tr>
        <td class="line-numbers">
          <span class="line-number" id="file-github-old-dl-btn-user-js-L1" rel="file-github-old-dl-btn-user-js-L1">1</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L2" rel="file-github-old-dl-btn-user-js-L2">2</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L3" rel="file-github-old-dl-btn-user-js-L3">3</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L4" rel="file-github-old-dl-btn-user-js-L4">4</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L5" rel="file-github-old-dl-btn-user-js-L5">5</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L6" rel="file-github-old-dl-btn-user-js-L6">6</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L7" rel="file-github-old-dl-btn-user-js-L7">7</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L8" rel="file-github-old-dl-btn-user-js-L8">8</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L9" rel="file-github-old-dl-btn-user-js-L9">9</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L10" rel="file-github-old-dl-btn-user-js-L10">10</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L11" rel="file-github-old-dl-btn-user-js-L11">11</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L12" rel="file-github-old-dl-btn-user-js-L12">12</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L13" rel="file-github-old-dl-btn-user-js-L13">13</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L14" rel="file-github-old-dl-btn-user-js-L14">14</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L15" rel="file-github-old-dl-btn-user-js-L15">15</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L16" rel="file-github-old-dl-btn-user-js-L16">16</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L17" rel="file-github-old-dl-btn-user-js-L17">17</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L18" rel="file-github-old-dl-btn-user-js-L18">18</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L19" rel="file-github-old-dl-btn-user-js-L19">19</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L20" rel="file-github-old-dl-btn-user-js-L20">20</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L21" rel="file-github-old-dl-btn-user-js-L21">21</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L22" rel="file-github-old-dl-btn-user-js-L22">22</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L23" rel="file-github-old-dl-btn-user-js-L23">23</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L24" rel="file-github-old-dl-btn-user-js-L24">24</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L25" rel="file-github-old-dl-btn-user-js-L25">25</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L26" rel="file-github-old-dl-btn-user-js-L26">26</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L27" rel="file-github-old-dl-btn-user-js-L27">27</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L28" rel="file-github-old-dl-btn-user-js-L28">28</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L29" rel="file-github-old-dl-btn-user-js-L29">29</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L30" rel="file-github-old-dl-btn-user-js-L30">30</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L31" rel="file-github-old-dl-btn-user-js-L31">31</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L32" rel="file-github-old-dl-btn-user-js-L32">32</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L33" rel="file-github-old-dl-btn-user-js-L33">33</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L34" rel="file-github-old-dl-btn-user-js-L34">34</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L35" rel="file-github-old-dl-btn-user-js-L35">35</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L36" rel="file-github-old-dl-btn-user-js-L36">36</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L37" rel="file-github-old-dl-btn-user-js-L37">37</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L38" rel="file-github-old-dl-btn-user-js-L38">38</span>
          <span class="line-number" id="file-github-old-dl-btn-user-js-L39" rel="file-github-old-dl-btn-user-js-L39">39</span>
        </td>
        <td class="line-data">
          <pre class="line-pre"><div class="line" id="file-github-old-dl-btn-user-js-LC1"><span class="c1">// ==UserScript==</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC2"><span class="c1">// @id           github-old-dl-btn@erikvold.com</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC3"><span class="c1">// @name         Use Old GitHub Downloads Button</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC4"><span class="c1">// @namespace    erikvold</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC5"><span class="c1">// @include      /^https?:\/\/github\.com\/[^\/]+\/[^\/]+/</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC6"><span class="c1">// @match        http://github.com/*/*</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC7"><span class="c1">// @noframes</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC8"><span class="c1">// @updateURL    https://userscripts.org/scripts/source/88790.meta.js</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC9"><span class="c1">// @homepage     http://userscripts.org/scripts/show/88790</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC10"><span class="c1">// @datecreated  2010-10-24</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC11"><span class="c1">// @lastupdated  2010-10-24</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC12"><span class="c1">// @version      0.1.1</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC13"><span class="c1">// @author       Erik Vergobbi Vold &lt;erikvvold@gmail.com&gt;</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC14"><span class="c1">// @license      MIT</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC15"><span class="c1">// @description  This user script will bring the old 'downloads' link back, and remove the new one.</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC16"><span class="c1">// ==/UserScript==</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC17">&nbsp;</div><div class="line" id="file-github-old-dl-btn-user-js-LC18"><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">d</span><span class="p">,</span> <span class="nx">gh</span><span class="p">)</span> <span class="p">{</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC19"><span class="kd">var</span> <span class="nx">dlBtn</span> <span class="o">=</span> <span class="nx">d</span><span class="p">.</span><span class="nx">getElementById</span><span class="p">(</span><span class="s2">"download_button"</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC20"><span class="k">if</span><span class="p">(</span><span class="nx">dlBtn</span><span class="p">)</span> <span class="nx">dlBtn</span><span class="p">.</span><span class="nx">parentNode</span><span class="p">.</span><span class="nx">removeChild</span><span class="p">(</span><span class="nx">dlBtn</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC21">&nbsp;</div><div class="line" id="file-github-old-dl-btn-user-js-LC22"><span class="kd">var</span> <span class="nx">networkLi</span> <span class="o">=</span> <span class="nx">d</span><span class="p">.</span><span class="nx">evaluate</span><span class="p">(</span><span class="s2">"//ul[contains(@class, 'tabs')]/li/a[@highlight='repo_network']"</span><span class="p">,</span> <span class="nb">document</span><span class="p">,</span> <span class="kc">null</span><span class="p">,</span> <span class="mi">9</span><span class="p">,</span> <span class="kc">null</span><span class="p">).</span><span class="nx">singleNodeValue</span><span class="p">.</span><span class="nx">parentNode</span><span class="p">;</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC23"><span class="k">if</span><span class="p">(</span><span class="o">!</span><span class="nx">networkLi</span> <span class="o">||</span> <span class="o">!</span><span class="nx">gh</span> <span class="o">||</span> <span class="o">!</span><span class="nx">gh</span><span class="p">.</span><span class="nx">nameWithOwner</span><span class="p">)</span> <span class="k">return</span><span class="p">;</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC24">&nbsp;</div><div class="line" id="file-github-old-dl-btn-user-js-LC25"><span class="kd">var</span> <span class="nx">newLi</span> <span class="o">=</span> <span class="nx">d</span><span class="p">.</span><span class="nx">createElement</span><span class="p">(</span><span class="s2">"li"</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC26"><span class="kd">var</span> <span class="nx">newA</span> <span class="o">=</span> <span class="nx">d</span><span class="p">.</span><span class="nx">createElement</span><span class="p">(</span><span class="s2">"a"</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC27"><span class="nx">newA</span><span class="p">.</span><span class="nx">setAttribute</span><span class="p">(</span><span class="s2">"highlight"</span><span class="p">,</span> <span class="s2">"repo_downloads"</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC28"><span class="nx">newA</span><span class="p">.</span><span class="nx">setAttribute</span><span class="p">(</span><span class="s2">"href"</span><span class="p">,</span> <span class="s2">"http://github.com/"</span> <span class="o">+</span> <span class="nx">gh</span><span class="p">.</span><span class="nx">nameWithOwner</span> <span class="o">+</span> <span class="s2">"/downloads"</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC29"><span class="nx">newA</span><span class="p">.</span><span class="nx">innerHTML</span> <span class="o">=</span> <span class="s2">"Downloads"</span><span class="p">;</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC30"><span class="nx">newLi</span><span class="p">.</span><span class="nx">appendChild</span><span class="p">(</span><span class="nx">newA</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC31">&nbsp;</div><div class="line" id="file-github-old-dl-btn-user-js-LC32"><span class="kd">var</span> <span class="nx">tabs</span> <span class="o">=</span> <span class="nx">networkLi</span><span class="p">.</span><span class="nx">parentNode</span><span class="p">;</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC33"><span class="nx">tabs</span><span class="p">.</span><span class="nx">insertBefore</span><span class="p">(</span><span class="nx">newLi</span><span class="p">,</span> <span class="nx">networkLi</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC34"><span class="nx">tabs</span><span class="p">.</span><span class="nx">insertBefore</span><span class="p">(</span><span class="nx">networkLi</span><span class="p">,</span> <span class="nx">newLi</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC35">&nbsp;</div><div class="line" id="file-github-old-dl-btn-user-js-LC36"><span class="k">if</span> <span class="p">(</span><span class="s2">"downloads"</span> <span class="o">!=</span> <span class="nx">gh</span><span class="p">.</span><span class="nx">controllerName</span><span class="p">)</span> <span class="k">return</span><span class="p">;</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC37"><span class="nx">newA</span><span class="p">.</span><span class="nx">setAttribute</span><span class="p">(</span><span class="s2">"class"</span><span class="p">,</span> <span class="s2">"selected"</span><span class="p">);</span></div><div class="line" id="file-github-old-dl-btn-user-js-LC38">&nbsp;</div><div class="line" id="file-github-old-dl-btn-user-js-LC39"><span class="p">})(</span><span class="nb">document</span><span class="p">,</span> <span class="nx">unsafeWindow</span><span class="p">.</span><span class="nx">GitHub</span><span class="p">);</span></div></pre>
        </td>
      </tr>
    </tbody></table>
  </div>

        </div>

        <div class="gist-meta">
          <a href="https://gist.github.com/erikvold/644434/raw/6c2fac83bf7e3a3db35592b2dfd4d1c96dd0e71d/github-old-dl-btn.user.js" style="float:right">view raw</a>
          <a href="https://gist.github.com/erikvold/644434#file-github-old-dl-btn-user-js" style="float:right; margin-right:10px; color:#666;">github-old-dl-btn.user.js</a>
          <a href="https://gist.github.com/erikvold/644434">This Gist</a> brought to you by <a href="http://github.com">GitHub</a>.
        </div>
      </div>
</div>

<p><a target="_blank" rel="external nofollow" rev="vote-for" href="http://gist.github.com/644434">Gist 644434</a> embed above</p>
