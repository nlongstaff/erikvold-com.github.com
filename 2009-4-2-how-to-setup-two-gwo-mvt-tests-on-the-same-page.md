---
title: How to Setup Two GWO MVTs on the Same Page
tags: Testing, Google Website Optimizer
---
This is a follow up post to the one I did yesterday, where I explained how to go about <a title="How to Setup a GWO MVT Test and A/B Test on the Same Page" target="_blank" rev="vote-for" rel="external nofollow" href="http://erikvold.com/blog/index.cfm/2009/3/31/how-to-setup-a-gwo-mvt-test-and-ab-test-on-the-same-page">running a Google Website Optimizer a/b test and multivariate Test on the same page</a>. I mention this because I intend to skip a lot of the steps I explained in that post already to avoid repeating myself.
</p>
<h2>The Problem</h2>
<p>
Consider the following hypothetical scenarios:
</p><ul>
<li>
You have two areas of one page that you want to test different variations of, each of which have separate goals, so you would like to run two separate Multivariate Tests on the same page to track the results separately.
</li>
<li>
You have a site wide element that you would like to test, and a page specific element that you would like to test.
</li>
</ul>
<p></p>
<p>
In both of the above cases you will need to setup two multivariate tests on the same page.
</p>
<h2>The Solution</h2>


  	<a href="http://erikvold.com/blog/index.cfm/2009/4/2/how-to-setup-two-gwo-mvt-tests-on-the-same-page#more" name="more" rel="nofollow"></a>
		
<center>
<img src="/blog/images/posts/two-gwo-mvt-same-page-diagram.jpg" border="1">
</center>
<p>
In the above image, I point out that you have to mentally split the page into parts, where the number of parts is equal to the number of tests you want to run on the page. In the image I have Page A, which is split into two pieces for the two tests that will run on it, which are Part A for Test A and Part B for Test B. In order to setup two tests on the same page you must encapsulate the test in to it's corresponding part of the page. The tracking scripts however can all go at the bottom of the page in no particular order.
</p>
<p>
For help on setting up the tests in the GWO console, read the steps laid out on how to setup a <a title="How to Setup a GWO MVT Test and A/B Test on the Same Page" target="_blank" rev="vote-for" rel="external nofollow" href="http://erikvold.com/blog/index.cfm/2009/3/31/how-to-setup-a-gwo-mvt-test-and-ab-test-on-the-same-page">Google Website Optimizer a/b test and multivariate test on the same page</a>, they are pretty much the same.
</p>
<h2>The Example</h2>
<p>
<a title="Example of Two GWO MVTs on the same page" rel="example nofollow" target="_blank" href="http://erikvold.com/tests/gwo/gwo-multiple-mvt-tests-on-one-page/index.cfm">This is my example page</a>.
</p>
<h2>The Conclusion</h2>
<center>
<img src="/blog/images/posts/two-gwo-mvt-tests-single-page.gif" style="border:1px solid #000000;">
</center>
<p>
In the above image I have a screen shot of my example page of two tests on the same page with an interesting twist to make a point. The two tests have two sections, and the twist is that the two tests share a section name "Header 1".
</p>
<p>
Also on the test page, you will notice that I call utmx_section("Header 1") and utmx_section("Header 2") on the page twice, once at the top of the page after the first control script, and once towards the bottom of the page, after the second control script. The reason for this is to show you that the utmx_section function only works of the test of the most recent control script to be loaded.
</p>
