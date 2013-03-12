---
title: Scriptish 0.1b4 Can Update Your User Scripts
short URL: http://r.evold.ca/scriptish0.1b4
tags: Programming, WebDev, Productivity, Greasemonkey, Internet, UserScripts, Firefox, Scriptish, Javascript
---
For a long time now both user script authors and Greasemonkey users have wanted Greasemonkey to be able to update user scripts. In absence of this feature user script authors have resorted to rolling their own code to do the updating, which has lead to a minefield of problems ranging from simple javascript errors to <a title="Downtime &amp; Rate Limiting - Userscripts.org" rel="external" rev="vote-for" target="_blank" href="http://userscripts.org/articles/29-downtime">causing long downtimes on userscripts.org</a>. Besides the obvious risks that third-party user script updaters have of not working, over using bandwidth, and harming the uptime of important websites, there is also a variability of design and usefulness which means it's hard for a user to know things that they should know, like:
</p><ol>
<li>Which of their installed user scripts are update-able?</li>
<li>Which of their installed user scripts have updates available?</li>
<li>Where will they be notified of updates for there user scripts?</li>
<li>What do they need to do in order to update a user script?</li>
<li>How can they disable updates for a user script?</li>
</ol>
<p></p>

<p>
Hopefully it's now plain to see why a user script engine must update user scripts, and yet none that I know of do. Greasemonkey for Firefox does not. Google Chrome runs user scripts natively, but also does not update them. Those two engines are by far the most popular, but there are a few others, all of which do not update user scripts..
</p>

<p>
Well <a title="Scripts update feature - Webmonkey Issues" rel="external nofollow" rev="vote-for" target="_blank" href="http://ocornu.lighthouseapp.com/projects/27038/tickets/4-scripts-update-feature">late last year I started discussing this feature with Olivier Cornu</a> for his fork of Greasemonkey which he called Webmonkey. Months later I decided to start a Greasemonkey fork of my own, which I call <a title="Scriptish" href="https://addons.mozilla.org/en-US/firefox/addon/231203/">Scriptish</a>. Then, as this year went by <a title="How to extend the new Add-ons Manager" rel="external" rev="vote-for" target="_blank" href="http://www.oxymoronical.com/blog/2010/07/How-to-extend-the-new-Add-ons-Manager">I discovered Mozilla's plans for the new Addon manager</a> and the stars seemed to align.
</p>

<p>
So a couple of days ago I finally got around to implementing user script updating in Scriptish, and released the feature in <a title="Scriptish 0.1b4" rel="download" href="https://addons.mozilla.org/en-us/firefox/downloads/file/100792/scriptish-0.1b4-fx.xpi">Scriptish 0.1b4</a> last night; now I'd like to discuss it a little bit for those that are interested.
</p>

<h2>User Script Updating in Scriptish</h2>

<h3>@updateURL</h3>
<p>
You may specify a URL for Scriptish to check for updates using the @updateURL <a title="Metadata block - Scriptish" rel="external" target="_blank" href="http://github.com/erikvold/scriptish/wiki/Scriptish-Manual:-Metadata-Block">metadata block key</a>. The @updateURL must be a secure url (ie: starts with "https://"), otherwise it will be ignored.
</p>

<h3>The optional use of ".meta.js"</h3>
<p>
To save bandwidth, and improve response times, you may optionally provide a ".meta.js" version of your user script as the @updateURL, which should be the same as the user script, but only containing the user script's metadata block. If you provide a @updateURL that ends with ".meta.js", then Scriptish will check then ".meta.js" file for updates, and download an update from the same url where ".meta.js" is replaced with ".user.js".
</p>

<h3>The option to use the download URL as the update URL if no @updateURL was provided.</h3>
<p>
If you go to the options window for Scriptish you will see a preference which allows you to use a user script's download URL as the update URL if there was no @updateURL defined; this option is turned off by default.
</p>

<h3>Using ".meta.js" by default from userscripts.org</h3>
<p>
If the update URL that should be used to check for updates is a userscripts.org URL, then the ".meta.js" version of the user script will be used by default.
</p>

<h3>The GM_updatingEnabled constant</h3>
<p>
All versions of Scriptish that provide user script updating will include a GM_updatingEnabled constant in the user script sandbox, this means that if you are a user script author that has implemented a updater for your script already, then your code can check if this variable is defined and equal to 'true' before attempting to check for updates.
</p>

<h2>Conclusion</h2>
<p>
A user script engine that updates user scripts has been long desired, so I'm proud to introduce the feature for the first time in <a title="Scriptish" rel="external" target="_blank" href="https://addons.mozilla.org/en-US/firefox/addon/231203/">Scriptish</a>, and I hope you give it a try!
</p>
