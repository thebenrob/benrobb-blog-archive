---
id: 18
title: 'Flashed my Bios with AsusUpdate&#8230;Ooops!'
date: 2007-01-19T11:35:49-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/19/flashed-my-bios-with-asusupdateooops/
permalink: /2007/01/19/flashed-my-bios-with-asusupdateooops/
dsq_thread_id:
  - "3487453607"
categories:
  - Old Stuff
---
So, after deliberating and waffling back and forth, I’ve decided to reinstall Windows 2003 Server Enterprise on my server. Only a week ago I backed everything up, wiped it clean and did a fresh install of Ubuntu64 the Edgy Eft edition, but there were a few things that didn’t work as well as planned.

I love having a shell on my server for remote access, but the Samba server just doesn’t serve content quite as fast as the original SMB protocol that Windows uses (no I can’t back that up with tests, just feels slower). In addition, I could never get the BitTorrent client to work on Ubuntu even though one comes installed, and I very quickly began to miss my uTorrent.

My recent time spent playing with VMWare Fusion and VMWare Server gave me a sudden and wonderful idea. I decided to reinstall Windows, then throw VMWare Server on and put Ubuntu Server in a virtual machine. I dug around in the old computer parts box and dug up a Linksys NIC, threw it in for good measure, and we’re ready to go. The plan is to have one NIC dedicated to the Ubuntu VM. I thought about using Virtual PC, but I’ve heard that it’s a little problematic with Linux distros, so I figured I’d stick with what I’ve used in the past.

That’s where the thought process ended. I backed everything up again (a lengthy process, we’re talking over 200 gigs of data) and then reinstalled Windows. I’m using an Asus A8N5X Motherboard and an AMD Athlon 64 3200+ in this particular server. I swapped the ram in the desktop (don’t need a gig in there anymore since I never play games) to give my server 1 gig of ram as well.

Windows installed just fine, I threw in my Asus Drivers CD and installed all the important pieces there as well, and figured I might as well flash my BIOS while I was at it. As it turns out that was a mistake. The update utility looks fairly nice and allows you to flash your BIOS without using boot disks, an attractive proposition for someone who hasn’t had a 3.5” floppy drive for many years. The program itself began behaving strangely (this should have been a warning), but I persisted. Eventually I navigated my way through the jungle of poor software design and clicked the button that said “Flash.”

After completing this step, the computer told me it had to reboot. I watched the Asus logo come up and then my stomach sank when a little message popped up that said

DISK BOOT FAILURE, INSERT SYSTEM DISK AND PRESS ENTER

My stomach sank. After I recovered from the initial shock, I restarted and entered the newly flashed BIOS. I disabled everything relating to 3.5” floppies which didn’t really make sense since I don’t have a floppy. If it can tell what kind of hard drives and CD drives I have, it’s a logical extrapolation that it could tell there was no disk drive. Anyway, I set the order of boot devices and restarted.

I was again greeted with the same friendly error. I had a heart-attack for awhile, booted into the recovery console a few times to try running

fixboot

and

fixmbr

but neither of those seemed to work. I had just finished lamenting to my wife when I had one final thought. “Wait a second, there are two hard drives in that box.” Sure enough, I went back into the BIOS and found a setting I had missed the first time around. My non-Windows hard drive was now set as the #1 drive, and since there was no OS on it, there was no boot. Changing the order of the drives cleared everything up and I was good to go.

So if at first you don’t succeed, talk to your wife and everything will clear itself up.