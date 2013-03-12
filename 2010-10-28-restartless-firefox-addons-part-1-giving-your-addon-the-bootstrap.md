---
title: Restartless Firefox add-ons, part 1: Giving your add-on the bootstrap
short URL: http://r.evold.ca/ffabs
tags: Javascript, Firefox Add-ons, Programming, Firefox
---
<h2>Intro</h2>
<p>
<a title="Mozilla Firefox 4 Beta" rel="external nofollow" rev="vote-for" target="_blank" href="http://www.mozilla.com/en-US/firefox/beta/">Firefox 4</a> will introduce a new type of add-on to users, <a title="Look Ma, no restarts!" rel="external nofollow" rev="vote-for" target="_blank" href="http://www.oxymoronical.com/blog/2010/03/Look-Ma-no-restarts">the restartless add-on</a>! It's true that <a title="How many hacks does it take to make your extension install without a restart" rel="external" rev="vote-for" target="_blank" href="http://adblockplus.org/blog/how-many-hacks-does-it-take-to-make-your-extension-install-without-a-restart">there are many problems that need to be resolved before all add-ons can be made restartless</a>, which should help illustrate why it has taken as long as it has for Mozilla to introduce the feature. The capability is available now, and although it is more difficult to write a restartless add-on than it is to write a add-on that requires a restart to be installed/uninstalled/enabled/disabled I think most would agree that a restartless add-on is usually superior to one that requires a restart. So I've decided to start a short blog series on how to write restartless add-ons for Firefox in order to help those that are interested along the way as much as I can.
</p>

<p>
You should note that Mozilla is working on a <a title="Mozilla Add-on SDK - GitHub" rel="external nofollow" rev="vote-for" target="_blank" href="http://github.com/mozilla/addon-sdk">add-on sdk</a> which makes writing restartless add-ons much easier by providing APIs which allow you to abstract away most of the painful parts, which are the parts that I plan to describe in this series. So if you're interested in writing a restartless add-on without the add-on sdk, or if you're planning on writing modules/packages to be used by add-ons made with the add-on sdk, then you may find this series useful.
</p>

<h2>The Bootstrap</h2>
<p>
The core of a restartless add-on is it's bootstrap.js file, because it's this file which Firefox loads at startup, and it's this file that Firefox will notify about install/uninstall/enable/disable/etc events which are key to making a add-on restartless. In order to notify Firefox that your add-on includes a bootstrap.js file, and that you want it to be used you must include a <i>em:bootstrap="true"</i> in your install.rdf file. If you're unfamiliar with <a title="Install Manifest - MDC" rel="external nofollow" rev="vote-for" target="_blank" href="https://developer.mozilla.org/en/install.rdf">a add-on's install manifest file (aka install.rdf) then you can read about it here</a> (it's basically just a metadata file for add-ons).
</p>
<p>
The <i>bootstrap.js</i> are a bit like a Web Worker in that it has it's own scope which has a special set of global variables and it is notified of events by defining specially named functions which are meant to receive these events.  They are disimilar from Web Workers in that they don't run in their own thread, they can pass objects in and out (not just strings), and they have access to pretty much everything using the <i>Components</i> global object which is made available to them.
</p>
<p>
For a complete list of the functions <i>bootstrap.js</i> uses, there parameters, etc, then <a title="Bootstrapped Extensions" rel="external" rev="vote-for" target="_blank" href="https://wiki.mozilla.org/Extension_Manager:Bootstrapped_Extensions">I suggest reading this article on Bootstrapped Extensions</a>. The bottom line is that you need to define functions which will handle install/uninstall/enable/disable/startup type events. For instance the first function that you'll want to define is startup(), because this is the function which would be called after the add-on is installed, after it is enabled, or after the browser starts up. Because a add-on typically needs to know why the startup function was called there is an <i>aReason</i> argument passed in to the function (read the docs on how to use <i>aReason</i>). The second function that you'll likely require is the shutdown() function, this is a <strong>very important</strong> part of restartless add-ons, it's basically the cleanup function, it has to remove any evidence that your add-on was ever present in a live browser session. In other words if your add-on adds/does X to the browser, then the shutdown() function will remove/undo X, where X can be stuff like adding xul elements and/or attributes, adding javascript variables to other scopes, adding observers/event listeners, creating background operations, and various other things; all of which are extremely easy to forget to remove.
</p>

<p>
<a rel="external nofollow" target="_blank" href="https://developer.mozilla.org/en/Extensions/Bootstrapped_extensions#Backward_compatibility">Note: If you'd like to make your add-on restartless and backwards compatible, then read this.</a>
</p>

<h2>Summary</h2>
<p>
We now know a restartless add-on needs two files: first a <a title="Install Manifest - MDC" rel="external nofollow" rev="vote-for" target="_blank" href="https://developer.mozilla.org/en/install.rdf">install.rdf</a> file, and second a <a title="Bootstrapped Extensions" rel="external" rev="vote-for" target="_blank" href="https://developer.mozilla.org/en/Extensions/Bootstrapped_extensions">bootstrap.js</a> file; we also know that the latter will be notified of install/uninstall/enable/disable type events related to the add-on which we are expected to define in order to use.
</p>
<p>
It may surprise you how many add-ons could be made with these two files alone. Most user chrome scripts or jetpack prototype scripts could be written as a bootstrap.js file and made into a extension simply by adding a <i>install.rdf</i> file and zipping the two together as a <i>.xpi</i> file.
</p>


  	<a href="http://erikvold.com/blog/index.cfm/2010/10/28/restartless-firefox-addons-part-1-giving-your-addon-the-bootstrap#more" name="more" rel="nofollow"></a>
		
<h2>Next</h2>
<p>
In part 2 I'll describe a couple of options for adding default preferences.
</p>
