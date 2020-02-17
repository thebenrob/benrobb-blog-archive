---
id: 77
title: 'Everything I Need To Know About Life&#8230;'
date: 2007-04-16T21:11:33-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/04/16/everything-i-need-to-know-about-life/
permalink: /2007/04/16/everything-i-need-to-know-about-life/
dsq_thread_id:
  - "3051383785"
categories:
  - Old Stuff
---
I learned in Isys 532 (not really, but this post is fishing for a grade.  Dr. Liddle, this one is for you).

I'll just throw out the warning up front that this is not a typical blog post.  For my Information Architecture class, I've been instructed to condense a semester's worth of learning into one blog post.

So my goal with this post is not to rehash all the research and work I've done throughout the semester, but to make a good parts version and wrap everything up.  So here we go in no particular order.  I wrote a random number generator to sort them for me.  A real random-number generator, not a psuedo-random number generator.

<strong>Lesson #1: Ruby is not a toy. And Rails is not a buzzword.</strong>
Dr. Liddle, I can already see you shaking your head and smiling as you read this.  To borrow a phrase, you're thinking that all I've got is a hammer and everything looks like a nail.

While I admit that there may be a bit of truth in it, the fact is that I really don't know that much about Ruby or Rails.  But there are very smart people in the world that know just about everything that there is to know about it, and they're working very hard to make it better.

It is not a solution for every problem.  I've never seen a decent client-side GUI built on Ruby, but when you add Rails and throw it onto the web, it becomes a very powerful, very simple, and very stress-relieving application platform.  It makes AJAX very simple.  It teaches good practice.  It has good separation of components.  It has a very active friendly community around it.  No it is not the solution to everything, but it is going to go places, and you should pay more attention to it instead of just smiling and shaking your head whenever I bring it up =)

<strong>Lesson #2: Your mileage may vary.</strong>
During this semester, I've spent countless hours on the internet, looking up different solutions to different problems, to put together programs and projects for technologies I've never even heard of before.

Even though I ran into the same problems and error messages that others had run into, their solutions did not always work for me.  There are lots of folks that Google themselves onto my blog, and while I hope that my solutions work for them, that assumption requires a certain amount of naivety, and it's not an assumption I'd make.

Sometimes an authoritative answer cannot be found, so we turn to the blogosphere.  The so-called Web 2.0 movement has enabled millions of people to build themselves a spot on the internet and granted access to amazing information resources, but just keep in mind where this knowledge is coming from.  Don't be surprised when someone else's solution does not work for you.

<strong>Lesson #3: More servers and computing power is not always the best answer.</strong>
Sometimes when you are presented with the same old problem, the same old answer is not the best one.  I wrote <a title="Memcached" href="https://benrobb.com/wp-content/uploads/2009/01/memcached.pdf" target="_blank">a paper</a> about Memcached this semester.  It's an innovative way to solve the ages-old problem of scalability.

Obviously when you get bigger, you've got to scale up, but the lesson taught by Memcached is that up is not the only direction to scale.  Proper use of innovative technologies can enable you to scale out as well as up.  And Memcached is free, so throwing more money on the fire isn't always the best solution either.

I actually just ran across <a href="http://elliottback.com/wp/archives/2007/04/15/why-my-wordpress-site-is-so-much-faster-than-yours/">an article</a> on Digg that provided instructions for surviving The Digg Effect.  The article didn't mention anything about buying new servers, but rather instructions for tuning your server, optimizing your DB, caching your results, and tweaking your PHP (read programming language of choice).  That's all free too.

<strong>Lesson #4: A Gentoo installation <a href="https://benrobb.com/2007/02/19/a-formal-apology-to-the-gods-of-ubuntu/">should not be undertaken</a> in the middle of a busy semester.</strong>
This is pretty much self-explanatory.

<strong>Lesson #5: There is no perfect one-size-fits all solution.</strong>
There are a million ways to architect a system to support your application.  Maybe <a href="https://benrobb.com/2007/03/14/model-driven-architecture-part-1/">Model</a> <a href="https://benrobb.com/2007/03/20/is-model-driven-architecture-right-for-me/">Driven</a> <a href="https://benrobb.com/2007/03/24/model-driven-architecture-part-3/">Architecture</a> will fit your needs.  Maybe it's an extensible Service Oriented Architecture.  Maybe it's <a href="https://benrobb.com/2007/01/30/howto-put-wsdl-on-rails/">a simple Web Service</a> that you publish for others to consume.

The point is that what works best for someone else, may not be your best option.  Figure out what you really need, do your research, talk to people who know what they're doing, and decide what works best for you.

<strong>Lesson #6: Don't reinvent the wheel.</strong>
If you're having some kind of pain with your infrastructure, chances are you're not the first.  Google is your friend.  Or in an attempt to not be search-engine specific, the internet is your friend.  There are a lot of smart and friendly people that can help you out.

<strong>Lesson #7: If you're supporting a really really big, revenue-generating infrastructure, you're going to want the right tools for the job.</strong>
This is somewhat related to the above point.  We talked a lot about different architectures, applications, frameworks, and tools for solving your enterprise-level problems.  Standards are developed for a reason.  There are some industry standard tools for getting important tasks done.  <a href="https://benrobb.com/2007/04/03/enterprise-java-tools/">log4J and JMS </a>are examples of accepted, widely used tools for enterprise logging and messaging.  If a particular part of your IT infrastructure is not helping to generate a strategic advantage for your business, using tried-and-true solution is an excellent idea.

<strong>Lesson #8: Database optimization is not for the faint of heart.</strong>
Part of the reason it's so difficult is because it's different for every application and every person.  It is hard, but it is not impossible.

Awhile ago I wrote about <a href="https://benrobb.com/2007/04/09/mysql-optimization/">my thoughts</a> for the best way to approach it.  Benjamin Swanson, a good friend of mine, developed <a href="http://eblog.byu.edu/?p=238">his own framework</a> for performing the task.  It'll take time, but so do most other things that are worth doing.

<strong>Lesson #9: Putting in the extra time is worth the extra time.</strong>
I've found through personal experience that taking the time to do something right is worth the effort.  Throughout my school career, I've built a reputation for being a go-to guy and getting things done because I've been willing to put in the time it takes to get things done.  I find it rewarding when my peers ask me for help with something I've figured out.

But that is not why I do it.  For me, putting in the time to learn something is its own reward.

<strong>*** Update ***</strong>

<strong>Lesson #10:  Make your technology fit your business.</strong>
Perhaps this lesson is more powerful when stated in the longer form.  Make your technology fit your business; don't make your business fit your technology.  Technology serves a purpose, but it is only a tool.  When applied to the business world, it should solve a business need and more importantly, should make it easier for the business people to do their jobs.  The MISM program at BYU emphasizes both the business and the technology, but in most cases, it's the business that makes the money.  The technology exists to help us do business better (well, obviously there are other uses for technology, but let's keep things in context here).