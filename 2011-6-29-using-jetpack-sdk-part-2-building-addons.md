---
title: Using Jetpack SDK, part 2: Building Add-ons
short URL: http://r.evold.ca/jetpacksdkp2
tags: Add-on SDK, Jetpack
---
Well after <a title="Using Jetpack SDK, part 1: WTF is CFX?" rev="vote-for" href="http://erikvold.com/blog/index.cfm/2011/6/28/using-jetpack-sdk-part-1-wtf-is-cfx">part 1 on cfx</a>, you should know what the cfx command line tool is, so let's see if you can build a add-on with it now.  FYI, I'm going to assume you know how to use git, because if you don't then you should learn asap.
</p>

<p>
First of all you'll need to have the <a href="https://addons.mozilla.org/en-US/developers/builder" title="Jetpack SDK">Jetpack SDK (aka Add-on SDK) source downloaded</a>, I recommend getting the source from <a title="Mozilla Jetpack SDK -  Github" href="https://github.com/mozilla/addon-sdk">github here</a>.  I typically keep all git clones from github in a folder called "github" someplace on my HD.  After you've got the Jetpack SDK downloaded, you will want to clone my simple <a href="https://github.com/erikvold/copy-html-jetpack" title="Copy HTML Firefox Add-on - Github">Copy HTML</a> add-on for Firefox.
</p>

<p>
Once you have the Jetpack source, and the Copy HTML source downloaded, navigate to the Jetpack SDK clone in a shell program and <a target="_blank" title="Jetpack SDK Readme.txt - Github" href="https://github.com/mozilla/addon-sdk/blob/master/README.txt" rel="external nofollow">follow these instructions</a>.  You should have gotten a message that says something like "Welcome to the Add-on SDK. Run 'cfx docs' for assistance.". Running cfx docs here would allow you to access the Jetpack SDK documentation, which is very valuable, and you should get familiar with it.  You can disregard the message for now though, and navigate to the Copy HTML clone in your same shell window, once you are there you can use two important commands which build your addon; the first is "cfx xpi" which will build a xpi, and the second is "cfx run" which will build the add-on temporarily and open it in Firefox instance for you to test it out. Typically you will use "cfx run" and few times, testing changes out, before finally running "cfx xpi" and distributing your add-on.
</p>

<p>
The <a title="Copy HTML" href="https://addons.mozilla.org/en-US/firefox/addon/copy-html/">Copy HTML add-on</a> is a simple add-on which adds a context menu called "Copy HTML" that allows one to copy the HTML source code for the area selected.  So if you highlight a blog post, and copy the html, then you will have the html source of the blog post in your clipboard, img tags, anchor links, and all.
</p>

<p>
Well give this a try, and see if you can get it to work, so that you will be ready for part 3 on using packages.
</p>
