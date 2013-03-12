---
title: Can You Execute The GWO Conversion Script With A IFrame Across Domains? or Subdomains?
tags: Google Website Optimizer
---
<h2>Answer</h2>
<p>
I tested this on different subdomains about a week ago and that worked. Then I just recently tested this across different domains, and it turns out that it will only work if the user/visitor's browser allows third party cookies, which is obviously not good enough to rely upon.
So it is not a good idea, and I recommend that you use a standard method of handling cross domain tracking, which I intend to blog about.
</p>
<h2>Aside</h2>
<p>
Having said that this is not a worth while idea, I do want to mention how to ensure that this method works for all browsers =]
So if you are just so inclined, then I suggest you read this article on <a title="How to set third-party cookies with iframes" rel="external" rev="vote-for" target="_blank" href="http://viralpatel.net/blogs/2008/12/how-to-set-third-party-cookies-with-iframe.html">how to set third party cookies with an iFrame</a>.
</p>
