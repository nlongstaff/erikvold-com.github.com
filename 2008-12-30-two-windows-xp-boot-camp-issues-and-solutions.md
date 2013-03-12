---
title: Two Windows XP Boot Camp Issues And Solutions
tags: Apple, Troubleshooting, Windows
---
I had a really annoying issue come up after <a title="How To Setup Windows XP With Boot Camp On A MacBook" rev="vote-for" target="_blank" href="">setting up Windows XP on my MacBook with Boot Camp</a>, and installing some essential software I could no longer right click (two finger touch), or tab to click, because the Boot Camp service was not running.
</p>

<p>
At first, I went to the <a title="Windows Control Panel - Wikipedia" rel="external" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Control_Panel_(Windows)">Control Panel</a> and opened Boot Camp from there, once I did this I had to enable the trackpad settings I wanted, and everything was fine, until I restarted, at which point I would have to go through the whole process again. So after a few reboots to convince myself that was a dead end, I took a look for the Boot Camp executable on my C Drive, and found it at C:\Program Files\Boot Camp\KbdMgr.exe, but when I tried to run it, I could see it running in the <a title="Windows Task Manager - Wikipedia" rel="" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Windows_Task_Manager">Task Manager</a>, but it was not working at all.
</p>

<p>
So finally I gave up, and uninstalled Boot Camp, then reinstalled Boot Camp, and after the reinstall reboot, I got a couple errors, and my Ethernet Controller device no longer had a driver.. The good part however was that the Boot Camp service was running again, and after I enabled my trackpad settings, and rebooted, it continued to work.
</p>

<p>
To deal with the Ethernet Controller driver, I installed the D:\Boot Camp\Drivers\NVidia\NVidiaChipsetXP.exe from my MacBook Mac OS X Install DVD, and I was all done.
</p>
