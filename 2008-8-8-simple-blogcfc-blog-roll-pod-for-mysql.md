---
title: Simple BlogCFC Blog Roll pod for MySQL
tags: Coldfusion, MySQL
---
I was looking for a BlogCFC Blog Roll pod today and could not find one that suited my needs, so here is the one I built for my MySQL db (note the MySQL script can easily be converted for MSSQL or other db types).

This is the Blog Roll MySQL CREAT TABLE script:

-- -----------------------------------------------------   
-- Table `tblblogpod_blogroll`   
-- -----------------------------------------------------   
CREATE  TABLE IF NOT EXISTS `tblblogpod_blogroll`(   
  `id` INT UNSIGNED NOT NULL AUTO_INCREMENT ,   
  `href` VARCHAR(255) NOT NULL DEFAULT 'http://' ,   
  `title` VARCHAR(255) NOT NULL ,   
  `text` VARCHAR(255) NOT NULL ,   
  `rel` VARCHAR(45) NOT NULL DEFAULT 'external nofollow',  
  `target` VARCHAR(15) NOT NULL DEFAULT '_blank',  
  PRIMARY KEY (`id`) )   
ENGINE = MyISAM;   

This is the Blog Roll Pod Code:

&lt;cfsetting enablecfoutputonly='true'&gt;   
&lt;cfprocessingdirective pageencoding='utf-8'&gt;   
&lt;!---   
   Name : Blogroll for BlogCFC &amp; MySQL   
   Author : Erik Vergobbi Vold   
---&gt;   
   
&lt;cfquery name="getBlogRoll" datasource="#application.blog.getProperty('dsn')#" username="#application.blog.getProperty('username')#" password="#application.blog.getProperty('password')#"&gt;   
SELECT text, href, title, rel, target   
FROM tblblogpod_blogroll   
ORDER BY text   
&lt;/cfquery&gt;  
   
   
&lt;cfmodule template="../../tags/podlayout.cfm" title="Blog Roll"&gt;   
   
&lt;cfloop query="getBlogRoll"&gt;   
   
&lt;cfoutput&gt;&lt;a #iif( len(trim(title)) gt 0, de('title="'&amp;title&amp;'"'), de(''))# #iif( len(trim(target)) gt 0, de('target="'&amp;target&amp;'"'),de(''))# #iif( len(trim(rel)) gt 0, de('rel="'&amp;rel&amp;'"'), de('   
'))# href="#href#"&gt;#text#&lt;/a&gt;&lt;br /&gt;&lt;/cfoutput&gt;   
&lt;/cfloop&gt;   
   
&lt;/cfmodule&gt;   
   
&lt;cfsetting enablecfoutputonly='false'/&gt;   

If anyone else decides to use this for MSSQL, or some other db type, please post the SQL script in a comment, thank you.

