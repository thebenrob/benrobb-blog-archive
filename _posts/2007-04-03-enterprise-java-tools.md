---
id: 69
title: Enterprise Java Tools
date: 2007-04-03T19:42:18-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/04/03/enterprise-java-tools/
permalink: /2007/04/03/enterprise-java-tools/
dsq_thread_id:
  - "3631633882"
categories:
  - Old Stuff
---
The Java Language presents many advantages for the enterprise-types.  My personal favorite language really shines on the web, but for the full architecture and support desired in enterprises, Java has a lot to offer (not the topic of this post).  Right now we're going to look at 2 Java tools that have become commonplace in enterprise development: log4j and JMS.

<strong>log4j</strong>
log4j (non-capitalized on purpose) is an open-source project developed under the Apache Jakarta banner.  It was originally developed by Ceki Gülcü. It is built to be the best Java logger around, and the industry agrees that it is.  It's used for debugging and logging and can provide detailed context for application failures.

It is built as a package that you can drop into your application and start making calls to the logger object.  log4j may provide the best or only solution for debugging (this is often case in distributed applications).

log4j enables logging at run-time without modifying the application's compiled binary.  This means that you can enable debugging without suffering the heavy performance loss that you might expect by bloating your binaries with extra code.

Perhaps one of the most useful features in log4j is the idea of hierarchy and inheritance.  As you make calls to the logger object and log different kinds of events, you can have different outputs that listen to the logs and pass them on when certain criteria are met.  It's sort of a subscriber provider model for things.  Potential subscribers would be loggers outputting information to the console, files, databses, SMTP servers, GUI components, etc.  These subscribers are called appenders.

This means that you could potentially have everything logged to a standard file, important things put into a different file, database, etc., and have critical errors emailed to someone that can fix them.  The only thing you'd need in your application code would be the one call to the logger object and everything else happens as the different loggers subscribe to the different events.  All the subscriptions to events are handled by external configuration files, so you don't have to modify your application code in order to change the behavior of the loggers.

<strong>JMS</strong>
The Java Messaging Service is another logging solution.  My research on this topic introduced the phrase "asynchronous logging" for the first time although it sounds like log4j works on the same principle.  Reading about JMS also used the publisher/subscriber metaphor which I unfortunately already used, but these two facts should illustrate some of the similarities.

JMS actually supports to different types of logging.  The queuing model has a producer and only one consumer.  They are independent, so the consumer does not have to be running when the producer produces, and the producer does not have to be running when the consumer consumer.  This is a higher level of abstraction than log4j uses (according to my understanding).

The Publish/Subscribe model published messages in "topics."  Zero or more subscribers can subscribe to a particular topic.  In this model the subscribers and the publisher are not even aware of the other's existence.

Some enterprising individual has even built an Appender for log4j that plugs the JMS into log4j.  O'Reilly has also published a book on the JMS which in my book means it's significantly more complex.  From my readings, log4j is also further abstracted out of the application than JMS.  It sounds like in order to change what your JMS publisher is doing, you'll have to change code in your application and recompile.