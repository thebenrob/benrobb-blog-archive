---
id: 46
title: Memcached
date: 2007-03-03T14:16:58-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/03/03/memcached/
permalink: /2007/03/03/memcached/
dsq_thread_id:
  - "5302924577"
categories:
  - Old Stuff
---
<p>I've been doing some research lately looking into memcached.  <a href="http://www.danga.com/memcached/" title="memcached">Memcached</a> is a system for distributing a memory cache across multiple machines.  If you're using a single server, then it probably won't do much for you, but as you start to scale up, it becomes a real life saver.  It is able to dramatically reduce database hits, meaning that your disks can take a little rest, and your server doesn't have to work so hard.</p><p>
The list of people using memcached is long and impressive including such sites as Slashdot, Digg, Wikipedia, LiveJournal, and more.  It was actually developed for LiveJournal and grew up from there (in much the same way that MediaWiki grew out of Wikipedia or Rails grew out of BaseCamp).  There are actually a lot of Rails folks starting to look into it now that Mongrel allows excellent scaling.</p>
<p>As I began to research memcached it became apparent that in order to get any sense of what it was capable of, I was going to have to dive in and get it running on my own.  There are only one or two decent articles on the web about it, despite it's apparent popularity, and so I began to look into it on my own.</p>
<p>My heart sank when I saw that it came distributed as source code.  My <a href="https://benrobb.com/2007/02/19/a-formal-apology-to-the-gods-of-ubuntu/">recent experience with Gentoo</a> has given me enough source compiling to last awhile, so I was pleased to see that it was listed in the both the DarwinPorts (now <a href="http://www.macports.org/" title="MacPorts">MacPorts</a>) and Ubuntu repositories.</p>
<p>So far I've got the software installed on the lappy and the virtual server.  I've started up the memcached daemon in both places and it seems to work well.  Since Rails is obviously my development platform of choice, I've also installed the memcache-client RubyGem and apparently, I'm ready to go.  Now for buliding a website.</p>
