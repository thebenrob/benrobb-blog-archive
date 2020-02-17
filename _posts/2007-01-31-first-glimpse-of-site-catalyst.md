---
id: 37
title: First Glimpse of Site Catalyst
date: 2007-01-31T15:56:39-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/31/first-glimpse-of-site-catalyst/
permalink: /2007/01/31/first-glimpse-of-site-catalyst/
dsq_thread_id:
  - "3051384019"
categories:
  - Old Stuff
---
I got my first glimpse of site catalyst which came after an evening of playing with AWStats preceeded by an evening of playing with Google Analytics.  I publicly proclaim that I am not an expert in any of these areas, I've simply been able to give them a test drive and here are my initial reactions to the three.

<strong>AWStats</strong>
You'd be absolutely amazed if you knew the extent to which our online activities are being tracked and recorded.  The basic install of AWStats (Advanced Web Statistics) uses only information obtainable in server logs.  These headers get passed around every time your web browser wants to load a page, download an image, etc.  Just from that information, AWStats is able to generate an impressive array of statistics and information.  The kinds of things that are available there are:
<ul>
	<li> IP Address</li>
	<li>UserID</li>
	<li>Time = the time that the request was completed</li>
	<li>HTTP request type (Get, Post, etc.)</li>
	<li>Size (in bytes) of the response</li>
	<li>Referer = if you follow a link from my site, I'm the referer</li>
	<li>User-Agent = tells the browser and platform type (Firefox 2.0.0.1, Mac OS X 10.4.8)</li>
</ul>
From this basic set of statistics, it's able to use a reverse DNS lookup with relative success to tell what countries all the hits are coming from.  Some statistical analysis are run as well, to produce reports showing statistics by month for how many hits, how many unique visitors (this calculation can be problematic), how many page views, browser stats, bandwidth usage, and any myriad of other things.  The reports are done in standard HTML and gives a pretty good Dashboard view of all sorts of things going on on your site.  In particular, I liked the reports showing what search terms and phrases that others were using to land on my site.  Not a bad tool, but again, it's limited to what gets passed around in HTTP headers.  By extending AWStats a bit and including some javascript, you start to approach the type of functionality offered by Google Analytics, so we'll move on to that now.

<strong>Google Analytics</strong>
Google Analytics is a straight javascript based solution to recording your web statistics.  Trust me when I use the term "javascript voodoo" to describe what's going on.  When you visit my website, your browser will download a little javascript file.  Then when the page loads, it calls a javascript function that will send a request to a google server somewhere and request to download a little file.  But that request to download sends all sorts of information about your browser above and beyond that's available in HTTP headers.  It can tell me how what screen resolution that you're using, for example.

Google Analytics shines however in the number and quality of reports that it generated.  I can go to Google Analytics and see just about everything related to traffic on my website.  It'll plot visitors on a world map, it'll build nice graphs and charts, etc.  The types of information available in Google Analytics lets you do things like, customize your page to be usable on the platform and browser that most of your users are using.  You can see if people hit one page and leave again (bounce rate) or if they stay around for while, it'll show you the duration of the visit.  It'll tell you the most common entry point for your site, whether it's the homepage or some other page on your site.  Shows you which is the last page your visitors looked at before the left.

It seems that the major difference between Google Analytics and Omniture however is the type of statisticsthat each system is capable of gathering.  After a very brief tour of Site Catalyst yesterday, I stand in awe of the types of things you can learn about your visitors.

<strong>Site Catalyst</strong>
Site Catalyst collects statistics about traffic, but what it does that no other product can do is tell you about the eCommerce implications of your site.  You can tell how many people landed on your page as a result of a particular add campaign, or an add placed on another website, or an email that you sent out to your customers.  You can tell how much revenue you generated from a particular product or product line, with all sorts of relevant details (profit margin, cost, etc).

In a way, Site Catalyst can make you nearly omniscient in the realm of your online eCommerce presence.  Omniture is currently developing a new product called Discover that we can expect to be rolled out in the first half of this year - don't ask, I don't know.  Discover refines the granularity of control down even further.  You want to blast an email out to everybody that added a MacBook Pro to their cart and abandoned the cart before checkout?  It's done.

Now, Site Catalyst is not for the faint of heart, the level of detail available in the reporting tools is amazing, and from what I could tell, you could spend days on the backend analyzing the reports.  Omniture has a team dedicated to looking for new ways to analyze data to provide valuable information to its clients.

Site Catalyst is not free, or even inexpensive.  It's the Cadillac of web analytics products, and you'll pay top-dollar for it.  Based on what I've seen though, it is entirely within the realm of possibility to recoup your yearly cost with a single marketing campaign (of course, this would be based on the popularity of your site).  I certainly couldn't recover the cost, but think of the possibilities for <a href="http://newegg.com" title="newegg">Newegg</a> or <a href="http://buy.com" title="buy.com">Buy.com</a>.

Bottom line is that the websites you visit probably know a lot more about your computer than you thought they did.  I know that I was certainly surprised by the level of detail available in these reports.  I don't mean to turn anyone into a paranoid, but these are things you should be aware of when you go online.  After all, anyone who uses these tools would be the first to tell you:

<em>Knowledge is Power</em>.