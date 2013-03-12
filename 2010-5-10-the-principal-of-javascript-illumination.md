---
title: The Principle of JavaScript Illumination
short URL: http://r.evold.ca/jsillume
tags: UX, Internet, Javascript, Programming, WebDev
---
Every web developer knows that their site should work when the site's users disables JavaScript, but I constantly find this principal is violated when it is simple thing to obey. When web UI developers violate this principal it shows an extreme laziness and a failure to understand good practices on their part; this can greatly worsen the user experience. So, I'd like to articulate what I'm going to call <strong>The Principle of JavaScript Illumination</strong> which is an idea I haven't seen articulated yet, but that everyone knows in their gut they should do, and yet I hardly ever see this principal adhered to in practice.
</p>

<h2>Definition</h2>
<p>
<strong>The Principle of JavaScript Illumination</strong> is a simple one, if some user interface element will not work when JavaScript is disabled, then have JavaScript add the element.
</p>

<h2>Implications</h2>
<p>
If you have a user interface (UI) element that uses JavaScript, then make sure there is a default functionality that will work when JavaScript is disabled. If the UI element cannot work at all without JavaScript, then you should make JavaScript add the element, this way if JavaScript is disabled then the user will not see UI elements that will not work, causing a bad user experience.
</p>

<h2>Examples</h2>

<h3>Facebook Chat</h3>
<p>
When you log in to Facebook with JavaScript disabled, the chat widget is displayed to you on the bottom right of the screen, but it doesn't do anything, it's completely useless to you and it's just in the way, so why the heck is it displayed to the user?
</p>

<h3>Kampyle</h3>
<p>
<a title="Kampyle" rel="external nofollow" rev="vote-against" target="_blank" href="http://www.kampyle.com/">Kampyle</a> provides some widget code for anyone to put on their site which adds a "Give Feedback" button to the bottom right of the user's screen, which the user can click on to give feedback for the site. The trouble is, when JS is disabled, or when the user uses NoScript to block assets from the kampyle.com domain, then the button doesn't work (see <a title="ROIRevolution" rel="external nofollow" target="_blank" href="http://roirevolution.com">ROIRevolution</a>'s site for an example of this), so why the heck is it displayed to the user?
</p>

<h2>Conclusion</h2>
<p>Be a good web citizen, and a smart web developer by obeying <strong>The Principle of JavaScript Illumination</strong>, because it's the right thing to do and because you're users will thank you for it.</p>
