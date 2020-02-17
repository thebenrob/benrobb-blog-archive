---
id: 34
title: 'What About Web Services&#8230;'
date: 2007-01-27T20:03:04-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/27/what-about-web-services/
permalink: /2007/01/27/what-about-web-services/
categories:
  - Old Stuff
---
No doubt you've heard about web services, but what exactly are they? I've had teachers and others try to get this into my brain for at least the last three years, but it was only lately in a discussion about service-oriented architecture that it finally began to make sense. Let me lay these two topics out as simply as I can to see if I can make sense of it.

One of the problems with defining web-services is that has many different meanings to many different people. Don't believe me? Type "define:web services" into your nearest Google search box to see what I mean.

<strong>So What Are They?</strong>
To get a better sense for what web services actually are, let's first briefly discuss service-oriented architecture or SOA. The concept of SOA is not new, rather it is the context in which we use it that is new and improved.  Very simply, the idea is that a piece of information or a particular process is exposed to consumers as a service. These consumers can be end-users or other services attempting to organize or "orchestrate" individual services into something an end-user can use.

Some people believe that web services is simply a new term for something that we've been doing for years.  In a way this is true, and I'd bet that you interact with them more often than you realize, but it seems like it's nothing new. Your computer runs dozens of services, each doing something important.  What's different about web services?

Let's say that you have a web-service that looks up the weather, one that plots an address on a map, and one that finds the nearest gas station. An end-user can look up each of these individually or they can use an intermediate service that integrates each of these individual services and provides a single point of interface for all three pieces of information.

Abstracting out one more level, this intermediate service can be described as a so-called "portlet." Think of a portlet as a widget; one piece of information that can be displayed along with many others and can be changed at will. The best example of this I can think of is your customized Google Homepage. You can choose from any number of portlets or widgets that will display many different kinds of information. When you login, requests are submitted to each individual portlet and the proper information comes back and is displayed in your browser.

<strong>How Does It Work?</strong>
I won't get into incredible detail here, as the purpose is simply to provide an overview, but as Strong Bad says, "Technology is another word for magic." Actually, there are some very basic technologies at work here. Each web service must simply describe itself with Web Service Description Language (WSDL) so that service consumers know what the service does and how they can interact with it.

Interaction happens through Simple Object Access Protocol (SOAP) and eXtensible Markup Language (XML). In very simplistic terms, SOAP is simply an extenstion to the HTTP protocol that enables the passing of parameters via a standard request/response interface. These parameters are passed in a standard XML format so that both sides can properly encode and decode the actual data being passed back and forth.

<strong>Why Web Services?</strong>
This now lets us as answer the question of why?  Web services are language and platform agnostic, meaning that because the paths of communication are so stricly defined, that as long as a programming language or platform can speak the communicate in this common way, the two can communicate.

The other important "why" is that it cuts down costs.  Before service-oriented architecture came along, if you had five proprietary systems that needed to communicate, each system had to define a custom interface to the other 4 in order to communicate.  This means ten different interfaces would need to be programmed if all five want to talk, but if all speak the common language of services, then only five must be written.  The business case for service-oriented architecture? Reduced cost.

Welcome to the Web 2.0.