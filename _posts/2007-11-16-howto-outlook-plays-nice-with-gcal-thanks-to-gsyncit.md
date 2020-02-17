---
id: 94
title: 'Howto: Outlook Plays Nice With gCal Thanks to gSyncit'
date: 2007-11-16T21:38:38-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/11/16/howto-outlook-plays-nice-with-gcal-thanks-to-gsyncit/
permalink: /2007/11/16/howto-outlook-plays-nice-with-gcal-thanks-to-gsyncit/
dsq_thread_id:
  - "3051384463"
categories:
  - Old Stuff
tags:
  - apple
  - google
  - sync
---
Being a Mac user at home is nice, but makes calendar compatibility with my work computer a little challenging.  For awhile, I used my Blackberry and synced it to both computers, but it wasn't made for this purpose and after a few syncs, it inevitably started crashing the Desktop Manager on my Windows machine at work while trying to sync calendars.

I got tired of completely clearing out the calendar to get it to sync again (I did it twice and couldn't take it anymore).  I first turned to <a href="http://www.funambol.com/" title="Funambol">Funambol</a> and <a href="http://sheduleworld.com" title="Schedule World">Schedule World</a> with instructions from <a href="http://internetducttape.com/2006/08/11/the-holy-grail-of-synchronization-how-to-synchronize-microsoft-outlook-multiple-locations-google-calendar-gmail-ipod-and-mobile-phone-with-funambol-scheduleworld/" title="The Holy Grail of Synchronization">this article</a> over at internetducttape.com.

I should have read the comments a little closer before trying it out, because this Funambol doesn't work with Exception Dates.  Exception dates occur when you have a recurring appointment and then change one occurence without changing the series.  With my work, this happens all the time because I'll have weekly recurring appointments with clients that often get bumped by an hour or a day.  Whenever these exceptions occured, the sync process started adding appointments to my Outlook calendar even though I had said the sync should only go one direction.  It also had an annoying habit of popping up the Outlook reminder dialog several times during the sync.

One of <a href="http://virtute.org/" title="Zach Cochran">my colleagues</a> pointed me in the direction of <a href="http://www.syncmycal.com/" title="Syncmycal">SyncMyCal</a>.  They make a $25 dollar product that he uses and said it handles exception dates very well.  They also make a <a href="http://www.syncmycal.com/compare_versions.htm" title="compare version">free version</a>, but it will only sync a 7 day window which didn't meet my needs.  I'm willing to shell out $25 to save the aggravation, but a last ditch effort on Google revealed another possibility (I swear I performed the same search two days earlier).

<a href="http://www.daveswebsite.com/software/gsync/" title="gsyncit">gSyncit</a> comes in here. Dave claims to offer the same functionality with a free version and a full that costs $10.  The only limitation on the free version is no auto-sync and a popup when you load Outlook or sync.  So far it works beautifully.  I installed it this morning, and the first, second, and third sync went off without a hitch (or Outlook reminders popping all over my screen, or creating ghost appointments on my real calendar).

I figure I'll give it a few days to see how it handles more new appointments and a few more exception dates, but I'm thinking that I'll soon be paying Dave his $10 for a product well executed.

What I can now do is subscribe to my gCal work calendar with iCal on my Mac at home, and now I have a single source for everything happening in my life.  And since iCal obviously plays nice with iTunes and iPods, my iPod is now the portable source of truth for my busy life.   I guess I should here add my thanks to Google for supporting open standards and making my cross-platform life a little simpler as well.  And thanks to Apple for doing that too.