---
id: 35
title: 'Web Services [Part 2]'
date: 2007-01-30T21:52:59-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/30/web-services-part-2/
permalink: /2007/01/30/web-services-part-2/
dsq_thread_id:
  - "3051384218"
categories:
  - Old Stuff
---
<p>I wrote a few days ago about web services.  Those writings were based on some preliminary research and class discussions.  Since then I've had a little spare time to sit down and play them a bit, and even was able to whip up my own little web service in Rails.  I'll provide a HowTo as another article, but wanted to give my definition a bit of a refinement after some personal experience.</p>
<p>Any programmer is familiar with the concept of invoking a method on an object.  For the non-programmers in the crowd, an object is simply something that us programmers use to represent real-life objects.  When you register for my web site, give your email address, name, and password, I create a user <em>object</em> that represents you.  When you come back to my website and login, I talk to your user object and ask it if the password you typed in is the right password.  If it says yes, then I let you in, and if it says no, I tell you to try again.</p>
<p>In a traditional computer program or web application, we always have to create our own objects from our own data.  Web services are changing that traditional model and changing the way we think about programming.  In a larger sense this realignment of thought is changing the underlying structure of the web.  It is changing the way that companies think about eCommerce.  It is changing the fundamental make-up of the web itself.  If you've heard about the Web 2.0, this is a very simplified description of that concept.  For more about the Web 2.0 you should look up what O'Reilly <a href="http://www.oreillynet.com/lpt/a/6228" title="The Web 2.0 by O'Reilly">wrote about the subject</a>.</p>
<p><strong>Web Services Redefined</strong><br />
So now that I've got the preliminaries out of the way, I'm going to explain web services much more simply than I did a few days ago.  Web services simply provides a way for you to access and talk to objects that other people have written.  More importantly, it doesn't matter what programming language or platform that someone else used to create the service, you can use it with any platform you want to.  That's really all there is to it.</p>
