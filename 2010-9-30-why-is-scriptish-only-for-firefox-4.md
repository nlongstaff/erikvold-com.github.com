---
title: Why is Scriptish only for Firefox 4?
short URL: http://r.evold.ca/scriptish4ff4
tags: Projects, Programming, Greasemonkey, Scriptish, Firefox
---
One little tidbit <a href="http://erikvold.com/blog/index.cfm/2010/9/29/scriptish-beta-a-new-greasemonkey">I didn't go over yesterday</a> about Scriptish was why I decided not to support any version of Firefox less than 4.0, so I thought I should mention my reasons behind that decision.
</p>
<p>
The primary reason I did it was to shave a large amount of time off of the time to release tbh.  Another reason was that by raising the min version of Firefox supported to 4.0 I was able to delete large amounts of legacy code, which means performance gains.  The final reason was that there was a <a title="Add-on Manager API - MDC" rel="external nofollow" rev="vote-for" target="_blank" href="https://developer.mozilla.org/en/Addons/Add-on_Manager">Add-on Manager API</a> being introduced in Firefox 4 which allows Firefox extensions to easily add extension types to the add-on manager, which means Scriptish can rely on that entirely, and ditch even more legacy code, <a title="How to extend Firefox 4's new Add-ons Manager" rel="external" rev="vote-for" target="_blank" href="http://www.oxymoronical.com/blog/2010/07/How-to-extend-the-new-Add-ons-Manager">Dave Townsend (Mossop) describes how to extend the add-on manager here</a>.
</p>
