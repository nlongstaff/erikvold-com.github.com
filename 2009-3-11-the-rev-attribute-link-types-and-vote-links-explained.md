---
title: The Rev Attribute, Link Types, and Vote Links Explained
tags: Microformats, SEO, HTML, WebDev
---
<h2>Rev Attribute</h2>
<p>
The html rev attribute in my opinion is underused and incredibly useful.
In short the <a title="REV Atrribute - HTML 4.01 Specification" rel="external nofollow" target="_blank" href="http://www.w3.org/TR/html401/struct/links.html#adef-rev">rev</a> attribute is the reverse of the <a title="REL Atrribute - HTML 4.01 Specification" rel="external nofollow" target="_blank" href="http://www.w3.org/TR/html401/struct/links.html#adef-rel">rel</a> attribute.
Here are the <a title="HTML 4.01 Specification" rev="vote-for" target="_blank" href="http://www.w3.org/TR/html401/">HTML 4.01 specification</a> definitions:
</p><ul>
  <li>
		<a title="REL Atrribute - HTML 4.01 Specification" rel="external nofollow" target="_blank" href="http://www.w3.org/TR/html401/struct/links.html#adef-rel">rel</a>:
		This attribute describes the relationship from the current document to the anchor specified by the href attribute.
		The value of this attribute is a space-separated list of link types.
	</li>
	<li>
		<a title="REV Atrribute - HTML 4.01 Specification" rel="external nofollow" target="_blank" href="http://www.w3.org/TR/html401/struct/links.html#adef-rev">rev</a>:
		This attribute is used to describe a <a title="Forward and reverse links - HTML 4.01 Specification" rev="" rel="" target="_blank" href="http://www.w3.org/TR/html401/struct/links.html#rev-link">reverse link</a> from the anchor specified by the href attribute to the current document.
		The value of this attribute is a space-separated list of link types.
	</li>
</ul>
<p></p>

<p>
A few months ago I wrote about <a title="The Difference Between REL and REV attritbutes of the A Tag (or REL vs. REV) - Erik Vold's Blog" rev="vote-for" target="_blank" href="http://erikvold.com/blog/index.cfm/2008/8/20/the-difference-between-rel-and-rev-in-the-a-tag-or-rel-vs-rev">the difference between the rev and rel attribute</a> where I give an example which may help, and there is also a good example <a title="Difference between rel and rev attribute - HTML - Snipplr" rel="external nofollow" rev="vote-for" target="_blank" href="http://snipplr.com/view/6529/difference-between-rel-and-rev-attribute/">here</a>.	
</p>


<h2>Link Types</h2>
<p>
Link types are the values that can be used in the rel and rev attributes.
Some link types are old, some are new, some are microformats, others are used by search engine bots.
<a title="Link Types - HTML 4.01 Specification" rel="external" target="_blank" href="http://www.w3.org/TR/html401/types.html#h-6.12">This is the HTML 4.01 list of link types</a>, and <a title="Link Types - HTML 5 Specification" rel="external" target="_blank" href="http://dev.w3.org/html5/spec/Overview.html#linkTypes">this is the HTML 5 draft list of link types</a>.
</p>

<p>
Some of the link types added to the HTML 5 specification are: archives, author, external, feed, first, and many others. Some of the link types removed are: start, chapter, section, subsection, and a few others.  
</p>

