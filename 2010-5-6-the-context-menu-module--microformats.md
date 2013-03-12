---
title: The Context Menu Module & Microformats
short URL: http://r.evold.ca/jp4micro
tags: Information Architecture, Microformats, Jetpack, Jetpacks
---
<a target="_blank" title="The Context Menu Module &amp; Microformats" rel="external" rev="vote-for" href="http://mozillalabs.com/jetpack/2010/05/03/context-menu-module-microformats/">Originally posted on Mozilla's Jetpack Blog</a>
</p>

<p>The Jetpack team recently released a context menu module in <a title="Jetpack SDK 0.3" rel="external" rev="vote-for" target="_blank" href="http://mozillalabs.com/jetpack/2010/04/29/announcing-jetpack-sdk-0-3/">version 0.3 of the Jetpack SDK</a>. This post will discuss the context menu module’s features and how it can be used to create an extension that allows users to interact with microformatted data on the web.</p>
<h2>Microformats</h2>
<p>If you are familiar with microformats, you can skip this section. In case you are not familiar with <a title="microformats" rel="external" target="_blank" href="http://microformats.org">microformats</a>, they are simply specifications on how to pattern commonly published data (contacts, events, reviews, etc.) in HTML so it can be easily consumed. <span id="more-382"></span></p>
<h3>hCard, geo, &amp; adr</h3>
<p>Take <a title="hCard Microformat" rel="external" target="_blank" href="http://microformats.org/wiki/hcard">the hCard microformat specification</a> for example, an hCard represents a person, organization, or place and includes information such as a name, contact info, address info, and perhaps their geo coordinates all in HTML. Here is an example of a microformat that contains this information:<br>

<br>
&lt;div class="vcard"&gt;<br>
&lt;a class="fn org url" href="http://www.commerce.net/"&gt;CommerceNet&lt;/a&gt;<br>
&lt;div class="adr"&gt;<br>
&lt;span class="type"&gt;Work&lt;/span&gt;:<br>
&lt;div class="street-address"&gt;169 University Avenue&lt;/div&gt;<br>

&lt;span class="locality"&gt;Palo Alto&lt;/span&gt;,<br>
&lt;abbr class="region" title="California"&gt;CA&lt;/abbr&gt;<br>
&lt;span class="postal-code"&gt;94301&lt;/span&gt;<br>
&lt;div class="country-name"&gt;USA&lt;/div&gt;<br>

&lt;/div&gt;<br>
&lt;div class="geo"&gt;Geo Coords:<br>
&lt;span class="latitude"&gt;37.386013&lt;/span&gt;<br>
&lt;span class="longitude"&gt;-122.082932&lt;/span&gt;<br>
&lt;/div&gt;<br>
&lt;/div&gt;
</p>

<h2>The Context Menu Module</h2>
<p>You can find documentation and further details on the context menu module here. The primary feature of the context menu module is the ability to create items in the context menu that are shown when right clicking on various content within the browser or a web page. CSS is used to specify in which contexts your new context menu items will appear. If you create a new context menu item whose context is set to “a” then the menu item will appear in all menus shown when the user right-clicks a link.</p>
<h2>Bring The Two Together</h2>
<p>The combination of microformats and the context menu module makes many practical Jetpack ideas possible. When websites microformat data on their site, and users have extensions installed in their browser which allow for consumption of microformatted data, users productivity can be greatly enhanced.</p>
<p>Even when a website does not microformat data on its pages, <a title="Jetpack Page Mods vs. User Scripts" target="_blank" href="http://mozillalabs.com/jetpack/2010/04/01/jetpack-page-mod-vs-user-script/">a user script or a Jetpack Page Mod</a> can be written to enhance the data on those pages with microformatting.</p>
<h2>An Example</h2>
<p>In order to show you how useful and extension that combines microformats and Jetpack’s context menu module is, I have created a jetpack-based extension which adds a ‘Find on Google Maps’ menu item to the context menu when the user right clicks on a <a title="geo - microformat specification" target="_blank" href="http://microformats.org/wiki/geo">geo</a> or <a title="adr - microformat specification" target="_blank" href="http://microformats.org/wiki/adr">adr</a> microformat – <em>geo is used for geo coordinates, and adr for addresses</em>. When the user clicks the extension’s context menu item, the targeted geo coordinate or address is displayed on <a title="Google Maps" rel="external nofollow" target="_blank" href="http://maps.google.com/">Google Maps</a> in a new tab. You can <a title="Find on Google Maps - Firefox Extension" target="_blank" href="https://addons.mozilla.org/en-US/firefox/addon/153353/">find this extension here on AMO</a>, as well as <a target="_blank" href="http://github.com/erikvold/googlemaps4microformats-jetpack">the source code here</a>. The bulk of the source code is &lt; 50 lines.</p>

<h2>Summary</h2>
<p>If you maintain a website that isn’t properly tagged with microformats I would suggest you consider adding them to your content.  If you are a user that notices a site that hasn’t properly tagged their site then you can either request that they do so, or write either a user script or page mod that does so for you. Once you have microformatted data you can then write &amp; use extensions to interact with the data.</p>
