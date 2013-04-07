---
title: How to setup and run MySQL in Cygwin
tags: Cygwin, MySQL
---
First, [download](http://dev.mysql.com/downloads/) and install MySQL Community Server (you need this for the command line tool, so make sure when your asked, to include this in the windows path).

Second, make sure that the path to MySQL (usually something like: /cygdrive/c/Program Files/MySQL/MySQL Server 5.0/bin) is in the $PATH of Cygwin.

That's it!

Try a command like the following now:

mysql --user=root --password=something -D nameOfDB -h serverName -e "SELECT * FROM A_TABLE"