<p>
The <a title="External Link Type - HTML 5 Specification" rev="vote-for" rel="external nofollow" target="_blank" href="http://dev.w3.org/html5/spec/Overview.html#link-type-external">external</a> and <a title="External Link Type - HTML 5 Specification" rev="vote-for" rel="external nofollow" target="_blank" href="http://dev.w3.org/html5/spec/Overview.html#link-type-nofollow">nofollow</a> link types were also added to the HTML 5 specification which have been widely used for some time now in the rel attribute for <abbr title="Search Engine Optimization">SEO</abbr> purposes.
The <a title="Tag Link Type - HTML 5 Specification" rev="vote-for" rel="external nofollow" target="_blank" href="http://dev.w3.org/html5/spec/Overview.html#link-type-tag">tag link type</a> was the better defined <a title="rel=&quot;tag&quot; Microformat" rel="external" rev="vote-for" target="_blank" href="http://microformats.org/wiki/rel-tag">rel="tag" microformat</a> before it was added to the HTML spec, however I expect and hope the microformat specification will continue.
The tag link type was created at Technorati, which they describe <a title="Using Technorati Tags - Technorati" rev="vote-for" rel="external nofollow" target="_blank" href="http://technorati.com/help/tags.html">here</a>, and <a target="_blank" title="How Tags Happened at Technorati" rev="vote-for" rel="external nofollow" href="http://www.powazek.com/2005/07/000532.html">this is how it was created</a>.  
</p>

<h2>Vote Links</h2>

<p>
The <a title="Vote Links Mocroformat" rev="vote-for" rel="external" target="_blank" href="http://microformats.org/wiki/vote-links">Vote Links microformat</a> are rev attribute values that I hope will become a link type in some future HTML specification.
These are three values described by the Vote Links microformat, they are:
</p><ul>
	<li>
		vote-for: Represents approval.
	</li>
	<li>
		vote-abstain: Represents abstention or indifference.
	</li>
	<li>
		vote-against: Represents disapproval. 
	</li>
</ul>
<p></p>

<p>
Currently I always rel="external nofollow" on any link that I will rev="vote-against", and rel="external" any link that I rev="vote-for" atleast once, which covers 75% of my links.
But there are other links which I want to be more specific about, and for me that is where the Vote Links microformat comes in handy, because I can vote-for a link that I also nofollow.
For example, I usually nofollow my links to Wikipedia (becuase it has so much <a title="Page Rank - Wikipedia" rel="external nofollow" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/PageRank">Page Rank</a> already) and use the vote-for microformat to show my support.
</p>

<h2>Conclusions</h2>

<ol>
	<li>The rev attribute has been widely misunderstood and misued, but it is very useful.</li>
	<li>There is a dramatic difference in the link types defined in the HTML 4 specification and the HTML 5 specification draft, but even some of the depricated link types appear useful to me.</li>
	<li>
		<a title="Absent Attributes - HTML 5 differences from HTML 4" rev="vote-against" rel="external" target="_blank" href="http://www.w3.org/TR/2008/WD-html5-diff-20080122/#absent-attributes">The rev attribute is not in the HTML 5 specification draft</a>, which is like removing the yang from a <a title="Yin and Yang - Wikipedia" rel="external nofollow" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Yin_and_yang">yin-yang</a>, and I have <a title="[uf-discuss] HTML 5, rev and votelinks" rel="external nofollow" rev="vote-against" target="_blank" href="http://microformats.org/discuss/mail/microformats-discuss/2008-January/011425.html">not</a> <a title="[whatwg] Absent rev?" rel="external nofollow" rev="vote-against" target="_blank" href="http://lists.whatwg.org/htdig.cgi/whatwg-whatwg.org/2008-November/017356.html">found</a> a good reason for it, only a few hints which reinforce my belief that it is not good idea.
	</li>
	<li>Vote Links rock!</li>
	<li>Between the HTML specification chaos and Microformats, this is the time where we all get to decide what we want to embrace, and let the HTML specification follow our lead.</li>
</ol>

		<a href="http://erikvold.com/blog/index.cfm/2009/3/11/the-rev-attribute-link-types-and-vote-links-explained#more" name="more" rel="nofollow"></a>
		
	</div>
	
<script type="text/javascript">
google_ad_client = "pub-5964377618444056";
google_ad_slot = "9885673634";
google_ad_width = 468;
google_ad_height = 60;
</script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"></script><ins style="display:inline-table;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px">
