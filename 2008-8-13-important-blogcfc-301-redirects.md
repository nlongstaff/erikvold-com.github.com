---
title: Important BlogCFC 301 redirects.
tags: Coldfusion
---
I put the following code after the first line of code of my blogCFC's application.cfm (and the comments), for a application.cfc converted site, this should go in the onRequestStart method:

&lt;!--- START: IMPORTANT 301 REDIRECTS ---&gt;   
&lt;cfif (cgi.server_name eq "www.erikvold.com")&gt;   
  &lt;cffunction name="cf301Redirect" access="public" returntype="void"&gt;   
    &lt;cfargument name="urlString" type="string" required="yes" /&gt;   
    
&lt;!--- 301 redirect the user to the provided url ---&gt;   
&lt;cfheader statuscode="301" statustext="Moved permanently" /&gt;   
&lt;cfheader name="Location" value="#arguments.urlString#" /&gt;   
&lt;/cffunction&gt;   

&lt;!--- START: Create redirect string ---&gt;   
&lt;cfset request.currentURL = [erikvold.com](http://erikvold.com)   

&lt;cfif cgi.script_name eq cgi.path_info&gt;   
&lt;cfif len(trim(cgi.query_string)) gt 0&gt;   
&lt;cfset request.currentURL = request.currentURL &amp; "#cgi.SCRIPT_NAME#?#cgi.query_string#" /&gt;   
&lt;cfelse&gt;   
&lt;cfset request.currentURL = request.currentURL &amp; "#cgi.SCRIPT_NAME#" /&gt;   
&lt;/cfif&gt;   
&lt;cfelse&gt;   
&lt;cfif len(trim(cgi.query_string)) gt 0&gt;   
&lt;cfset request.currentURL = request.currentURL &amp; "#cgi.SCRIPT_NAME##cgi.PATH_INFO#?#cgi.query_string#" /&gt;   
&lt;cfelse&gt;   
&lt;cfset request.currentURL = request.currentURL &amp; "#cgi.SCRIPT_NAME##cgi.PATH_INFO#" /&gt;   
&lt;/cfif&gt;   
&lt;/cfif&gt;   
&lt;!--- END: Create redirect string ---&gt;   

&lt;!--- redirect the user ---&gt;   
&lt;cfset cf301Redirect( request.currentURL ) /&gt;   
&lt;/cfif&gt;   
&lt;!--- END: IMPORTANT 301 REDIRECTS ---&gt;    

Duplicate content is bad, mmmm K..

So to avoid it, redirect your www.domain.com to domain.com, or I'm sure anyone can alter this quickly to do the reverse.

I'd love to see any https alterations, or I'll probably do my own eventually too..
