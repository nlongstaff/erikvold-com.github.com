---
title: How to setup and run MySQL in Cygwin
tags: Cygwin, MySQL
---
First, <a title="MySQL Downloads" href="http://dev.mysql.com/downloads/" rel="external nofollow" target="_blank">download</a> and install MySQL Community Server (you need this for the command line tool, so make sure when your asked, to include this in the windows path).</p>

<p>Second, make sure that the path to MySQL (usually something like: /cygdrive/c/Program Files/MySQL/MySQL Server 5.0/bin) is in the $PATH of Cygwin.</p>

<p>That's it!</p>

<p>Try a command like the following now:
</p><div class="code">mysql --user=root --password=something -D nameOfDB -h serverName -e "SELECT * FROM A_TABLE"</div>
