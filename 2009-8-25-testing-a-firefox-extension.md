---
title: Testing a Firefox Extension
short URL: http://r.evold.ca/fftexttesting
tags: Programming, Testing, Automation, Firefox
---
If you are starting a new Firefox extension now or might in the future, then here are some tips you should be aware of, and which I want to record for myself.
</p>
<h2>Setup a New Profile</h2>
<p>
Firefox saves bookmarks, passwords, user preferences, <strong>and extensions</strong> in a set of files collected in a folder, which is all called your <strong>profile</strong>, and this is stored in a different location than the Firefox program files.
So the first step I recommend is to <strong>setup a new profile for the extension</strong>.
If you need help with this follow the <a title="Managing profiles" rel="external" target="_blank" href="http://support.mozilla.com/en-US/kb/Managing+profiles">Firefox support knowledge base article on managing profiles here</a>.
</p>
<h2>Add a Pointer File</h2>
<p>
If you are using Firefox 2.0+ (and you should be) then you can <strong>create a pointer to the folder where you are developing the extension</strong>, and this is the fastest way to develop.
</p><ol>
<li>Find the profile folder for the profile you just created, and open the "extensions" folder inside.</li>
<li>Create a new text file whose name is the extension's id, and whose contents are the location to the extension's source.</li>
</ol>
<p></p>
<p>For more reading see the <a title="Building a Firefox Extension" rel="external" target="_blank" href="https://developer.mozilla.org/en/Building_an_Extension">Mozilla developer center article on building an extension</a>
