---
title: Some more help for those still confused by rev="canonical"
tags: Usability, Internet, SEO, HTML, Programming, WebDev
---
I just read an interesting comment by one of the fieriest rev=canonical opponents <a title="Sam Johnson" rel="external nofollow" rev="vote-against" target="_blank" href="http://samj.net/">Sam Johnson</a>  where he explains his confusion <a rev="external nofollow" target="_blank" href="http://annevankesteren.nl/2009/04/rev-canonical#comment-6774">here</a>, by saying:
</p>
<blockquote>
<p>I'm surprised the rev=canonical guys are still banging on about this... nobody outside of the web developer community has a good word to say about it and it's been universally criticised by the standards community (with good reason).

</p><p>rev=canonical is saying "I'm the canonical URL and that URL over there points at me". That means it must only ever be used on the canonical URL itself - too bad for an infinite number of potential permutations. Then there's the likes of Matt Cutts pointing out that one should give, not take, canonical-ness but Chris Shiflett (one of the primary promoters) <a target="_blank" href="http://shiflett.org/blog/2009/apr/a-rev-canonical-http-header">foolishly dismisses</a> this feedback as "irrelevant". Mark Nottingham is more direct in <a rel="external nofollow" target="_blank" href="http://www.mnot.net/blog/2009/04/14/rev_canonical_bad">Counting the ways that rev="canonical" hurts the Web</a> but the rev=canonical fanboys cite this as "evidence that those writing the standards are going off track".

</p><p>I suggest rel="<a rel="external nofollow" target="_blank" href="http://code.google.com/p/shortlink/">shortlink</a>" as an unambiguous solution to this fiasco - the short[_- ]?ur[il] option has more permutations than can easily be counted and delivers no additional value.

</p><p>In order to discourage people from supporting many variations I'm now serving up warnings and errors when rev=canonical and rel=short*ur? are discovered at <a rel="external nofollow" target="_blank" href="http://rel-shortlink.appspot.com/">http://rel-shortlink.appspot.com/</a>.
</p><p>Sam</p>
</blockquote>
<p>
Well that is wrong and <a rel="external" rev="vote-for" target="_blank" href="http://annevankesteren.nl/2009/04/rev-canonical#comment-6775">here</a> is my response:
</p>


  	<a href="http://erikvold.com/blog/index.cfm/2009/4/22/revcanonical-is-as-clear-as-day#more" name="more" rel="nofollow"></a>
		
<blockquote>
Sam your understanding of "canonical" is <strong>completely incorrect</strong> (it's ok though, it seems like there is a huge opposition that is making the same naive mistake). rev=canonical does not have to be restricted to being used on the canonical url itself, because if it is not the canonical then it will have rel=canonical (but doesn't have to), and rev=canonical actually is saying is "my canonical represents this" (here is another way to think of rev=canonical: "this document's canonical represents that"), and what rel=canonical is actually saying is: "that is my (this document's) canonical" (thus it can be used on the canonical url itself).

<p></p><p>
Furthermore, your understanding of rev seems to be off the mark in this instance, under your understanding of rev=canonical it would be saying: "this document is the canonical" and "this document's canonical is represents that". That is utterly wrong. It is impossible for the rev attribute to say "this document is <strong>the (as in the one and only)</strong> canonical for that", it could be interpreted as "this document is <strong>a</strong> canonical for that" (as you do) but that breaks the definition of "canonical", and in light of the def of canonical, "this document's canonical represents that" is the only interpretation that makes sense.

</p><p>
I know that many will be tempted to blame the confusion on  the rev attribute, but really you all get rev, it's when a value comes in to play that you don't understand, like 'canonical' for instance.

</p><p>Just because you are confused does not mean your solution is better.

</p><p>
Please read my deeper explanation here: <a title="Counting the ways rev=canonical helps the Web and a rel=short* rebuttal" href="http://erikvold.com/blog/index.cfm/2009/4/21/rev_canonical_good">Counting the ways rev="canonical" helps the Web and a rel="short*" rebuttal</a>. It rebuttals the rest of your comment.

</p>
</blockquote>
<p>Then I had to follow that up with:</p>
<blockquote>
<p>I apologize Sam, where I say "(as you do)", that is incorrect.
</p><p>We agree that rev=canonical cannot be allowed to be interpreted as you described though, I just see a interpretation of rev=canonical that is more accurate, that I would like to hear rebuttals for, instead of rebuttals for the interpretation you put forward, because we agree there. And Matt Cutts only point against rev=canonical is this point you and I agree on.
</p>
</blockquote>
<p>
Then I messed up again, and had to say (last one Anne I promise):
</p>
<blockquote>
Sigh, apologies to Matt now, his argument is more than just the point I mentioned in the last comment, but I can take care of the rest of his argument by saying simply verify rev=canonical by checking for a rel=canonical. 
</blockquote>
<p>
I hope this helps the rest of those that are confused.
</p>
	</div>
	
<script type="text/javascript">
google_ad_client = "pub-5964377618444056";
google_ad_slot = "9885673634";
google_ad_width = 468;
google_ad_height = 60;
</script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"></script><ins style="display:inline-table;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px">
