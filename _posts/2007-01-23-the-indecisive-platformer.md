---
id: 24
title: The Indecisive Platformer
date: 2007-01-23T11:48:12-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/23/the-indecisive-platformer/
permalink: /2007/01/23/the-indecisive-platformer/
dsq_thread_id:
  - "3441499619"
categories:
  - Old Stuff
---
So I've now switched back to Wordpress.  I just finished a manual migration of sorts to pull all my posts back over from Typo.  Part of the problem was mod_ruby woes, part was little bugs, and part was features that just weren't available (although the skins are way better).  Excuse me while the dust settles and I pick up my Wordpress habits once again.

My web-host uses Apache1.3_mod_ruby to host Rails applications.  This reloads the entire ruby environment with each page (I've been told) and was effecting speed.  In addition to that, sometimes, you just got a nice Application Error page that was fixed by simply reloading the page.  Not good for PR.

I couldn't seem to get the Typo trackback feature to work either.  It worked fine running on my laptop while I was giving it a test drive, but once it was up in production on the server, it wouldn't post or receive trackbacks.  I decided to chalk this up to weird apache1.3 issues as well, since it seemed to work fine with Mongrel and Lighty.

And finally, there is much more support for multiple users and levels of user access in Wordpress.  This isn't a big issue now, but might become one later on down the road.  So to wrap up, I've switched platforms once again.  I still plan on posting an in-depth review of everything I learned about Wordpress, Typo, and Mephisto when I get some time, but for now, school is keeping me busy.