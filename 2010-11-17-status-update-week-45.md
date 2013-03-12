---
title: Status Update: Week 45
short URL: http://r.evold.ca/2010w45
tags: MultiVista, Mozilla, Firefox Add-ons, Scriptish
---
<h2>MultiVista</h2>
<p>
Last week I started a new job working for <a title="MultiVista" rel="external" target="_blank" href="http://multivista.com">MultiVista</a> (they make documentation software for the construction industry), and that's been going well, I'm learning their software still and spent the week getting a crash course on the products and how the interface works for all of the different user roles, then I started fixing some bugs and got acquainted with a decent portion of the source. I like their products though, and the team I'm working with here in Victoria all seem like a great bunch of people.
</p>

<p>
On tuesday and thursday they (sometimes) hit the gym for a bit, which is something that I know I need to do, and want to do, but just never do, so I think this should help get me in to better shape. My first visit was sad though, and I'm very sore atm, so I've got a ways to go..
</p>

<p>
The only downside is <a rel="external nofollow" target="_blank" href="http://maps.google.com/maps?f=d&amp;source=s_d&amp;saddr=Metchosin+BC+V9C+4G6,+Canada&amp;daddr=200-764+Yates+Street,+Victoria,+BC+V8W+1L4,+Canada&amp;hl=en&amp;geocode=FTno4QIdaYOi-ClVXWHcKAmPVDHyFgb333Wo3g%3BFbbs4gIdgKGl-CmV0_BshXSPVDHZrTEGbgoGig&amp;mra=ls&amp;sll=48.285934,-123.361359&amp;sspn=0.48249,1.131592&amp;ie=UTF8&amp;z=12">the commute</a> (if only I could boat to work!), so I'll have to find a place closer to town eventually.
</p>

<h3>Open Source</h3>
<p>
I was very clear that I wanted to be able to work on the open source projects that I've been working on, and other open source projects related to the web browser realm, and they've said (and this is all in writing too) that will be fine as long as I'm keeping them up-to-date about what I'm working on, and the projects don't compete with MultiVista's interests. Since I want to stick to working on open source browser related projects in my free time now, and MultiVista is involved in making software for construction documentation, I don't imagine that there will be any issue.
</p>

<h2>Done</h2>
<p>
Well needless to say I won't have as much time to work on open source projects as I've had over the last year, but I was able to get a few things done last week:
</p>

<h3>Mozilla Lab's Prospector</h3>
<ul>
<li>findSuggest: Display suggestions whenever the find bar is displayed (<a rel="external" rev="vote-for" target="_blank" href="https://github.com/mozilla/prospector/issues/issue/31">Issue #31</a>)</li>
<li>findSuggest: Clicking a suggestion == query should be like clicking next (<a rel="external" rev="vote-for" target="_blank" href="https://github.com/mozilla/prospector/issues/issue/32">Issue #32</a>)</li>
<li>Shutdown faster (<a rel="external" rev="vote-for" target="_blank" href="https://github.com/mozilla/prospector/issues/issue/39">Issue #39</a>)</li>
</ul>
<h3>Greasemonkey</h3>
<ul>
<li><a rel="external" rev="vote-for" target="_blank" href="https://github.com/greasemonkey/greasemonkey/commit/9c5ff1874b4405bd11219ca24bbe5088171f87a8">Bug Fix</a>: Some delayed injections were not happening</li>
<li>My pull request for using Growl style notifications was finally pulled! (<a rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/greasemonkey/greasemonkey/pull/1193">Pull request 1193</a>)</li>
</ul>
<h3>Scriptish</h3>
<ul>
<li><a title="Scriptish 0.1b6 is ready!" rel="external" rev="vote-for" target="_blank" href="http://erikvold.com/blog/index.cfm/2010/11/14/scriptish-01b6-is-ready">Released Scriptish 0.1b6!</a></li>
<li>@icon failures are no longer fatal errors, just errors logged in the error console (<a rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/erikvold/scriptish/issues/issue/120">Issue #120</a>). Thanks for the help there <a rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/supahgreg">supahgreg</a>!</li>
</ul>


  	<a href="http://erikvold.com/blog/index.cfm/2010/11/17/status-update-week-45#more" name="more" rel="nofollow"></a>
		
<h2>Next</h2>
<p>
Scriptish is nearly ready to be released, I'm just waiting for feedback on 0.1b6 and for a resolution to <a rel="external nofollow" rev="vote-for" target="_blank" href="https://bugzilla.mozilla.org/show_bug.cgi?id=612025">bug 612025</a>, then I'll be ready to release 0.1 and request a review from a AMO editor to obtain public status on <a title="AMO" rel="external nofollow" rev="vote-for" target="_blank" href="http://addons.mozilla.org">addons.mozilla.org</a>. After I've relased 0.1 I'll start thinking about tackling the 0.1.x <a rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/erikvold/scriptish/issues">issues</a>.
</p>
<p>
<a title="Building a Jetpack Package for Userscripts - Erik Vold's Blog" rev="vote-for" target="_blank" href="http://erikvold.com/blog/index.cfm/2010/5/7/building-a-jetpack-package-for-userscripts">I've had a plan to make a user script package</a> for Mozilla's <a rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/mozilla/addon-sdk">add-on sdk</a> for quite some time now, and <a rel="external nofollow" rev="vote-for" target="_blank" href="https://github.com/erikvold/userscripts-jetpack-package">it's already partly done</a>, so I think I'll be investing time getting that ready before the add-on sdk beta release is ready for the public, which should be December/January as I understand it.
</p>
<p>
Prospector is still keeping me interested as well, and there are a couple of issues I've got plans for still, so with some luck I'll be able to contribute a few more patches to that wonderful project this week.
</p>
