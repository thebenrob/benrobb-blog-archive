---
id: 56
title: Campaign Tracking in SiteCatalyst
date: 2007-03-19T21:09:33-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/03/19/campaign-tracking-in-sitecatalyst/
permalink: /2007/03/19/campaign-tracking-in-sitecatalyst/
dsq_thread_id:
  - "3051384673"
categories:
  - Old Stuff
---
At the risk of this blog starting to sound like an advertisement for SiteCatalyst, that is not my intention, I'm just continually surprised by the amount of control you can exercise over your data.  There are so many different ways to combine your data so you can view it from every angle.

I just barely finished reading sections of Omniture's Implementation Manual and the Omniture Advanced User Training documents.  Today's tidbit deals with tracking campaigns.

Omniture's code includes a variable for a campaign.  When this variable is populated, it persists as a visit continues until a visitor completes a success event (a purchase, a registration, a download, etc.) that the site owner has defined.  If you own a commerce site, you can use different codes to track pay-per-click campaigns, affiliate referrals, email click-throughs, and any other number of marketing efforts.

You can view the reports for these  in the commerce section of a report suite by running the Tracking Codes report.  This will show you your different tracking codes and their relative success rates (again, how you measure success is completely customizable by you).  Not enough detail you say?  Well there's more.

Let's say you want data about more than just a single tracking code.  Let's say you run a marketing campaign that consists of emails, banner ads, affiliate links, and AdWords bids.  SiteCatalyst allows you to classify all the different tracking codes into Campaigns and report on those as well.  I can't say enough about the value of this type of information.  To borrow a term from a recent visitor to our web analytics class, running an online business without this information is the equivalent of flying blind.