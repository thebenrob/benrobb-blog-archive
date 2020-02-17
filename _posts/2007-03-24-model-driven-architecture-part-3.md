---
id: 61
title: 'Model Driven Architecture [part 3]'
date: 2007-03-24T22:19:08-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/03/24/model-driven-architecture-part-3/
permalink: /2007/03/24/model-driven-architecture-part-3/
dsq_thread_id:
  - "3865668548"
categories:
  - Old Stuff
---
This will be a short post, but I thought it would be interesting to look at one specific offering of an MDA product to see what they can do.  OptimalJ is made by Compuware and provides MDA programming for those of use that live in a J2EE world.

To start things off, <a href="http://www.compuware.com/products/optimalj/resources/4639_ENG_HTML.asp" title="OptimalJ Fact Sheet (this is a pdf file)">this PDF</a> file is one of their marketing releases, but as we look through it, we can see the foundations of what makes an MDA product.

OptimalJ consists of three basic components.  (1) Metamodels create separation between application design, infrastructure, and code.  (2) Technology patterns make model-to-model transformation possible. (3) Finally, implementation patterns allow for the model-to-code transformation.

Metamodels: At the high level, you need to separate the different aspects of your applications so that you can address the concerns of each individual piece before you bring it all together to work out those issues.  Since we've started breaking things down into threes (3 MDA posts and 3 OptimalJ components) we'll do one final three-part breakdown.  There are three kinds of metamodels.  The domain model, the application model, and the code model.

Proper usage of these metamodels formally defines the kinds of data needed by the application,  what technology the application will be using, and specific code pieces that will be used in certain situations.  This last part is a bit confusing, but the OptimalJ product allows for editing of templates (of a sort) that will later be used during the translation of model-to-code.

Technology Patterns: above we mentioned that this provides model-to-model transformation.  Specifically, this provides for the transformation of the domain model into the application model.  So starting from the kind of data that we want, we now translate that into the architecture of our application.  What kind of application is this?  Web-based, client-server, etc.

Implementation Patterns:   this transforms the application model into the code model.  This is where actual code is produced.

OptimalJ provides graphical editors for all these different pieces, but breaking it down this way, we can begin to see what OptimalJ can do.  We start up front with the need for an application.  After defining what data we need in the data model, we can generate an application model that provides an overview of the application itself.  Further transformation into the code model gives an application that can be compiled and run.

If we change the way the data should be stored, we can regenerate the application model and the code model and cut out all the in-betweens of recoding to match our new data structure.  All this auto-generation even includes SQL scripts for datbase creation if you're willing to spring for the higher-end versions.  Eclipse support and Netbeans support virtually guarantees that you'll be in a familiar environment.  Is there anyone in the world that still writes Java outside of those IDEs?