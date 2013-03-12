---
title: I Vote For The Vote Links Microformat
tags: Information Architecture, Microformats, SEO, HTML, WebDev
---
I'm still not sure if I'm a fan of all of the <a title="Microformats - Wikipedia" rel="external" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Microformats">microformats</a> that I have come across so far. But I can tell you that I am a huge fan of the <a title="Vote Links - Microformats Wiki" rel="external" rev="vote-for" target="_blank" href="http://microformats.org/wiki/vote-links">VoteLinks</a> microformat, because I think there is a huge need for them in <a title="Search Engine Optimization - Wikipedia" rel="external" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Search_engine_optimization">SEO</a> arena.
</p>

<p>
Currently search engines like <a title="Google" rel="external" rev="vote-for" target="_blank" href="http://www.google.com">Google</a>, <a title="Yahoo!" rel="external" rev="vote-abstain" target="_blank" href="http://www.yahoo.com">Yahoo</a>, and <a title="Live Search By Microsoft" rel="external nofollow" rev="vote-against" target="_blank" href="http://www.live.com/">that other search engine</a> (made by the same company that makes <a title="Internet Explorer By Microsoft" rel="external nofollow" rev="vote-against" target="_blank" href="http://www.microsoft.com/windows/internet-explorer/download-ie.aspx">that crappy browser</a>) all primary rely on <a title="PageRank - Wikipedia" rel="external" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Pagerank">PageRank</a>, which determines the importance of a document by considering the importance of the documents that link to it. In PageRank, every link is valuable, except those links that use the <a title="Link type &quot;nofollow&quot;" rel="external" rev="vote-for" target="_blank" href="http://dev.w3.org/html5/spec/Overview.html#link-type-nofollow">nofollow link type</a> (ie: any link without the nofollow link type is considered an endorsement). PageRank does not consider the possibility that document A might want to have a vote on document B's calculated importance, besides just the option of endorsing document B.
</p>

<p>
Enter the <a title="Vote Links - Microformats Wiki" rel="external nofollow" rev="vote-for" target="_blank" href="http://microformats.org/wiki/vote-links">VoteLinks</a> microformat. With this specification, website masters can now specify links on their web documents as votes for or against other web documents. You can also abstain from voting, ofcourse.
</p>

<p>
For example, you may have noticed that in my second paragraph I was taking a shots at the <a title="Microsoft Corporation" rel="external nofollow" rev="vote-abstain" target="_blank" href="http://www.microsoft.com/">Microsoft Corporation</a> (which I love to do) and if you look at the html markup, then you will notice that those links are votes against Live Search and Internet Explorer. So now I'm telling any user agent that visits this document that this document is a vote against those Microsoft products. This document is also a vote for some wikipedia articles, Google, Yahoo, and the VoteLinks microformat. That's a lot of knowledge that spiders can gain because of this markup, hopefully the search engine spiders start considering this microformat as a factor soon..
</p>

<p>
Anyhow, if you want to start using the VoteLinks microformat now, all you need to do is insert the following values into the rev attribute of your html anchor tags:
</p><ul>
<li>vote-for: This signals that the current document is a vote for the href url of the anchor tag.</li>
<li>vote-against: This signals that the current document is a vote against the href url of the anchor tag.</li>
<li>vote-abstain: This signals that the current document is indifferent to the href url of the anchor tag.</li>
