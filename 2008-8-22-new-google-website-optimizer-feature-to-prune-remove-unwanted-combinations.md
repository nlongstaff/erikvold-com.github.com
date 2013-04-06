---
title: New Google Website Optimizer Feature to Prune/Remove Unwanted Combinations
tags: Google Website Optimizer
---
[Google Website Optimizer](http://www.google.com/websiteoptimizer/) has had several updates in the works, the most notable, in my opinion, is the ability to remove or prune unwanted combinations.

Now, an unwanted combination can mean a lot of different things, so to be specific I'm going to assume that the only time someone would no longer want to test a combination is if the combination is losing.

In this case, the important question is: how do I know that a combination is losing enough that I can say it is a statistically a loser? and therefore worthy of being dropped/removed/pruned.

Well in order to answer that question you need only review the [Margin of Error](http://en.wikipedia.org/wiki/Margin_of_error) (MOE) of your combinations. What this can tell you is which combinations have a statistically significant difference over other combinations. This is done simply matching up error margin's and checking if they overlap, if they do, the the difference is not statistically significant, but if the two error margin's do not overlap, then the difference (in conversion rate) can be considered statistically significant.

So let's make up an example, say we have the following data on six combinations:

1. Combination 1: Conversion Rate: 25% +/- 5.5%
1. Combination 2: Conversion Rate: 40% +/- 6%
1. Combination 3: Conversion Rate: 35% +/- 5.7%
1. Combination 4: Conversion Rate: 15% +/- 6%
1. Combination 5: Conversion Rate: 22% +/- 5.8%
1. Combination 6: Conversion Rate: 12% +/- 7%

Well in the above results, it's clear that Cominbation 2 is leading, and that combo 2 is not significantly different from combo 3, but it is doing significantly better than the rest of the combinations, statistically speaking. So they could all be removed. And that would help us determine a winner between combo 2 and combo 3 more quickly, obviously.

And remember, the moment the MOE's cease to overlap is not a good time to prune a combination, wait a bit, until your pretty confident the MOE won't overlap again, because it hasn't overlapped for sometime, and the MOE has had time to narrow.

Thanks [Google](http://google.com)!
