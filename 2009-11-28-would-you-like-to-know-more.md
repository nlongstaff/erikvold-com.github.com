---
title: Would You Like To Know More?
short URL: http://r.evold.ca/knowmore
tags: Learning, Ubiquity, Information Architecture, Wikipedia, Internet, UserScripts, Usability, Jetpacks, Microformats, HTML, Productivity, WebDev, Daily UserScript
---
This is just a last moment idea inspired by the movie <a title="Starship Troopers" rel="external info" target="_blank" href="http://en.wikipedia.org/wiki/Starship_Troopers_%28film%29">Starship Troopers</a> which flashed in to my mind a couple of days ago as I was thinking about Jetpacks for the <a title="Jetpack for Learning Design Challenge" rel="external info" target="_blank" href="http://design-challenge.mozillalabs.com/jetpack-for-learning/">Jetpack for Learning Design Challenge</a>. It is primarily a Microformat/Link Type proposal for rel-info with some ideas and prototypes demonstrating how it could be used.
</p>
<h2>Abstract</h2>
<p>
When you are reading something on the web there are usually pages which exist elsewhere on the web that would provide background information, and further reading if you desired to dig deeper into the subject(s) you are reading about. Sometimes some of those pages are linked to from the article you are on, but often the link wouldn't make sense in the context of the content, and using a link tag isn't very useful to a user, so the link is not made.
</p>
<p>
I propose a rel-info <a title="HTML 5 Link Types" rel="external info" target="_blank" href="http://dev.w3.org/html5/spec/Overview.html#linkTypes">link type</a>, even if just as a Microformat, for 'a' and 'link' tags to provide a link to context-sensitive information.
</p>
<p>
With rel-info a user can read more about the Movie that was discussed at Netflix or IMDB easily for example, because the publisher (or a script the user subscribes to, more on this later) provided a rel-info link which the user can easily find and follow with a Jetpack, Firefox extension, or some other browser extension.
</p>
<h2>Proposal</h2>
<p>
When rel-info links are provided on a page browser extensions can easily extract them from the page, which can lead to <strong>a large number of use cases</strong>, of which I am sure I have only just scratched the surface. There is another side to this coin however which is that <strong>there are a large number of ways that rel-info links might be added to a page</strong>.
</p>
<p>
Let's explore the latter case, first the person who published the page could add rel-info links, but then browser extensions could add rel-info links, they could also search for and remove rel-info links. A user could subscribe to a person's or institution's suggestion feed or script which adds and/or removes rel-info links to pages, along with using a AI based browser extensions to add rel-info links.
</p>
<p>
When the rel-info links are going to be consumed there are some other interesting possibilities, for example a browser extension could filter the links by a HTML 5 'data-topic' attribute by keeping a list of topics that the user dislikes or likes, the domain could also be used for filtering. A browser extension could allow the user to mark pages as read so that they are removed from pages in the future as another example.
</p>
<h2>Prototypes</h2>
<p>
To test this link type out with a Jetpack I first had to add it to some pages, so I decided to write a couple of UserScripts to do this demonstrating how they can be dynamically added to pages by anyone even users themselves. The first userscript was to <a title="Make All IMDB Title Links Info Links" rel="external" target="_blank" href="http://userscripts.org/scripts/show/62882">add the rel-info link type to IMDB links</a>, and another to <a title="Make All Wikipedia Links Info Links" rel="external" target="_blank" href="http://userscripts.org/scripts/show/62878">add the rel-info link type to Wikipedia links</a>.
</p>
<p>
If you install the above UserScripts then you should find rel="info" or rel="... info" on your IMDB and Wikipedia links. Once you have done that you can check out and install the <a title="Would You Like To Know More?" rel="external" target="_blank" href="http://jetpackgallery.mozillalabs.com/jetpacks/163">"Would You Like To Know More?" Jetpack</a>. This is a slidebar Jetpack, and when you open this slidebar the focused tab is then scanned for rel-info links, if any are found then they are displayed in a list for you to choose from, if you click one of the provided links a new tab will be opened for the new page.
</p>
<p>
These UserScripts and the Jetpack take advantage of HTML 5 'data-' attributes, by adding a 'data-source' attribute to the rel-info links added on the userscript side, which the jetpack was written to check for and display if found. This is an example of how HTML 5 'data-' attributes can be used with the rel-info link type which I propose to create more interesting results.
</p>
