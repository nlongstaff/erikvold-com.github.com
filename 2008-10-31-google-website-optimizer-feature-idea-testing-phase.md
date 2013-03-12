---
title: Google Website Optimizer Feature Idea: Testing Phase
tags: Google Website Optimizer
---
<p>I've got an idea for a new Google Website Optimizer (GWO) feature, the testing phase. Think of this, what if we had 6 steps to the GWO setup, step five would be the 'testing' step, and step 6 would be the 'view report' step (the current fifth step).</p>

<p>Currently, in my experience setting up google website optimizer tests, after I press "Launch Now" on step 4, I sometimes feel like kissing a relic for good luck, then I go to the test page, confirm a combination was displayed as intended, then clear cookies, make sure I get a combination besides the complete original, and do a conversion, then I wait for 2 - 4 hours to confirm the exact data I expected came in, and then take a breath of relief. Does that sound like fun to you? Well I have pretty much mastered setting up GWO tests, and that's my emotional/'testing' pattern, almost every test (ignore preview for a moment please, for much greater than 50% of the tests I handle it is not enough)..</p>

<p>It's not the end of the world if a test doesn't work for me though, if this every does happen to me, I'm sure I'd be able to fix it so fast it wouldn't matter. The other option is to stop the test, copy it, fix it, start again.. more time just gets lost.</p>

<p>My idea is to have a the 'testing' step I mention above, I figure it would work something like this:
</p><ul>
<li>Step 4: Has two options 'test test' (step 5) 'launch test' (step 6). Or something that makes more sense.</li>
<li>Step 5: The GWO code does not run automatically as it would if it were a live test, but instead it would be triggered by a url variable like gwoTest=true.</li>
<li>Step 5: Data is retrieved lightening fast (not 3hrs waiting for data). I understand that there may have to be some limitations to this step, like it can only be run for a short time period of time, or for 10 (or x) visitors, then it shuts down (maybe we can restart a fresh too). Otherwise people might try to run real tests in the test mode for faster results. (This would be nice, might be impossible though..)</li>
