---
title: How To Setup Windows XP With Boot Camp On A Macbook
tags: Apple, How To, Windows
---
I finally setup <a title="Microsoft Windows XP Professional" rel="external" rev="vote-for" target="_blank" href="http://www.microsoft.com/windowsxp/pro/default.mspx">Windows XP Pro</a> on my <a title="Apple - Macbook" rel="external" rev="vote-for" target="_blank" href="http://www.apple.com/macbook/">Macbook</a> using <a title="Apple Software - Boot Camp" rel="external" rev="vote-for" target="_blank" href="http://www.apple.com/support/bootcamp/">Boot Camp</a> over the weekend, and I hit some gotchas, because I did not read <a title="Boot Camp Installation Guide" rev="external" target="_blank" href="http://manuals.info.apple.com/en_US/Boot_Camp_Install-Setup.pdf">the guide</a>. So I thought I would make a quick summary of the process. Although, I would recommend reading <a title="Boot Camp Installation Guide" rev="external" target="_blank" href="http://manuals.info.apple.com/en_US/Boot_Camp_Install-Setup.pdf">the installation guide</a> to anyone doing this for the first time.
</p>

<p>
</p><h2>Setting up Windows XP on a Macbook with Boot Camp:</h2>
<ol>
<li>Run Boot Camp Assistant.</li>
<li>Create a partition for Windows (you will need at least 6 GB, I prefer around 20 GB).</li>
<li>Insert Windows XP Installation CD when it is requested, Boot Camp will restart the system and start the Windows installation process.</li>
<li>Follow the Windows installation instructions until you are asked to selected a partition.</li>
<li>Select the C:\BOOTCAMP partition.</li>
<li>Select "Format the partition using the FAT file system (Quick)". Do not select "Leave the current file system intact".</li>
<li>Continue following the Windows installation instructions until it has completed.</li>
<li>Insert your Mac OS X Installation DVD. If the installer does not start automatically, then run the setup.exe on the disc.</li>
<li>Follow the Boot Camp + Drivers installation instructions until the setup is complete.</li>
<li>Go to Start → All Programs → Apple Software Update, and run this to install the <a title="Multi-Touch Trackpad Update for Windows XP &amp; Vista" rel="external" rev="vote-for" target="_blank" href="http://support.apple.com/downloads/Multi_Touch_Trackpad_Update_for_Windows_XP___Vista">Multi-Touch Trackpad Update for Windows XP &amp; Vista</a>, which is very important.</li>
<li><a title="Microsoft Windows Update" rel="external nofollow" target="_blank" href="http://windowsupdate.microsoft.com/">Update Windows</a> and you're done.</li>
</ol>
<p></p>

<p><strong>Note:</strong> To manually <a title="Selecting an operating system during startup" rel="external" rev="vote-for" target="_blank" href="http://docs.info.apple.com/article.html?path=BootCamp/2.0/en/bc1147.html">select the Operating System that you want to use during startup</a>, press and hold the "option" key after you hear the chime during the boot cycle.</p>
