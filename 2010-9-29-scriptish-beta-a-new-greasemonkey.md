---
title: Scriptish Beta! A New Greasemonkey
short URL: http://r.evold.ca/scriptishbeta
tags: Programming, Projects, UX, Greasemonkey, Internet, UserScripts, Firefox, Productivity, Javascript, Online Kindness
---
My favorite browser extension for quite a while has been Greasemonkey (GM), I loved how simple it made customizing the web with JavaScript (JS) which allows all users to both filter out the crap that site owners try to provide us (ie: ads, share links, suggested junk) and add new useful features anywhere you that wish. Greasemonkey allowed us to customize the waves as we surfed the web, as well as making a few modifications to the board, and I loved it for that.
</p>
<p>
Some problems arose with Greasemonkey though, because it was built for Firefox (FF) 1.5, and even the latest GM version (0.8.6) claimed to support 1.5, which meant that Greasemonkey the GM maintainers did not want to introduce new features that would not be available in FF 1.5, and they did not want to take advantage a of newer version, like say FF 3.0's <a title="JavaScript Modules - MDC" target="_blank" rel="external" rev="vote-for" href="https://developer.mozilla.org/en/JavaScript/Code_modules">JavaScript Modules</a> (JSM), which would allow GM to use much less memory and improve performance when a user is using multiple windows, and on startup because less JS would need to be loaded at startup.
</p>
<p>
The good news for GM is that with the next major release, 0.9 (which contributors including myself have been working on for quite some time now) is that the minimum version of Firefox that Greasemonkey will support will be FF 3.0, which means it can now take advantage of the benefits that FF 3.0 offers, finally. The trouble I found while trying to contribute to GM is that the maintainers don't really want to alter the code base, they're actually seem to be fine with doing the minimum necessary and bug fixing for the rest of the future, at least that is how it seemed to me after writing quite a few patches which were rejected, either outright, or by degradation (meaning I would have to basically redo everything, on crappy architecture, because they've sat on their hands for so long). Patches such as using JSM, reg exp @includes, @icon, and a few more.
</p>
<p>
So the reason that I decided to bypass Greasemonkey and start working on a fork, which I now call <strong>Scriptish</strong>, is because I was tired of beating my head against a wall, I wanted to have and use the Greasemonkey that I always wanted asap, so I'm making it now. I've always enjoyed working with others, and I hope that I can convince some GM contributors to start working on Scriptish in the future.
</p>
<h2>Scriptish</h2>
<p>
<a title="Scriptish Firefox Extension" target="_blank" rev="vote-for" href="https://addons.mozilla.org/en-US/firefox/addon/231203/">Scriptish</a> is a fork of GM, you can think of it as a superset of Greasemonkey, it can do whatever GM does, and more. Some of it's new features are:
</p><ul>
<li>@author - displayed to users in the addon manager</li>
<li>@contributor - displayed to users in the addon manager</li>
<li>@homepage or @homepageURL - displayed to users in the addon manager</li>
<li>@icon or @iconURL - Include a icon for your user script which is displayed in the addon manager and for notifications from the script.</li>
<li>@screenshot - displayed to users in the addon manager.</li>
<li>@match - a include pattern introduced by Google Chrome user scripts.</li>
<li>@noframes - a simple way to prevent a user script from running in iframes.</li>
<li>GM_worker - use a <a title="Worker - MDC" rel="external nofollow" rev="vote-for" target="_blank" href="https://developer.mozilla.org/En/DOM/Worker">Worker</a> within user scripts.</li>
<li>GM_notification - send a Growl style notification to the user.</li>
<li>GM_setClipboard - save data to the clipboard from a user script.</li>
</ul>
If you'd like to do some reading on these features, then checkout the <a title="Scriptish wiki - GitHub" target="_blank" rev="external" href="http://github.com/erikvold/scriptish/wiki">Scriptish wiki</a>, which should explain them all in detail.
<p></p>
<p>
Other changes include major reorganization of the internal code, using JSM, in a way that only loads code into memory that will actually be used, by loading the req'd code the first time that it is going to be used. I was also able to remove a bunch of legacy code, because Scriptish will only support Firefox 4.0 or higher for the moment.
</p>
<h3>Give it a try!</h3>
<p>
If you'd like to give Scriptish a try, then <a title="Scriptish Firefox Extension" target="_blank" rev="vote-for" href="https://addons.mozilla.org/en-US/firefox/addon/231203/">you can download Scriptish here</a>. If you want to get involved here are some links for you:
</p><ul>
<li>GitHub: <a title="GitHub Mailing List" href="http://github.com/erikvold/scriptish">http://github.com/erikvold/scriptish</a></li>
<li>Mailing List: <a title="Scriptish Mailing List" href="http://groups.google.com/group/scriptish">http://groups.google.com/group/scriptish</a></li>
<li>Issue Tracker:  <a title="Scriptish Issue Tracker" href="http://github.com/erikvold/scriptish/issues">http://github.com/erikvold/scriptish/issues</a></li>
</ul>
<p></p>
<p>
I hope you like it, I'll be working on it for the next few months at least, pretty hard I imagine; I'd like to make it restartless, and implement user script updates &amp; communication asap. If you think you'd like to open it up and hack on it, then please do!!
</p>
