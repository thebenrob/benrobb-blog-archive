---
id: 50
title: dd-wrt Open Source Firmware
date: 2007-03-13T21:07:07-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/03/13/dd-wrt-open-source-firmware/
permalink: /2007/03/13/dd-wrt-open-source-firmware/
dsq_thread_id:
  - "3051384607"
categories:
  - Old Stuff
---
My trusty Linksys router has been going steady for close to 4 years now, but recently it's started having some troubles.  It was still performing most of its duties just fine, but the wireless started to become very problematic.  In addition, it uses Stateful Packet Inspection as part of the firewall, which completely breaks down with the new Windows Vista TCP/IP stack (I found that out during beta, I don't actually run Vista at home).

So I figured that since my laptop was the only wireless device on my home network, I could just work around it, and plug in whenever I needed internet access.  Certainly limiting, but on a student budget, I didn't feel like fronting the money for a new router.

The recent win at the Web Analytics Competition provided some play money, and somehow a Nintendo Wii found its way into my entertainment center.  Now those of you familiar with the Wii know that it has built in wifi (yes it's only 802.11B, but wireless is wireless).  Suddenly I had another wireless device to manage.  The Wii connected fine originally and downloaded the system updates, but whenever I tried to connect to WiiConnect24 (which enables every other internet enabled feature on the Wii) it errored out with a 220602 error whenever I tried to access the EULA.

After googling around a bit, I found a solution that involved turning off all your encryption, etc., accepting the EULA, turning all your encryption back on, and continuing as normal.  I tried this solution and found it to be lacking.  I still received the same error.

I had heard of dd-wrt (pronounced "d-d-wort") before, but was a little nervous about using it.  The complete and utter lack of wireless functionality finally got to me, and tonight I broke down and installed dd-wrt.

<a href="http://www.dd-wrt.com/dd-wrtv2/ddwrt.php" title="ww-drt">dd-wrt</a> is an open source firmware for use on many varieties of routers, but has found a home among those fed up with their Linksys WRT54G series routers.  It wasn't all rose, but after a few hours of playing around, I'm up and running successfully on encrypted wireless on the dd-wrt mini firmware for WRT54G.

Unfortunately, I'm not sure what happened.  I'm sure you've all had those moments that after screwing around with everything you can think of, giving up a few times, trying again, something finally gives and it works, but you don't know what happened?  This was one of those times.

I originally flashed my router with the dd-wrt standard image and thought I had bricked my router (bricked = turned into an expensive plastic brick that doesn't do anything but flash lights).  Linksys provides a management console to recover from such things, but I was having trouble getting there.  Try as I might, that console to load the original firmware back just wouldn't come up.  I got online and ordered my Airport Extreme Base Station figuring if I was gonna spend money, I might as well spend a lot and get the best.

But I have trouble giving up on things, so I tried the hard reset to get to the Linksys Managament console again and the dd-wrt suddenly came up and was seemingly working.  However as I began to change settings, it appeared that the update.cgi script that should have been running to save my settings wasn't actually running at all.

After another hard reset, I flashed it back to the Linksys firmware which came up and allowed me to configure away.  However, this less than optimal solution turned out that I still didn't have wireless.  I tried again with the dd-wrt mini firmware and all seems to be well.  The mini firmware seems to have all the functionality that the original Linksys firmware had.  One thing in particular that I missed from my brief view of the standard image was the ability to do your dynamic DNS right from the router.  Anyway, everything is working, the Wii got its EULA and my MacBook Pro is now up and running wirelessly.

I just cancelled my order for the Airport Extreme Base Station from Apple.  I figure now that all these issues are resolved, I might give my free copy of Vista another go and see how it runs.  I'm reluctant to do this however, since I swiped the Ram from my desktop and put it in my server, and a server just doesn't seem like the best place for a consumer release of Vista.

So to wrap things up, if you're fed up with your WRT54G router (or many others, see <a href="http://www.dd-wrt.com/wiki/index.php/Supported_Devices" title="dd-wrt supported devices">this page</a> for a list of supported routers) and you're looking for something new, you might want to give dd-wrt a try.  It's working great for me.