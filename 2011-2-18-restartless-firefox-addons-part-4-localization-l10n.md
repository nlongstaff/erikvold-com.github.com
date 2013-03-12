---
title: Restartless Firefox Add-ons, Part 4: Localization (l10n)
short URL: http://r.evold.ca/rrffap4
tags: Localization, Firefox Add-ons, Programming, Firef
---
Alright, part four has been a long time coming, but I finally got around to typing out an localization include for restartless Firefox 4 addons which I'm ready to talk about. If you haven't read <a title="Restartless Firefox Add-ons, Part 2: Includes" rev="vote-for" href="http://erikvold.com/blog/index.cfm/2011/1/2/restartless-firefox-addons-part-2-includes">part 2</a> it's all about how to use includes, so read it first, if you don't know what a restartless addon is, then start with <a title="Restartless Restart Add-on for Firefox" href="http://erikvold.com/blog/index.cfm/2010/11/3/restartless-restart-addon-for-firefox">part 1</a>.
</p>

<p>
To start off with I wrote this include for <a title="Restartless Restart Firefox extension" rev="vote-for" rel="external" target="_blank" href="https://github.com/erikvold/restartless-restart-ffext/">Restartless Restart</a>, and I consider that to be my demo.
</p>

<h2>Overview</h2>
<p>
Alright, so you should know how to use includes in a restartless addon now, and I shouldn't have to explain why localizing your addon is important, and you have an example; here are some notes:
</p>

<p>
To begin with you will need to copy <a title="l10n.js" rel="external" target="_blank" href="https://github.com/erikvold/restartless-restart-ffext/blob/master/src/includes/l10n.js">this l10n.js file</a> in to your addon, then include it at startup (in your addons bootstrap.js file) and create the all important underscore function (literally "_(aKey)"), like so:
</p>

<h3>Setup</h3>

<div class="code">function startup(data) AddonManager.getAddonByID(data.id, function(addon) {<br>
  include(addon.getResourceURI("includes/l10n.js").spec);<br>
  l10n(addon, "filename.properties", "en-US");<br>
}</div>

<p>
So the example above assumes that you copied the l10n.js into a includes/ subdirectory, and that "filename.properties" is the name of the files within a /locale/en-US/ subdirectory for example, so the path to the english (US) translation for the text in your addon would be "/locale/en-US/filename.properties" (I would recommend using something other than "filename"). After l10n() is called it will create (and return) a global function named "_", which can be used to obtain the appropriate localized text. The 3rd parameter for l10n is the default locale that should be used when all other attempts fail. A failed attempted could be caused by a missing locale file (say you haven't yet translated your addon for the user's locale for instance), or the locale file could exist but not have the requested key, or the key could exist but be blank.
</p>

<h2>Using _</h2>
<p>
_ takes 2 arguments aKey, and aLocale which is optional.</p>

<p>
<strong>aKey</strong> is the key for the text in your .properties file.
</p>

<p>
<strong>aLocale</strong> allows you to attempt to grab a specific translation before trying to get a translation from the user's locale, and lastly trying the default locale specified by the addon developer in the l10n call above (if that 3rd argument of l10n isn't provided then "en" is used). I use this in Restartless Restart to provide the user with the ability to override their browser's locale and get another translation. So I use the ja-JP translation for Restartless Restart on my Firefox profiles these days just because.
</p>


<h2>Conclusion</h2>
<p>
If you have a restartless addon, and you haven't localized it yet, then get to it!
</p>
