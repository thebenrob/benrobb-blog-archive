---
id: 29
title: Web Traffic Analysis
date: 2007-01-24T00:04:56-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/24/web-traffic-analysis/
permalink: /2007/01/24/web-traffic-analysis/
dsq_thread_id:
  - "3051383262"
categories:
  - Old Stuff
---
<p>In the realm of analyzing traffic that your web-site is generating, there are two main approaches.  Log-file analysis & real-time analysis (I don't know if that's an industry term, but that's what I'm going to call it).</p>
<p><strong>Real-Time Analysis</strong><br />
As a general rule, the real-time analysis tools use javascript to track visitors to your website.  Pasting a bit of javascript into the header of your HTML pages (or templates) means that every time a page is loaded, your website will send a call to a remote database somewhere with information about the visitor.  Logging into the account you've created at the remote site will allow you to view statistics with varying levels of details depending on the service.  Due to the use of Javascript to track and record statistics, these are completely platform independent.</p>
<ul>
<li>Omniture's <a href="http://www.omniture.com/products/web_analytics/sitecatalyst" title="Site Catalyst">Site Catalyst</a> - Enterprise level analytics.  As far as I know, Site Catalyst is really the only player at this level in the market.  I don't know a whole lot about it, but as I get access to it later on, I'm sure I'll be writing more about it.</li>
<li><a href="https://www.google.com/analytics/home/" title="google analytics">Google Analytics</a> - As far as I know, this is the weapon of choice for those that don't have the resources to implement and use site-catalyst but still want real-time analysis of their web traffic</li>
<li>Microsoft's Gatineau - As of this writing, Gatineau isn't live yet, so we don't exactly know how it will work,  but you can bet their trying to enter the Google Analytics market.  Details are sparse, but there are a few details over at <a href="http://www.searchenginejournal.com/?p=4239" title="searchenginejournal.com">searchenginejournal.com</a></li>
<li>Others - There are many other tools available.  Some of the ones I know of are <a href="http://sitetracker.com/" title="sitetracker">Sitetracker</a>, <a href="http://www.onestat.com/" title="onestat">OneStat</a> (pay service), and <a href="http://www.statcounter.com/" title="statcounter">StatCounter</a></li>
</ul>
<p><strong>Log-file Analysis</strong><br />
The alternate method of tracking visitors to your site is to use log-file analysis.  Every time your HTTP server sends out a page to a web browser, the request is stored in a log file.  A log file is simply a text file on your server that contains IP addresses, times, pages requested, and any other number of statistics.  Parsing through the log files and comparing certain bits of data to others allows a detailed picture of the traffic on your website.  Because these tools actually live on the servers andlook through log files, they are OS dependent.</p>
<ul>
<li><a href="http://awstats.sourceforge.net/" title="awstats">AWStats</a> - As far as I know, AWStats is the major player in this market.  It's an open-source tool that has been around since before I was doing web development.  I don't have extensive experience with AWStats, but my understanding is that the level of detail is not quite on par with Google Analytics.  AWStats works by running a PERL (maybe Python) script that parses through your server log files to generate static HTML pages.  A cron job runs the script whenever you schedule it, and then the stats are available at http://yourdomain/stats.  There is also a CGI interface that will do it in real-time for you.</li>
<li>Others - There are many tools that do this type of job.  See the <a href="http://en.wikipedia.org/wiki/Web_log_analysis_software" title="wikipedia web log file analysis software">Wikipedia</a> for more options in this arena.</li>
</ul>
<p>A post from Jimmy Zimmerman <a href="http://jimmyzimmerman.com/blog/2007/01/analytics-by-log-files.html" title="Jimmy Zimmerman's blog">highlights one issue with log-file analysis</a>.  Blogs and other types of web-sites that encourage user feedback have forms for posting comments, etc.  These comment forms are highly targeted by comment spammers that use this method of feedback for free advertising.  Since these spams consist of valid Request/Response pairs, they pollute your log files with false data.  If you use log-file analysis to track statistics on your site, be aware of this and take steps to cleanse your logs to produce accurate stats.</p>
