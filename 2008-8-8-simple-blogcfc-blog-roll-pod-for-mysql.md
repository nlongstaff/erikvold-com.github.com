---
title: Simple BlogCFC Blog Roll pod for MySQL
tags: Coldfusion, MySQL
---
<p>I was looking for a BlogCFC Blog Roll pod today and could not find one that suited my needs, so here is the one I built for my MySQL db (note the MySQL script can easily be converted for MSSQL or other db types).</p>

<p>This is the Blog Roll MySQL CREAT TABLE script:
</p><div class="code">-- -----------------------------------------------------<br>
-- Table `tblblogpod_blogroll`<br>
-- -----------------------------------------------------<br>
CREATE  TABLE IF NOT EXISTS `tblblogpod_blogroll` (<br>
  `id` INT UNSIGNED NOT NULL AUTO_INCREMENT ,<br>
  `href` VARCHAR(255) NOT NULL DEFAULT 'http://' ,<br>
  `title` VARCHAR(255) NOT NULL ,<br>
  `text` VARCHAR(255) NOT NULL ,<br>
  `rel` VARCHAR(45) NOT NULL DEFAULT 'external nofollow' ,<br>
  `target` VARCHAR(15) NOT NULL DEFAULT '_blank' ,<br>
  PRIMARY KEY (`id`) )<br>
ENGINE = MyISAM;</div><p></p>

<p>This is the Blog Roll Pod Code:
</p><div class="code">&lt;cfsetting enablecfoutputonly='true'&gt;<br>
&lt;cfprocessingdirective pageencoding='utf-8'&gt;<br>
&lt;!---<br>
   Name : Blogroll for BlogCFC &amp; MySQL<br>
   Author : Erik Vergobbi Vold<br>
---&gt;<br>
<br>
&lt;cfquery name="getBlogRoll" datasource="#application.blog.getProperty('dsn')#" username="#application.blog.getProperty('username')#" password="#application.blog.getProperty('password')#"&gt;<br>
SELECT text, href, title, rel, target<br>
FROM tblblogpod_blogroll<br>
ORDER BY text<br>
&lt;/cfquery&gt;<br>
<br>
<br>
&lt;cfmodule template="../../tags/podlayout.cfm" title="Blog Roll"&gt;<br>
<br>
&lt;cfloop query="getBlogRoll"&gt;<br>
<br>
&lt;cfoutput&gt;&lt;a #iif( len(trim(title)) gt 0, de('title="'&amp;title&amp;'"'), de(''))# #iif( len(trim(target)) gt 0, de('target="'&amp;target&amp;'"'),de(''))# #iif( len(trim(rel)) gt 0, de('rel="'&amp;rel&amp;'"'), de('<br>
'))# href="#href#"&gt;#text#&lt;/a&gt;&lt;br /&gt;&lt;/cfoutput&gt;<br>
&lt;/cfloop&gt;<br>
<br>
&lt;/cfmodule&gt;<br>
<br>
&lt;cfsetting enablecfoutputonly='false'/&gt;</div><p></p>

<p>If anyone else decides to use this for MSSQL, or some other db type, please post the SQL script in a comment, thank you.</p>
