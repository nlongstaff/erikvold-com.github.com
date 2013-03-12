---
title: My Solution to the Alt-Tab Problem
short URL: http://r.evold.ca/alttab
tags: Usability, UX
---
While I was reading through my subscriptions the other day I noticed Aza Raskin's recent blog post, <a title="Solving the Alt-Tab Problem" rel="external" target="_blank" href="http://www.azarask.in/blog/post/solving-the-alt-tab-problem/">"Solving the Alt-Tab Problem"</a>, where he describes issues with the current alt-tab implementation which orders the applications by Most Recently Used (MRU), please take a moment to read his very detailed post before continuing with this post.
</p>

<p>
I thought this was a very interesting problem. I've personally always hated the way that alt-tab works, and hardly ever use it because of this, even though I know it should be helpful, it just is not. So, I thought a bit about this in the back of my mind and I finally came up with a solution that I like, and I haven't seen it mentioned yet so I will explain it here, but first I want to list the issues Aza mentioned with MRU and my main issue with it, then I'll quickly describe some of the other solutions I've heard, and finally I'll give you my solution.
</p>

<h2>Issues With MRU</h2>
<ul>
<li>Switching between 3+ applications is brutal (see Aza's post).</li>
<li>Constant seethings of MRU confound a person's strong spatial memory (see Aza's post).</li>
<li>Thinking about how to switch tabs rips a person's attention from their real task (see Aza's post).</li>
<li>If a user presses alt-tab, then decide they made a mistake and want to return to the application that they were using before pressing alt-tab, then they need press alt-shift-tab, because if they just let go of the alt key, then they will be switched to the last application that they used (my issue).</li>
</ul>

<p>
The first and last issues listed above are the two main reasons why I never use alt-tab today.
</p>

<h2>Proposed Solutions</h2>
<h4>Aza's HRMRU</h4>
<p>
In Aza's post he mentions a possible solution, which he admits he doesn't think is great, which is a <strong>habit respecting design</strong> which he dubbed HRMRU. HRMRU is basically a prediction algorithm which allows the computer to try to predict the order that you desire (read his post for a full explanation). He mentioned the possibility of using a <a title="Markov mode" rel="external nofollow" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Hidden_Markov_model" data-source="Wikipedia">Markov model</a>, but an HRMRU could be implemented an infinite number of ways.</p>

