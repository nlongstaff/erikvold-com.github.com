---
title: A Jetpack: Tweet This!
short URL: http://r.evold.ca/dailyus97
tags: Jetpacks, Twitter, Daily UserScript, Automation, Productivity, Firefox
---
I wrote my first entry for the <a title="Jetpack 50-line Code Challenge" rel="external" rev="vote-for" target="_blank" href="http://mozillalabs.com/jetpack/2009/11/13/jetpack-50-line-code-challenge/">Jetpack 50-line Code Challenge</a> a few weeks ago and I would like to share it with you now. The Jetpack is called <a title="Tweet This! - Jetpack Gallery" rel="external info" rev="about" target="_blank" href="http://jetpackgallery.mozillalabs.com/jetpacks/136">Tweet This!</a>, and it is meant to help you quickly tweet about a page you are viewing in <a title="Mozilla Firefox" rel="external nofollow" target="_blank" href="http://www.mozilla.com/firefox/">Firefox</a> with the document's published short url, if it is defined (otherwise <a title="Tr.im" rel="external nofollow" target="_blank" href="http://tr.im/">tr.im</a> is used).
</p>
<h2><a title="Tweet This! - Jetpack Gallery" href="http://jetpackgallery.mozillalabs.com/jetpacks/136">Tweet This!</a></h2>
<h3>Details</h3>
<p>The <a title="Tweet This! - Jetpack Gallery" rel="external info" rev="about" target="_blank" href="http://jetpackgallery.mozillalabs.com/jetpacks/136">Tweet This!</a> Jetpack adds a 'Tweet This!' menu item to Firefox's 'Bookmarks' menu and context menu, which when used, will allow the user to Tweet about the page they are on. A user can select some text on the page, or else the page's title will be used for some text in the tweet, and then the Jetpack will first check if the text + long url is less than 140 characters long, and just use the long url if so, but otherwise it will use my <a title="Get Short URL" rev="external" target="_blank" href="http://getshorturl.appspot.com/">Get Short URL</a> service (hosted by Google App Engine) to find the shortest url for the page, which is published by the page, and if one has not been published which is smaller than a length you can change in settings, but is by default 35. If the shortest url found is not shorter than the setting length specified then the <a title="Tr.im" rel="external nofollow" target="_blank" href="http://tr.im/">tr.im</a> service is used to create a short url for the page.
</p>
<p>
After the Jetpack has a short url for the page, and some text to tweet about it, it will finally trim the text so that the tweet is equal to 140 chars if necessary, then send the tweet, and notify you with the tweet if it has been sent (also the username that it was sent from is displayed).
</p>
<h3>Notes</h3>
<ul>
<li>
If you do not see a notification, then an error occurred, and no tweet was sent, so it will be safe to try again, just make sure you wait about a minute before trying again (don't be too hasty). An error would only occur if the <a title="Tr.im" rel="external nofollow" target="_blank" href="http://tr.im/">Tr.im</a> or <a title="Twitter" rel="external nofollow" target="_blank" href="http://twitter.com">Twitter</a> servers return an error.
</li>
<li>The jetpack settings are pretty basic, and while they provide a range type they do not show the range to the user, or the value the user has selected in the range. Hopefully this will be changed in short time, but until then I'll just let you know here the Max URL Length range is from 20 to 100.</li>
</ul>


  	<a href="http://erikvold.com/blog/index.cfm/2009/12/12/a-jetpack-tweet-this#more" name="more" rel="nofollow"></a>
		
<h3>Trivia</h3>
<ul>
<li>Only <strong>49</strong> lines of code.</li>
<li>Uses both APIs added to the arsenal in Jetpack 0.6</li>
<li>Uses <strong>3</strong> future Jetpack APIs.</li>
<li>Uses the following <strong>6</strong> Jetpack APIs:
<ul>
<li>jetpack.lib.twitter</li>
<li>jetpack.menu (future api, added in 0.6)</li>
<li>jetpack.notifications</li>
<li>jetpack.selection (future api)</li>
<li>jetpack.storage.settings (future api, added in 0.6)</li>
<li>jetpack.tabs</li>
</ul>
</li>
<li>Uses the following <strong>3</strong> External APIs:
<ul>
<li>getshorturl.appsport.com</li>
<li>tr.im</li>
<li>twitter</li>
</ul>
</li>
</ul>
<h3>Screen Shot</h3>
<div><img alt="Screen shot of 'Tweet This!' in the 'Bookmarks' Firefox menu" src="http://jetpackgallery.mozillalabs.com/images/jetpacks/0/136/136-image-1-large.jpg"></div>
<h3>How To Install</h3>
<ol>
<li><a title="Get Firefox!" rel="external nofollow" rev="vote-for" target="_blank" href="http://getfirefox.com/">Get Firefox here</a>.</li>
<li><a title="Jetpack - AMO" rel="external nofollow" rev="vote-for" target="_blank" href="https://addons.mozilla.org/en-US/firefox/addon/12025">Get Jetpack here</a></li>
<li><a title="Tweet This! - Jetpack Gallery" href="http://jetpackgallery.mozillalabs.com/jetpacks/136">Get the Tweet This! Jetpack here</a></li>
</ol>
<h3>Links</h3>
<ul>
<li><strong>Jetpack Gallery:</strong> <a title="Tweet This! - Jetpack Gallery" rel="external" rev="vote-for" target="_blank" href="http://jetpackgallery.mozillalabs.com/jetpacks/136">http://jetpackgallery.mozillalabs.com/jetpacks/136</a></li>
<li><strong>UserScripts.org:</strong> <a title="Tweet This! - UserScripts.org" rel="external" rev="vote-for" target="_blank" href="http://userscripts.org/jetpacks/280">http://userscripts.org/jetpacks/280</a></li>
<li><strong>GitHub:</strong> <a title="Tweet This! - GitHub" rel="external" rev="vote-for" target="_blank" href="http://github.com/erikvold/tweet-this--jetpack">http://github.com/erikvold/tweet-this--jetpack</a>
