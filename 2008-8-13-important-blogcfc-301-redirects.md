---
title: Important BlogCFC 301 redirects.
tags: Coldfusion
---
<p>I put the following code after the first line of code of my blogCFC's application.cfm (and the comments), for a application.cfc converted site, this should go in the onRequestStart method:
</p><div class="code">&lt;!--- START: IMPORTANT 301 REDIRECTS ---&gt;<br>
&lt;cfif (cgi.server_name eq "www.erikvold.com")&gt;<br>
  &lt;cffunction name="cf301Redirect" access="public" returntype="void"&gt;<br>
    &lt;cfargument name="urlString" type="string" required="yes" /&gt;<br>
    <br>
    &lt;!--- 301 redirect the user to the provided url ---&gt;<br>
    &lt;cfheader statuscode="301" statustext="Moved permanently" /&gt;<br>
    &lt;cfheader name="Location" value="#arguments.urlString#" /&gt;<br>
  &lt;/cffunction&gt;<br>
<br>
&nbsp;&nbsp;&nbsp;&lt;!--- START: Create redirect string ---&gt;<br>
&nbsp;&nbsp;&nbsp;&lt;cfset request.currentURL = "<a target="_blank" href="http://erikvold.com">http://erikvold.com</a>" /&gt;<br>
<br>
  &lt;cfif cgi.script_name eq cgi.path_info&gt;<br>
    &lt;cfif len(trim(cgi.query_string)) gt 0&gt;<br>
      &lt;cfset request.currentURL = request.currentURL &amp; "#cgi.SCRIPT_NAME#?#cgi.query_string#" /&gt;<br>
    &lt;cfelse&gt;<br>
      &lt;cfset request.currentURL = request.currentURL &amp; "#cgi.SCRIPT_NAME#" /&gt;<br>
    &lt;/cfif&gt;<br>
  &lt;cfelse&gt;<br>
    &lt;cfif len(trim(cgi.query_string)) gt 0&gt;<br>
      &lt;cfset request.currentURL = request.currentURL &amp; "#cgi.SCRIPT_NAME##cgi.PATH_INFO#?#cgi.query_string#" /&gt;<br>
    &lt;cfelse&gt;<br>
      &lt;cfset request.currentURL = request.currentURL &amp; "#cgi.SCRIPT_NAME##cgi.PATH_INFO#" /&gt;<br>
    &lt;/cfif&gt;<br>
  &lt;/cfif&gt;<br>
  &lt;!--- END: Create redirect string ---&gt;<br>
  <br>
  &lt;!--- redirect the user ---&gt;<br>
&nbsp;&nbsp;&nbsp;&lt;cfset cf301Redirect( request.currentURL ) /&gt;<br>
&lt;/cfif&gt;<br>
&lt;!--- END: IMPORTANT 301 REDIRECTS ---&gt;</div><p></p>

<p>Duplicate content is bad, mmmm K..</p>

<p>So to avoid it, redirect your www.domain.com to domain.com, or I'm sure anyone can alter this quickly to do the reverse.</p>

<p>I'd love to see any https alterations, or I'll probably do my own eventually too..</p>
