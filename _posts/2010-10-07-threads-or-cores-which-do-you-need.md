---
id: 293
title: 'Threads or Cores: Which Do You Need?'
date: 2010-10-07T16:47:55-07:00
author: Ben
layout: post
guid: http://benrobb.com/?p=293
permalink: /2010/10/07/threads-or-cores-which-do-you-need/
dsq_thread_id:
  - "3051384521"
image: /wp-content/uploads/2010/10/chips-157x90.jpg
categories:
  - Old Stuff
---
I'm slightly ashamed to say that I never really understood the concept of <a href="http://content.dell.com/us/en/enterprise/d/large-business/thread-cores-which-you-need.aspx?dgc=SM&amp;cid=57468&amp;lid=1479422">threads or cores</a> before now.

I didn't know what hyper-threading was, but I'd bought the hype that quad-core processors with 8 logical cores were spectacular.  As it turns out, they are, but now I know why.

Logical cores aren't as powerful as physical cores, if you could squeeze 8 physical cores on a die, that would be better than 8 logicals, but until somebody figures out how to do that, I'll stick with the logical ones.

Hyper threading just means that two processes can be operating on a single processor, though still not at the same time, which is why physical cores are better.  Hyperthreading just means that if one thread gets stuck waiting for something, and another thread is ready to go, the first one pauses to let the other one go past.  Kind of like a cargo train pulling onto a side-track so the bullet train can go past.