---
title: Restartless Firefox Add-ons, Part 3: Icons
short URL: http://r.evold.ca/rrffap3
tags: UX, Firefox Add-ons, Firefox
---
Well this is only part three, we are still just getting started after all =] so since I have very little time today I thought that I would write about how to include a icon for your restartless extension, since it's not exactly obvious. Although this method is documented <a title="Install.rdf iconURL - MDN" target="_blank" rel="external nofollow" rev="vote-for" href="https://developer.mozilla.org/en/install_manifests#iconURL">here</a>.
</p>
<p>
Basically all you need to do is include a icon.png in the root of your xpi (the same place as your bootstrap.js and install.rdf) and Firefox will automatically find it. You can also include a icon64.png in the root of your xpi and this will be used in the add-on manager's add-on detail view, so it's a good idea to include both if you have them because it'll be a better UX.
</p>
<p>
If you want to use the icon in other places use the method that I described in <a title="Restartless Firefox Add-ons, Part 2: Includes" href="http://erikvold.com/blog/index.cfm/2011/1/2/restartless-firefox-addons-part-2-includes">part 2</a> in order to find the file: url of the image and use that.
</p>
