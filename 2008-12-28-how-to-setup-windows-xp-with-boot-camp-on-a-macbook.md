---
title: How To Setup Windows XP With Boot Camp On A Macbook
tags: Apple, How To, Windows
---
I finally setup [Windows XP Pro](http://www.microsoft.com/windowsxp/pro/default.mspx) on my [Macbook](http://www.apple.com/macbook/) using [Boot Camp](http://www.apple.com/support/bootcamp/) over the weekend, and I hit some gotchas, because I did not read [the guide](http://manuals.info.apple.com/en_US/Boot_Camp_Install-Setup.pdf). So I thought I would make a quick summary of the process. Although, I would recommend reading thh [Installation Guide](http://manuals.info.apple.com/en_US/Boot_Camp_Install-Setup.pdf) to anyone doing this for the first time.

##Setting up Windows XP on a Macbook with Boot Camp:

1. Run Boot Camp Assistant.
1. Create a partition for Windows (you will need at least 6 GB, I prefer around 20 GB).
1. Insert Windows XP Installation CD when it is requested, Boot Camp will restart the system and start the Windows installation process.
1. Follow the Windows installation instructions until you are asked to selected a partition.
1. Select the C:\BOOTCAMP partition.
1. Select "Format the partition using the FAT file system (Quick)". Do not select "Leave the current file system intact".
1. Continue following the Windows installation instructions until it has completed.
1. Insert your Mac OS X Installation DVD. If the installer does not start automatically, then run the setup.exe on the disc.
1. Follow the Boot Camp + Drivers installation instructions until the setup is complete.
1. Go to Start → All Programs → Apple Software Update, and run this to install the [Multi-Touch Trackpad Update for Windows XP &amp; Vista](http://support.apple.com/downloads/Multi_Touch_Trackpad_Update_for_Windows_XP___Vista) which is very important.
1. [Update Windows](http://windowsupdate.microsoft.com/) and you're done.

**Note:** To manually [select the operating system that you want to use during startup](http://docs.info.apple.com/article.html?path=BootCamp/2.0/en/bc1147.html), press and hold the "option" key after you hear the chime during the boot cycle.
