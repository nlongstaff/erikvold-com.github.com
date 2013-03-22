---
title: The Daily UserScript: Lightweight Twitter Account Manager
short URL: http://r.evold.ca/dailyus50
tags: Usability, UserScripts, Twitter, Daily UserScript, Automation, Productivity
---
This userscript is one that I have wanted myself for awhile now, because I manage a handful of twitter accounts now (<a title="Erik Vold - Twitter" rel="external" target="_blank" href="http://twitter.com/erikvold">@erikvold</a>, <a title="Vold Software Solutions - Twitter" rel="external" target="_blank" href="http://twitter.com/voldsoftware">@voldsoftware</a>, <a title="BetterGWO - Twitter" rel="external" target="_blank" href="http://twitter.com/bettergwo">@bettergwo</a>, and <a title="SuperbGA - Twitter" rel="external" target="_blank" href="http://twitter.com/superbga">@superbga</a>) and I have made a few mistakes where I thought I was in one account but was really in another and followed someone on the wrong account, or worse posted a tweet from the wrong account. Another reason that got me motivated was that I have not seen another userscript that did everything I wanted, and nor was there one that achieved what <a title="embøl - Userscripts.org" rel="external nofollow" rev="vote-for" target="_blank" href="http://userscripts.org/users/56901">embøl</a> was looking for as <a title="Twitter Multiple Account Manager" rel="external nofollow" rev="vote-for" target="_blank" href="http://userscripts.org/topics/36345">he describes on the userscripts.org forum</a>.
</p>

<p>However, as you will see this userscript is extremely useful to Twitter users with only one account as well.</p>

<h2>Screen Shot</h2>
<p>
<img alt="Screen shot of the Twitter Account Manager UserScript" src="http://farm3.static.flickr.com/2667/3981508522_f2aa7b86be.jpg">
</p>

<h2>The Unpleasantries:</h2>
<p>
</p><ol>
<li>It's not easy to tell which account you are logged into on every page.</li>
<li>It takes a number of steps to switch accounts. Signing out, focusing on input fields, retyping the same old username and passwords over and over again to log back in.</li>
<li>
It takes a number of steps to login initially in the first place, again focusing on input fields, retyping the same old username and passwords, yet again.
</li>
</ol>
<p></p>

<h2>The Alleviation:</h2>
<p>
Once you install the <a href="http://userscripts.org/scripts/show/59103" title="Twitter Account Switcher" rel="external nofollow" target="_blank" rev="vote-for">"Twitter Account Switcher" UserScript</a> all of the above stated unpleasantries are taken care of gracefully, and here is how it works:
</p><ul>
<li>
<p>First of all I have added a <i>username</i> url variable to the <a title="Twitter Login" rel="external nofollow" rev="vote-for" target="_blank" href="http://twitter.com/login">http://twitter.com/login</a> which will take the provided username and auto insert it into the username field on the login form, then focuses on the password field (which will kick Firefox's password manager in to action), after which it checks to see if a password was inserted and if so it automatically submits the login form. This means that when I go to <a title="@erikvold - Twitter Login" rel="external nofollow" rev="vote-for" target="_blank" href="http://twitter.com/login?username=erikvold">http://twitter.com/login?username=erikvold</a> (which I now have bookmarked) I will automatically be logged in; when you go to <a title="@erikvold - Twitter Login" rel="external nofollow" rev="vote-for" target="_blank" href="http://twitter.com/login?username=erikvold">http://twitter.com/login?username=erikvold</a> you will see "erikvold" in the username input field of the login form and the focus will be on the password input field because you do not have the password for my twitter.com account in your Firefox password manager, and if you use an incorrect password then you will receive an alert from twitter telling you so.
</p>
<p>
This is obviously good for all Twitter accounts because it allows you create totally safe auto login bookmarks for the accounts.
</p>
</li>
<li>
<p>
The second benefit is only useful to those Twitter users that manage multiple accounts, because it will help you switch between all of your accounts very simply. First you will notice that a new drop down menu was added in the top navigation to the right of Profile or Login link, depending on if you are logged in or not, this is the profile manager. By default it will display either "NULL" which does nothing, or the username of the account that you are currently logged into. To switch or choose an account to log in to quickly, just use this drop down menu.
</p>
<p>
Note: Once you install this userscript it will remember the username of every account which you successfully logged in to. You can also manually add usernames if you want to quickly create a long list, and if desired you can manually remove usernames from the username list, but remember that the username will be automatically added to the list if you log in to the account again.
</p>
</li>
</ul>
<p></p>

  	<a href="http://erikvold.com/blog/index.cfm/2009/10/4/the-daily-userscript-twitter-account-manager#more" name="more" rel="nofollow"></a>
		
	</div>
	
<script type="text/javascript">
google_ad_client = "pub-5964377618444056";
google_ad_slot = "9885673634";
google_ad_width = 468;
google_ad_height = 60;
</script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js"></script><ins style="display:inline-table;border:none;height:60px;margin:0;padding:0;position:relative;visibility:visible;width:468px">
