---
title: The Daily UserScript: YouTube 'Time' Menu Command
short URL: http://r.evold.ca/dailyus4
tags: Usability, UserScripts, Automation, Daily UserScript, Greasemonkey, Ubiquity, YouTube
---
This userscript allows you to go to a specific time on any YouTube video without need of the provide <abbr title="User Interface">UI</abbr>. This functionality is available through a Greasemonkey menu command or through the greasemonkey Ubiquity command. 
</p>

<h2>The Unpleasantry:</h2>
<p>
Say you are watching a youtube video, and for whatever reason you want to skip directly to a specific point in the video.
There are two options available to you currently, the first is to use your mouse and move the video's time slider, which is hardly specific.
The other option is to add something like this "#t=0m56s" string to the url, which isn't that hard, but if you want to share the url later then you will have to remove string again, also you might have to clean the existing string first, and the finally problem here is that you get to the right part of the url to add the string properly.
</p>

<h2>The Alleviation:</h2>
<p>
Once you install the <a href="http://userscripts.org/scripts/show/54134" title="YouTube 'Time' Menu Command" rel="external nofollow" target="_blank" rev="vote-for">"YouTube 'Time' Menu Command" UserScript</a> you have a better option, which is: 
</p>

  	<a href="http://erikvold.com/blog/index.cfm/2009/7/21/the-daily-userscript-youtube-time-menu-command#more" name="more" rel="nofollow"></a>
		
<h3>Greasemonkey Ubiquity Command Method</h3>
<p>
<a href="http://erikvold.com/blog/index.cfm/2009/7/16/greasemonkey-command-with-input-string-for-ubiquity-05" title="Greasemonkey Command With Input String For Ubiquity 0.5" rel="external nofollow" rev="vote-for" target="_blank">I recently released a greasemonkey command I was working on</a>, and you can use this userscript in combination with the <i>greasemonkey</i> Ubiquity command.
</p><ol>
<li>Hit your Ubiquity hotkey</li>
<li>Type "gm time with 5:05" to go to time 05min and 05sec, and press enter.</li>
</ol>
<p></p>
<p>
Here are some input examples:
</p><ol>
<li>1h3m5s</li>
<li>3m5s</li>
<li>1:3:5</li>
<li>01:03:05</li>
<li>3:5</li>
<li>03:5</li>
