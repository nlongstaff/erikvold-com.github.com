---
title: Disconnected: No Supported authentication methods available
short URL: http://r.evold.ca/gitssh
tags: How To, Git, Troubleshooting, Programming
---
<a title="Erik Vold - Twitter: trying to commit to github" rel="external nofollow" target="_blank" href="http://twitter.com/erikvold/status/4539492845">I recently ran in to this error message</a> when trying to pull or push anything from/to <a title="GitHub" rel="external" rev="vote-for" target="_blank" href="https://github.com/">GitHub</a> with <a title="TortoiseGit" rel="external nofollow" rev="vote-for" target="_blank" href="http://code.google.com/p/tortoisegit/">TortoiseGit</a> and <a title="PuTTY: A Free Telnet/SSH Client" rel="external nofollow" rev="vote-for" target="_blank" href="http://www.chiark.greenend.org.uk/~sgtatham/putty/">PuTTY</a>: "Disconnected: No Supported authentication methods available".
</p>
<p>
It turns out this message was a result of my lack of knowledge of PuTTY, and I simply did not have Pageant running with the ssh key for GitHub loaded.
</p>
<p>
I did some searching on Google and there wasn't much help out there that I could find, so I wanted to explain this for the next guy and make a reference to the only page that helped me, which was at GitHub: <a title="Guides: Addressing authentication problems with SSH" rel="external" rev="vote-for" target="_blank" href="http://github.com/guides/addressing-authentication-problems-with-ssh">Guides: Addressing authentication problems with SSH</a>