<p>The way that HRMRU is implemented doesn't really matter imo, throughout my time at UBC studying statistics and computer science (with a focus on machine learning), and the rest of my life, I haven't seen an algorithm that would be suitable to implement HRMRU, indeed I wouldn't trust a human being with all of the time in the world to predict my habits (in this context). Furthermore, if some HRMRU method were implemented, then in order to switch applications in the blink of an eye I would have to predict the predictions made by the HRMRU implementation, and that would a terrible user experience. My last issue with this solution is that it would bog down my machine; I absolutely hate it when applications use cpu cycles when it is not necessary, when that happens I start losing control of myself, and I seriously want to start bitching at the developers, because it's what they deserve (if they didn't give me the option of turning their crappy code off).
</p>

<h4>Lukas Mathis' Solution</h4>
<p>
I'm not sure what to call Luka's solution, but he explains it <a rel="external nofollow" rev="vote-against" target="_blank" href="http://ignorethecode.net/blog/2010/05/05/solving_the_alt_tab_problem/">here</a>. Basically his idea is to have the currently open application in the second position, and the last application opened in the first position, and the rest are listed in positions 3 and on. Read his post for full details.
</p>

<p>This solution would solve the last issue listed above, but does not solve the other issues.</p>

<h3>Others</h3>
<p>
In the comments of Aza's post I saw a number of other options/~solutions mentioned, some of which I think are worth mentioning here, which I'll do as best as I can. There are other solutions mentioned in the comments of Aza's post though, so don't assume this is a comprehensive summary, because it's quite far from that.
</p>

<h4>Constant Order</h4>
<p>This solution is very simple, the applications are listed in the same order that they were opened.</p>
<p>
Truth be told I think this was the best solution mentioned in the long list of comments on Aza's post, it's even better than MRU, it takes care of all issues except for allowing quick application switching, which happens to be very important.
</p>

<h4>alt-tab-mouse</h4>
<p>
This is implemented on OSX and the windows alt-tab power toy (maybe winXP too I haven't checked). It's a simple solution, the user presses alt-tab, then uses their mouse to select the desired application. 
</p>
<p>
This is a great solution, there is no doubt about it, but switching from keyboard to mouse all of the time is a terrible user experience, so a fully keyboard based solution is a must have, so this is only really part of a solution. Also, switching between 3+ applications in the blink of an eye is not possible with this solution, so it's just not enough.
</p>

<h4>Application Grouping (Activity Grouping)</h4>
<p>
I didn't really bother figuring out how this solution is supposed to work, as I understand it though you'll be able to group applications together, then some how you're able to switch quickly between applications..
</p>
<p>
Albeit, I don't fully understand this idea, and may not fully appreciate it, but it doesn't sound great to me. Presumably I would have to switch group/activity, then choose an application, and how I would do this isn't clear to me. This does sound like it could be an option, but it sounds like switching between 3+ apps may still be an issue, or at least it's not something that you could do in the blink of an eye.
</p>

<h4>Number the Listed Applications</h4>
<p>
This idea is simple, number or letter each open application (with 0-9 and a-z, then nothing). This way a user can alt-tab, then hit the number/letter associated to the desired application.
</p>
<p>
I like this solution.
</p>

<h2>My Solution</h2>
<p>
To start with I think a few of the solutions mentioned above should be implemented, namely the alt-tab-mouse solution, the lettering of the first 26 open applications, and ordering the applications by the order that they were opened.
</p>
<p>
Obviously, I think that if the user presses alt-tab then lets go of these keys, then I don't think the application should be changed. Also, I think the user needs to be able to customize the order that the applications are ordered (the default ordering would be the order they were opened, and this would be customizable on the fly), so the question is how should the user be able to do this? well I thought of a couple ways, one is to use the mouse to change the order via drag &amp; drop, and the keyboard method I thought up was to incorporate the ctrl key. To change the order of the applications by keyboard only a user would simply move the selection box to the application that they want to move (so alt-tab or alt-shift-tab to the application, while holding the alt key) then they hold the ctrl key along with the alt key which 'picks up' the application, and then the user could press alt-ctrl-tab to move it right, or alt-ctrl-shift-tab to move the application left.
</p>
<p>
Now when the user presses alt-tab the currently focused application will be selected, and they can quickly alt-tab to switch to the application to the right, or alt-shift-tab to switch to the application to the left, and they can manually alter the order of the applications to something suitable for them at that moment in time. 
</p>

<p>
There should also be a separate key for switching back and forth between the last application used, I don't care what it is, maybe alt-tab-`, it doesn't matter I think. It would also be nice if the last application used was easy to spot in the alt-tab list somehow, so that the user could slow down and ensure that they are going to the right application before switching, so in this case they would press alt-tab, then hold tab see the last application used, and then press ` to select it and then they just let go of the alt key to switch to it.
</p>

<p>
Finally, I've got another set of hotkeys that I think will help, which are to use the numbers 1-5 or 1-9 such that the user can quickly switch to the application that is some # positions away from the currently application in the alt-tab list by pressing alt-# or alt-shift-# (ie: pressing a number while holding alt) which would select the application some # of positions to the right or left of the current application (ie: pressing tab while holding alt is equivalent to pressing 1), and if the desired application is 100 positions away or whatever, then they just press alt-tab-5 20x, or reorder the list so that they don't have to do that every time. This may sound bad for a large number of applications, but that'll be the case with any solution, even HRMRU.
</p>

<p>You'll notice that all of the issues listed above are solved, and the code would be lightening fast, the only issue I see is that unless you've read about these hotkeys you may not find them, but alt-tab will still work, and be useful.</p>
