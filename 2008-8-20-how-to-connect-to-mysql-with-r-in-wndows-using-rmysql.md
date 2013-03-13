---
title: How to Connect to MySQL with R in Wndows (using RMySQL)
tags: R, MySQL
---
This is a quick step-by-step guide on how to connect to <a title="MySQL: The world's most popular open source database" target="_blank" rel="external nofollow" rev="vote-for" href="http://www.mysql.com/">MySQL</a> via <a title="R Project for Statistical Computing" target="_blank" rel="external nofollow" rev="vote-for" href="http://www.r-project.org/">R</a>. If your wondering why you might want to do that, think of all the math that could be done in R, the results of which could be saved into a MySQL DB.</p>

<p>
<a title="CRAN - Package RMySQL" rel="external" rev="vote-for" target="_blank" href="http://cran.r-project.org/web/packages/RMySQL/index.html">RMySQL</a> is the R package that you will need to connect to MySQL; it was made by <a title="The Omega Project for Statistical Computing" rel="external" rev="vote-for" target="_blank" href="http://www.omegahat.org/">Omegahat</a>.
</p>

<p>Steps:
</p><ol>
<li>Open RGui (Assuming you have installed R already).</li>
<li>Goto Packages -&gt; Install Package(s)...</li>
<li>Pick a server at a location near by.</li>
<li>Choose 'RMySQL' and install. </li>
<li>Run the following commands to connect: </li>
</ol><p></p>
<div class="code">&gt; library(RMySQL)<br>
&gt; drv = dbDriver("MySQL")<br>
&gt; con = dbConnect(drv,host="mars",dbname="sat133",user="sat133",pass="T0pSecr3t")<br>
&gt; album = dbGetQuery(con,statement="select * from tasks")<br>
&gt; a</div>

<p>In the query above, if the host, database, username, and password all exist, then the code above should return a table of results =]</p>

  	<a href="http://erikvold.com/blog/index.cfm/2008/8/20/how-to-connect-to-mysql-with-r-in-wndows-using-rmysql#more" name="more" rel="nofollow"></a>
		
	</div>
	
<script type="text/javascript">
google_ad_client = "pub-5964377618444056";
google_ad_slot = "9885673634";
google_ad_width = 468;
google_ad_height = 60;
</script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"></script><ins style="display:inline-table;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px">
