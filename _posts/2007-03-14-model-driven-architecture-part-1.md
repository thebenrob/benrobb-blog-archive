---
id: 53
title: 'Model Driven Architecture [part 1]'
date: 2007-03-14T20:17:22-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/03/14/model-driven-architecture-part-1/
permalink: /2007/03/14/model-driven-architecture-part-1/
dsq_thread_id:
  - "3946479793"
categories:
  - Old Stuff
---
<p>Model Driven Architecture (MDA) is one of many buzzwords you'll hear in software development circles.  It's actually more than one word, but nobody ever says buzzphrase, we're much more excited by buzzwords.  This article is by no means meant to be a comprehensive resource, it simply represents my attempt to wrap my head around the concept.</p>
<p>Model driven architecture is an attempt to focus information systems on business problems rather than on the technology itself.  The idea is that by defining our data and our processes in a certain way, that applications can be written by computers instead of programmers.</p>
<p>The models we are talking about here are significantly more complex than a class diagram or a sequence diagram, but at heart are really providing some of the same information.  You can define the types of data your application must represent and you can define how different entities in your system should interact.  Then if you define everything properly, a super special computer program can actually generate a functioning application for you.</p>
<p>The main standards behind MDA are mostly developed by the Object Management Group (OMG) which they seem to produce at an astonishing rate (see <a href="http://www.omg.org/gettingstarted/overview.htm" title="specs">this list</a> if you want to be impressed).  In reality, these computer generated applications are probably better used as a starting point rather than a polished final product, but a good deal of the time investment in creating a new application can be done for you.</p>
<p><strong>Principles</strong><br />
There are a few principles that underpin the model driven architecture.  From <a href="http://www-128.ibm.com/developerworks/rational/library/3100.html" title="Rational">an IBM article</a> on the subject:</p>
<blockquote>
<ul>
<li>Models expressed in a well-defined notation are a cornerstone to understanding systems for enterprise-scale solutions.</li>
<li>The building of systems can be organized around a set of models by imposing a series of transformations between models, organized into an architectural framework of layers and transformations.</li>
<li>A formal underpinning for describing models in a set of metamodels facilitates meaningful integration and transformation among models, and is the basis for automation through tools.</li>
<li>Acceptance and broad adoption of this model-based approach requires industry standards to provide openness to consumers, and foster competition among vendors.</li>
</ul>
</blockquote>
<p>If that made any sense, then good on you.  Here's the benrobb version.</p>
<blockquote>
<ul>
<li>Defining your data makes it easier to understand, especially when there's lots of it.</li>
<li>Our really cool MDA tool lets you turn your model into different types of applications in different languages.</li>
<li>This will get even cooler if we can get lots of people to do it.</li>
</ul>
</blockquote>
<p><strong>Value Proposition</strong><br />
The main value I see is that it allows you to seperate the design from the architecture, the business from the technology, or in the words of CARE Technologies (OptimalJ creator), the "what" from the "how."</p>
<p>Compuware (OlivaNovA creator) lays out <a href="http://www.compuware.com/products/optimalj/1811_ENG_HTML.htm">these values</a>:</p>
<blockquote>
<ul>
<li>accelerate productivity—cut development time by 40 percent or more</li>
<li>enhance maintainability—simplify maintenance and refactoring tasks, reducing time and cost</li>
<li>increase flexibility—respond rapidly to business and technology change</li>
<li>ensure quality—promote and enforce best practices and industry-proven code standards</li>
<li>streamline integration—leverage and optimize existing technology investments</li>
<li>synchronize requirements with code—trace business requirements to application code implementation</li>
</ul>
</blockquote>
<p>We all know that technology changes faster than most business processes, and MDA provides a way to allow you to keep your business processes, but also keep up to date on your technology.</p>
<p><strong>Vendors</strong><br />
OMG maintains a list of vendors of MDA products.  Of the vendors on this list, I've actually heard of a few:</p>
<ul>
<li>CARE Technologies - Oliva<strong>NOVA</strong> The Programming Machine</li>
<li>Compuware - OptimalJ</li>
<li>IBM - Rational</li>
<li>TenFold - BusinessTransformation & TechnologyTransfer</li>
</ul>
<p><strong>Criticisms</strong><br />
These are simply coming from <a href="http://en.wikipedia.org/wiki/Model-driven_architecture" title="model driven architecture">Wikipedia</a>, but there are a few that I think are important to mention here.</p>
<p>Vendor Lock-in: Although the idea behind MDA is to free you from the worry of technology and code, using it does lock you into a specific vendor, because at this point in time, none of them are interoperable.</p>
<p>Incomplete standards:  some of the technical standards involved have yet to be implemented in standard way, and some have not even been defined yet.</p>
<p>Expertise scarcity: Modellers/MDA Architects are in much scarcer supply than your average (or even above average) developer.</p>
<p><strong>Conclusions</strong><br />
Well, that's all the time I've got now since the baby needs her shower.  Part 1 has really focused on what MDA is, what it does, and who is doing it, but in Part 2 we'll take a look at some of the things you might want to take a look at if you (or your organization) is looking into doing something with MDA.</p>
