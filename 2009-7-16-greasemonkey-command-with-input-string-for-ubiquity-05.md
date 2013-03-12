---
title: Greasemonkey Command With Input String For Ubiquity 0.5
short URL: http://r.evold.ca/greaseubiquity
tags: Programming, Ubiquity, Greasemonkey, Internet, Browsers, How To, Firefox, Automation, Javascript, WebDev
---
I have been working hard on this for the last week, trying to get a better version out by getting an update I did for Greasemonkey into the trunk (this will take a lot of time, and will be an improvement), but I am now pleased to release a version of the <a href="http://gist.github.com/141957" title="Greasemonkey Command for Ubiquity 0.5+" rel="external nofollow" target="_blank" rev="vote-for">Greasemonkey Ubiquity Command (ready for Ubiquity 0.5)</a> which will accept an input string.
  </p>

	<h2>What is it?</h2>
	<p>
		It is a <a href="http://labs.mozilla.com/projects/ubiquity/" title="Ubiquity" rev="vote-for" rel="external nofollow" target="_blank">Ubiquity</a> command which allows you find and execute <a href="http://wiki.greasespot.net/GM_registerMenuCommand" title="GM_registerMenuCommand" rel="external nofollow" rev="vote-for" target="_blank">Greasemonkey menu commands</a>.
	</p>

	<h2>How do you get it?</h2>
	<ol>
		<li>Get <a href="http://labs.mozilla.com/projects/ubiquity/" title="Ubiquity" rev="vote-for" rel="external nofollow" target="_blank">Ubiquity</a> 0.5 or greater.</li>
		<li>Get <a href="https://addons.mozilla.org/en-US/firefox/addon/748" title="Greasemonkey" rel="external nofollow" rev="vote-for" target="_blank">Greasemonkey</a>.</li>
		<li>Get the <a href="http://gist.github.com/141957" title="Greasemonkey Command for Ubiquity 0.5+" rel="external nofollow" target="_blank" rev="vote-for">Greasemonkey Ubiquity Command</a>.</li>
		<li>Get a <a href="http://userscripts.org/" title="UserScripts.org" rel="external nofollow" rev="vote-for" target="_blank">UserScript</a> with a menu command, and that is it!</li>
	</ol>

		<a href="http://erikvold.com/blog/index.cfm/2009/7/16/greasemonkey-command-with-input-string-for-ubiquity-05#more" name="more" rel="nofollow"></a>
		

	<h2>Example</h2>
	<p>
		I have written an example userscript adapted for this Ubiquity command <a href="http://userscripts.org/scripts/show/53795" title="IMDB Vote Command" rel="external nofollow" rev="vote-for" target="_blank">here</a>.
		It is a <a href="http://wiki.greasespot.net/GM_registerMenuCommand" title="GM_registerMenuCommand" rel="external nofollow" rev="vote-for" target="_blank">Greasemonkey menu command</a> for IMDB pages like <a href="http://www.imdb.com/title/tt0107290/" title="Jurassic Park" rev="vote-for" rel="external nofollow" target="_blank">this one</a>, which allows you to vote on the movie without using the ui provided.
	</p>
	<p>
		To try the userscript, install it, and make sure you have ubiquity, greasemonkey, and the command; all of which I link to above.
		Then go to a movie page on <a href="http://imdb.com" title="IMDB" rel="external nofollow" target="_blank">imdb.com</a> on which you see the rating stars, and you will need to be logged in to IMDB in order to make a rating.
		Then, in Ubiquity, type "greasemonkey vote with 5", where you can replace 5 with your vote out of 10.
		Once you execute this, your vote should change.
	</p>

	<h2>Screenshot</h2>
	<img src="/images/screenshots/greasemonkey-command-for-ubiquity.jpg" alt="Greasemonkey Command for Ubiquity 0.5">

	<h2>The Future</h2>
	<p>
		There are many many ideas I have come up with so far, for sites that could use a site specific Ubiquity command, offering the @include/@exclude and other features of Greasemonkey, so I find this is a happy way to bridge the two worlds together.
		So I expect that there will be many Greasemonkey menu commands built to work with Ubiquity, and all of those that exist today can easily be updated to accomodate this Ubiquity command.
	</p>
	<p>
		I have also been thinking about making another Ubiquity command soon, or updating this one, so that site owners can offer site specific commands for their site, on their site, without asking the user to install them (which they can do now by methods I describe above).
		The idea is like hotkeys essentially, but so much better, as you don't have to remember the keys, and there is an input string.
	</p>

	<p>
		I hope you enjoy this, and would love to hear some feedback! <a href="http://twitter.com/erikvold" title="@erikvold" target="_blank" rel="external nofollow" rev="vote-for">tweet me</a>
