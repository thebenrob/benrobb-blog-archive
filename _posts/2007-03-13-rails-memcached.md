---
id: 51
title: 'Rails &#038; MemcacheD'
date: 2007-03-13T21:38:30-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/03/13/rails-memcached/
permalink: /2007/03/13/rails-memcached/
dsq_thread_id:
  - "3156910674"
categories:
  - Old Stuff
---
Well, after spending a few frustrated hours on Saturday, I've got a working application that uses memcached.  And when I use the word application, I use it very loosely.  It's basically a page that sets the current time into the session.

Now originally I followed <a href="http://nubyonrails.com/articles/2006/08/17/memcached-basics-for-rails" title="nuby on rails">this tutorial</a> and installed the necessary gems in order to cache the ActiveRecord objects into memcached.  I followed all instructions exactly as instructed, but starting the memcached server in verbose mode, revealed no object calls to and from the cache.  If I loaded up the application console, I could access the cache directly and put things in on my own, but the functionality provided by cached_model was not working on my machine for whatever reason.

Being somewhat of a nuby anyway when it comes to Rails, I turned to an alternate solution rather than hopelessly debugging the current problem.  I found <a href="http://townx.org/blog/elliot/ruby_tuesday_what_ive_learned_about_rails_and_memcache" title="Ruby Tuesday">another tutorial</a> that had instructions on how to cache sessions into memcached.  I used the memcache-client client rather than the Ruby-memcache client going for the speed and the ease of setup.  It works like a charm.

Now rather than just leaving it there, I'll tell you what I'v discovered over and above what Elliott discovered over at townx.  The ongoing development of memcache-client has apparently made some advancements to the point where it matches the application stability of Ruby-memcache when the memcache server is turned off.

At the time of the post, Elliott observed that when using memcache-client the whole application fell over when the connection to the memcache server was lost, while Ruby-memcache kept the application running with irretrievably broken sessions.  He then wrote a plug-in that monitored the memcache servers and when they came back online would begin using them again (rather than having to restart the application).  My observation as of today is that memcache-client now has both of those functionalities built in.

When the connection to the memcache server is lost, then the sessions are broken, any data stored is inaccessible, however when the memcache servers some back online, the application recognizes that and begins using the sessions again.  If the memcache server was turned off, then any data in them is gone as well, but if the memcache server itself was still running and it was just the connection lost, then the session data should still be available in the memcache servers.

As a sidenote, over at Nuby on Rails, they noted that the the memcached server available on Macs through Darwinports is broken.  I verified this; the calls I made to the cache directly from the console did indeed take 5 seconds to  push through.  However,when running it from my Ubuntu box even over the internet (Sundance to Orem) the application response was pretty snappy.  Not to shabby considering the quality of the internet in Sundance.