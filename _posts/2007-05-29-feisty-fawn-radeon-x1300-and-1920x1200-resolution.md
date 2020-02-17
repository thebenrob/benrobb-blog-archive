---
id: 83
title: 'Feisty Fawn, Radeon x1300, and 1920&#215;1200 Resolution'
date: 2007-05-29T18:43:01-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/05/29/feisty-fawn-radeon-x1300-and-1920x1200-resolution/
permalink: /2007/05/29/feisty-fawn-radeon-x1300-and-1920x1200-resolution/
dsq_thread_id:
  - "3051383466"
categories:
  - Old Stuff
---
For all the weary googlers out there, this one is for you.  I've recently installed Ubuntu 7.04 Feisty Fawn on my Dell Optiplex 745 Desktop which has a Dell 2407WFP Widescreen monitor plugged into it.

During the LiveCD installation and afterwards, the best resolution I could get on the screen was 1600x1200@60 which isn't bad, but looks slightly wider than it should given that in Windows XP &amp; Vista (setup on different partitions) it displays at 1920x1200@60.  I used the <strong>Restricted Drivers Manager</strong> to install fglrx for the Radeon, but that didn't help.

All my google searches related to the video card and the monitor inevitably led me to instructions dealing with installing the fglrx driver and running Beryl etc.  Nothing told me how to get my screen resolution bigger.  Basic edits to the Xorg file led me to several changes that didn't work (and some that completely broke X, let that be a lesson to always backup before making changes...lucky for me I did).

I finally stumbled upon a bug that had been logged with a link to <a href="http://www.wiredfool.com/index.php?s=lcd+ubuntu&amp;sbutt=Go" title="Widescreen LCDs and Ubuntu Linux">this article</a> at WiredFool.  I followed the tips he had including cutting out a lot of the fluff in the Xorg file and used the <a href="http://xtiming.sourceforge.net/cgi-bin/xtiming.pl" title="Modeline calculator">Modeline calculator</a> that the article linked to.  I tried a few different runs through before I found one that displayed the way I wanted it.

I skipped everything in the "Monitor Configuration" section.  Filled in my <strong>Visible Resolution</strong> and <strong>Refresh Rate</strong> in the "Basic Configuration" section, and also checked the 16:9 <strong>Constrain Aspect Ratio box</strong>.  I left everything else the same and hit the calculate button at the bottom.  The Modeline is displayed at the top of the screen.

Your mileage may vary, but if perhaps you're hardware is exactly the same as mine, here are the relevant portions of my xorg.conf file (although not formatted very well...you can add the tabs back in if you want).

Section "Monitor"
Identifier	"DELL 2407WFP"
Option		"DPMS"
Modeline "1920x1080@60" 182.28 1920 1952 2640 2672 1080 1102 1113 1135
EndSection

Section "Screen"
Identifier	"Default Screen"
Device		"Generic Video Card"
Monitor		"DELL 2407WFP"
Defaultdepth	24
SubSection "Display"
Depth	1
Modes	"1920x1200"
EndSubSection
SubSection "Display"
Depth	24
Modes	"1920x1200"
EndSubSection
EndSection

Good luck in all your Feisty adventures.