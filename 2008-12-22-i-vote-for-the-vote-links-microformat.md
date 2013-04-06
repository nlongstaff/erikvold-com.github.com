---
title: I Vote For The Vote Links Microformat
tags: Information Architecture, Microformats, SEO, HTML, WebDev
---
I'm still not sure if I'm a fan of all of the [microformats](http://en.wikipedia.org/wiki/Microformats) that I have come across so far. But I can tell you that I am a huge fan of the [Vote Links](http://microformats.org/wiki/vote-links) microformat, because I think there is a huge need for them in [SEO](http://en.wikipedia.org/wiki/Search_engine_optimization) arena.

Currently search engines like [Google](http://www.google.com), [Yahoo!](http://www.yahoo.com), and [that other search engine](http://www.live.com/) (made by the same company that makes [that crappy browser](http://www.microsoft.com/windows/internet-explorer/download-ie.aspx) all primary rely on [PageRank](http://en.wikipedia.org/wiki/Pagerank), which determines the importance of a document by considering the importance of the documents that link to it. In PageRank, every link is valuable, except those links that use the [no follow link type](http://dev.w3.org/html5/spec/Overview.html#link-type-nofollow) (ie: any link without the nofollow link type is considered an endorsement). PageRank does not consider the possibility that document A might want to have a vote on document B's calculated importance, besides just the option of endorsing document B.

Enter the [Vote Links](http://microformats.org/wiki/vote-links) microformat. With this specification, website masters can now specify links on their web documents as votes for or against other web documents. You can also abstain from voting, ofcourse.

For example, you may have noticed that in my second paragraph I was taking a shots at the [Microsoft Corporation](http://www.microsoft.com/) (which I love to do) and if you look at the html markup, then you will notice that those links are votes against Live Search and Internet Explorer. So now I'm telling any user agent that visits this document that this document is a vote against those Microsoft products. This document is also a vote for some wikipedia articles, Google, Yahoo, and the VoteLinks microformat. That's a lot of knowledge that spiders can gain because of this markup, hopefully the search engine spiders start considering this microformat as a factor soon..

Anyhow, if you want to start using the VoteLinks microformat now, all you need to do is insert the following values into the rev attribute of your html anchor tags:

- vote-for: This signals that the current document is a vote for the href url of the anchor tag.
- vote-against: This signals that the current document is a vote against the href url of the anchor tag.
- vote-abstain: This signals that the current document is indifferent to the href url of the anchor tag.
