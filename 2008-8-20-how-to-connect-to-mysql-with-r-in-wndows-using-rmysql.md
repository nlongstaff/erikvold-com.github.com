---
title: How to Connect to MySQL with R in Wndows (using RMySQL)
tags: R, MySQL
---
This is a quick step-by-step guide on how to connect to [MySQL](http://www.mysql.com/")[R](http://www.r-project.org/). If your wondering why you might want to do that, think of all the math that could be done in R, the results of which could be saved into a MySQL DB.

[RMySQL](http://cran.r-project.org/web/packages/RMySQL/index.html) is the R package that you will need to connect to MySQL; it was made by [Omegahat](http://www.omegahat.org/).

Steps:

1. Open RGui (Assuming you have installed R already).
1. Goto Packages -&gt; Install Package(s)...
1. Pick a server at a location near by.
1. Choose 'RMySQL' and install. 
1. Run the following commands to connect: 

&gt; library(RMySQL)      
&gt; drv = dbDriver("MySQL")   
&gt; con = dbConnect(drv,host="mars",dbname="sat133",user="sat133",pass="T0pSecr3t")    
&gt; album = dbGetQuery(con,statement="select * from tasks")   
&gt; a    

In the query above, if the host, database, username, and password all exist, then the code above should return a table of results =]

  	<a href="http://erikvold.com/blog/index.cfm/2008/8/20/how-to-connect-to-mysql-with-r-in-wndows-using-rmysql#more" name="more" rel="nofollow"></a>
		
