---
title: The Difference Between REL and REV attributes of the A Tag (or REL vs. REV)
tags: Microformats, SEO, HTML, Programming
---
<p>I recently took some time to clear up the difference between the rel and rev attributes of the A tag, and I thought it would make a decent post, because I don't think many people have taken the time yet.</p>

<p>The "rel" attribute indicates the relationship of the target (the link in the href attribute) to the page. The "rev" attribute is the opposite of the "rel" attribute, that is, it indicates the relationship of the page to the target.</p>

Example 1a:
<div class="code">&lt;a title="Help Page" rel="help" href="/help.cfm"&gt;Help&lt;/a&gt;</div>
<p>I read the above line is English as: "/help.cfm is the 'help' page of this page".</p>

Example 1b:
<div class="code">&lt;a title="Some Form" rev="help" href="/someForm.cfm"&gt;Go to form&lt;/a&gt;</div>
<p>I read this example is English as: "This page is the 'help' page of /someForm.cfm"</p>

<p>Note: One exception to the rule is the keyword 'alternate' which implies a bi-directional relationship, rather than the single direction relationships in examples 1a&amp;b.</p>

<p><a title="Vote Links" rev="vote-for" href="http://microformats.org/wiki/vote-links">VoteLinks</a> is a very interesting use of the "rev" attribute that I hope everyone will consider using, I may go into it later, but check it out anyhow!</p>

  	<a href="http://erikvold.com/blog/index.cfm/2008/8/20/the-difference-between-rel-and-rev-in-the-a-tag-or-rel-vs-rev#more" name="more" rel="nofollow"></a>
		
	</div>
	
<script type="text/javascript">
google_ad_client = "pub-5964377618444056";
google_ad_slot = "9885673634";
google_ad_width = 468;
google_ad_height = 60;
</script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"></script><ins style="display:inline-table;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px">
