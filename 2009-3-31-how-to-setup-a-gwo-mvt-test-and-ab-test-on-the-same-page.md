---
title: How to Setup a GWO MVT Test and A/B Test on the Same Page
tags: Testing, Google Website Optimizer
---
<h2>The Problem</h2>
  	<p>
		I was recently asked if it was technically possible to setup a A/B Test and Multivariate Test on the same page with Google Website Optimizer.
		I had to think about it for a moment, I knew that one could run multiple tests on the same site with <abbr title="Google Website Optimizer">GWO</abbr> already, so I knew the utmx cookie must be able to remember multiple tests.
		So I thought it must work as long as one is careful about the way that he applies the code to the page, so I let the person know I was pretty sure it would work.
		Soon after I had whipped up a sample to give it a whirl and it worked perfectly, so I had my proof.
		</p>
		<h2>The Solution</h2>
		

		<a href="http://erikvold.com/blog/index.cfm/2009/3/31/how-to-setup-a-gwo-mvt-test-and-ab-test-on-the-same-page#more" name="more" rel="nofollow"></a>
		
		<p>
		I am going to describe how to setup a A/B test and MVT test on the same page at the same time, but they don't have to be implemented at the same time, and the steps really aren't much different.
		</p>
		<p>
			</p><ol>
				<li>
					Setup your A/B test normally.
					So now you will have a Page A and and Page B.
				</li>
				<li>
					Create your MVT test.
					<ol>
						<li>
							Use the Page A url for the test as you normally would.
						</li>
						<li>
							Put the control script for the MVT test under the control script for the A/B test, and tag the rest of the Page A normally.
							Then put the code in the corresponding places on Page B.
						</li>
						<li>
							Create a dummy/copy page of Page A without the A/B test markup (it should now only have the MVT test markup on it).
						</li>
						<li>
							Hit the validate button in the image below, it will fail, the warning messages don't matter.<br>
							<img title="GWO MVT Setup Validation Page" alt="Screen shot of Google Website Optimizer's MVT validation step" src="http://erikvold.com/blog/images/posts/mvt-setup-screen-one.gif" border="0"><br>
							There should be a link beside the validate button now named "Test page not accessible? Try offline validation &gt;&gt;", press it and upload a copy of the conversion page and your dummy page of Page A.
							This will pass validation if you did it right.
						</li>
						<li>
							Create your variations for the MVT normally.
							Save and continue when your done.
						</li>
						<li>
							Preview if you would like, then launch and your done!
						</li>
					</ol>
				</li>
			</ol>
		<p></p>
		<h2>The Example</h2>
		<p>
		I have setup some sample pages if you would like to review my code.
		This is my <a title="Page A" rel="nofollow" target="_blank" href="http://erikvold.com/tests/gwo/gwo-ab-mvt-tests-on-one-page/index.cfm">Page A</a>, this is my <a title="Page B" rel="nofollow" target="_blank" href="http://erikvold.com/tests/gwo/gwo-ab-mvt-tests-on-one-page/indexb.cfm">Page B</a>, this is my <a title="Conversion Page" rel="nofollow" target="_blank" href="http://erikvold.com/tests/gwo/gwo-ab-mvt-tests-on-one-page/end.cfm">Converison Page</a>, and this was my <a title="Dummy Page of Page A" rel="nofollow" target="_blank" href="http://erikvold.com/tests/gwo/gwo-ab-mvt-tests-on-one-page/dummy-page-for-mvt-setup.cfm">Dummy Page A</a>.
		I will be leaving the tests running for the time being, so for a short time you may want to disable javascript in order to view the source code.
		</p>
		<h2>The Conclusion</h2>
		<p>
		So to conclude it seems that it is possible to have multiple tests on the same page, but it takes some careful thought.
		Although this example of a MVT test running on a A/B test is relatively simple to setup, I hope this post helps you if you ever want to give multiple tests on the same page a try.
		</p>
		<p>
		Some of you may be thinking at this point "I knew that I could run multiple tests on the same site, but I thought I read/heard some place or other that you could not run two tests on the same page.." and I understand that
		What scarce little I have been able to find on the subject seems to be far less specific about the limitations on running multiple tests on the same page then I would like to see.
		</p>
		<p>
		For instance the first example I found was the book <a title="Always Be Testing the Complete Guide to Google Website Optimizer" target="_blank" rel="external nofollow" href="http://www.scribd.com/doc/11765261/Always-Be-Testing-the-Complete-Guide-to-Google-Website-Optimizer">"Always Be Testing the Complete Guide to Google Website Optimizer"</a>, which says on page 294: "Is it possible to have more than one test going on a given test page? No, that's not something Website Optimizer currently allows, at least not without some major hacking.".
		Now would you call the above solution major hacking? I wouldn't.
		</p>
		<p>
		Another example is in the <a title="Google Website Optimizer Help Forum" rev="vote-for" rel="external nofollow" target="_blank" href="http://www.google.com/support/forum/p/websiteoptimizer?hl=en">GWO Help Forum</a>, someone asked the question <a title="Is there a way to run multiple optimizer tests on a single page?" rev="vote-against" rel="external nofollow" target="_blank" href="http://www.google.com/support/forum/p/websiteoptimizer/thread?tid=333e98d4a19bb684&amp;hl=en">"Is there a way to run multiple optimizer tests on a single page?"</a> and <a title="Trevor Claiborne Profile" rel="external nofollow" target="_blank" href="http://www.google.com/s2/profiles/113167956230175580065?hl=en">Trevor Claiborne</a> responded with this interesting contradiction "You cannot have two experiments running on the same page at the same time. Your site using a tabbed interface may allow for you to pull this off however.".
		</p>
		<p>
		I suspect the reasoning behind these people saying that multiple tests on the same page is not possible, is that some situations are not possible without some real code hacking, but it is possible, I have just proved that, and like I will show below so has Eric Vasilik long before me.
		</p>
		<h2>The Bonus (Multiple Conversions)</h2>
		<p>
		<a title="Eric Vasilik" rel="external" rev="vote-for" target="_blank" href="http://www.ericvasilik.com">Eric Vasilik</a> has written a post at <a title="Google Website Optimizer Tricks" rel="external" rev="vote-for" target="_blank" href="http://www.gwotricks.com/">gwotricks.com</a> on <a title="Multiple Goals - GWO Tricks" rel="external" rev="vote-for" target="_blank" href="http://www.gwotricks.com/2009/01/multiple-goals.html">how to track multiple goals for a single test</a> which is using the fact that multiple tests can be run on the same site or page to create a shadow test which achieves the goal of having multiple conversions.
		I read this before I was asked the A/B+MVT question by the client I mentioned and it gave me the insight I needed I feel to try this out, because it is basically the same idea, running two tests on the same page.
		In Eric's multiple goal solution though, he wrote custom code to modify the utmx cookie which is what allows one test to shadow another.
		</p>
