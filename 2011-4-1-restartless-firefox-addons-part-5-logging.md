---
title: Restartless Firefox Add-ons, Part 5: Logging
short URL: http://r.evold.ca/rrffap5
tags: Firefox Add-ons, Programming, Firefox
---
This is a simple one for most of you, but <a rel="external nofollow" target="_blank" rev="vote-against" href="http://stackoverflow.com/questions/5507123/debug-print-from-a-bootstrapped-firefox4-extension">I found someone asking the question "How do I dump messages from bootstrap.js" on stackovercrap</a> so I thought it would make a good topic to quickly blog about.
</p>

<p>
First of all what I'm about to describe is exactly how one would log messages and report errors from a <a target="_blank" rel="external" rev="vote-for" href="https://developer.mozilla.org/en/JavaScript_code_modules">JavaScript code module</a>, so if you already know how to do this, then stop reading and bounce.
</p>

<p>
If you are lost without <a title="window.dump" rel="external" target="_blank" href="https://developer.mozilla.org/en/window.dump">window.dump</a> or don't know what that is, then give this page <a rel="external nofollow" target="_blank" href="https://developer.mozilla.org/en/window.dump">https://developer.mozilla.org/en/window.dump</a> a quick read. There is a note that says:
</p>

<p>
</p><blockquote>
"dump is commonly used to debug JavaScript. Privileged code can also use <a title="Components.utils.reportError" target="_blank" rel="external" rev="vote-for" href="https://developer.mozilla.org/en/Components.utils.reportError">Components.utils.reportError</a> and <a title="nsIConsoleService" rel="external" target="_blank" rev="vote-for" href="https://developer.mozilla.org/en/XPCOM_Interface_Reference/nsIConsoleService">nsIConsoleService</a> to log messages to the Error Console."
</blockquote>
<p></p>

<p>
Bingo! Give the page on <a title="nsIConsoleService" rel="external" target="_blank" rev="vote-for" href="https://developer.mozilla.org/en/XPCOM_Interface_Reference/nsIConsoleService">nsIConsoleService</a> a re-read. There is a code example on the top of that page that you can use to get a console service, then the page describes it's various methods, such as <a title="logStringMessage" target="_blank" rel="external" rev="vote-for" href="https://developer.mozilla.org/en/XPCOM_Interface_Reference/nsIConsoleService#logStringMessage()">logStringMessage</a>. You can use the logStringMessage method in window.dump's stead.
</p>

<p>
The window.dump page also mentioned <a title="Components.utils.reportError" target="_blank" rel="externa" rev="vote-for" href="https://developer.mozilla.org/en/Components.utils.reportError">Components.utils.reportError</a> which can be used for logging error messages to the Error Console.
</p>

<p>
The way that I prefer to access the console service is via the <a title="Services.jsm - MDN" rel="external" rev="vote-for" target="_blank" href="https://developer.mozilla.org/en/JavaScript_code_modules/Services.jsm">Services.jsm</a> JavaScript code module, like so:
</p>

<div class="code">Components.utils.import("<a target="_blank" href="resource://gre/modules/Services.jsm">resource://gre/modules/Services.jsm</a>");<br>
Services.console.logStringMessage("this is a console message, look for it in the messages tab of the Error Console.");</div>
