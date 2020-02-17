---
id: 36
title: 'Howto: Put WSDL on Rails'
date: 2007-01-30T23:51:39-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/30/howto-put-wsdl-on-rails/
permalink: /2007/01/30/howto-put-wsdl-on-rails/
dsq_thread_id:
  - "3051383282"
categories:
  - Old Stuff
---
Why do I love Rails so much?  Because there is so much to love!  Who ever dreamed that creating web services could be so simple?  Where other frameworks can consume them very simply, Rails defines simplicity when it comes to creating them.  Consuming them is easy as well, but it's on the creation side that Rails really stands out from the competition.  So how do you do it?

First off, let me say that my inexperience in web services means that I'm far from a subject matter expert.  I can however follow simple instructions, and I found a beautiful set over at the SOA Ranch.  This is a 3 part series, though more are supposedly coming.  I hope these articles continue to be published, but I have my doubts as the most recent articles are nearly 6 months old now.  The first one I found was <span style="text-decoration: line-through;">part 3</span> part 2.5 in the series, and you can follow the links back to part 1 &amp; part 2 (update 1/3/2009: I've removed the links since they no longer point to Rails content, apologies for the inconvenience).

So let's get down to business.  I'll make the assumption that you've got a <a title="how to make a working rails environment" href="https://benrobb.com/2007/02/01/howto-make-a-rails-environment-in-ubuntu/">working Rails environment</a>.  For Mac users, <a title="Locomotive" href="http://locomotive.raaum.org/">the latest version of Locomotive</a> has everything you need for creating web services.  For everyone else you'll have to make your Rails environment the old fashioned way, although you can look forward to <a title="rubuntu" href="http://brainspl.at/articles/2006/02/16/rubuntu-is-almost-born">Rubuntu</a> soon.  We're going to create a very simple web service that accepts a string, changes it a bit and returns a string.

First create yourself a new application

<code>rails WebServiceProvider</code>

Then you'll want to open your application in your favorite Rails editor.  Then we need to generate your web service.

<code>./script/generate web_service Manipulation manipulate</code>

This will create an API file for us to define our web service's interface.  It also creates a controller for us to use, and then a test file for us to use later (we won't get to scripted testing in this article, although we will test it manually to prove that it works).

Now open up your manipulation_api.rb file in app/apis.  You'll see the following line of code that is the beginnings of our string manipulating web service.

<code>api_method :manipulate</code>

We'll need to define parameters and data types for our method like so:

<code>api_method :manipulate, :expects =&gt; [:string], :returns =&gt; [:string]</code>

There are many data types that can be used here, but we're keeping things easy for now.  Now we'll go look at the ManipulationController at app/controllers/manipulation_controller.rb.  Because we followed the standard Rails naming conventions the mapping of the web service to the controller is already done, but if we hadn't, this mapping can be done explicitly by adding the following to our controller.

<code>web_service_api ManipulationApi</code>

We can also give our web service a different name with the wsdl_service_name directive

<code>wsdl_service_name 'Manipulation'</code>

Notice also that in the controller is where we define all our logic for what happens with the parameters being passed in by our web service consumer.  the manipulate method has already been created for us, so we simply need to tell our method to accept a string, perform our logic, and return another  string.

Again we'll keep things simple.

<code>def manipulate(terms)
return "Yeah! " + terms + "!"
end
</code>

Now for all intents and purposes, our web service has been coded.  We'll add one more line to our controller that will generate a web front-end for the service so we can go see how it looks on the browser end.  Just add the following line to your controller.

<code>web_service_scaffold :invoke</code>

Now let's turn on the server and see how things look.  Back at the terminal type

<code>./script/server</code>

Open your browser and point it to <a title="invoke web service" href="http://localhost:3000/Manipulation/invoke">http://localhost:3000/Manipulation/invoke</a>.  This shows us the web view of our API.  Follow the manipulate link to see the auto-generated web form that will show us what our service looks like.  Type your message into Param0 box and click the invoke button to see all your beautiful web service XML.  Another important point for those wishing to consume your web service is that Rails is automatically generating your wsdl for you.  You can see how this works by checking the routes.rb file in app/config but just know that visiting <a href="http://localhost:3000/Manipulation/service.wsdl">http://localhost:3000/Manipulation/service.wsdl</a> you can see the WSDL file that others will need to use your web service.  You can use something besides service.wsdl by editing your routes.rb file appropriately.

Now this is obviously a simple example, but it illustrates the basic steps and important points.  You probably wouldn't have much use for a web service that adds the word "Yeah" and a few exclamation points to some user-input, but if we were doing this in the context of a real web application, you can start to imagine the possibilities available in your controller if you've got a dynamic database-driven application to work with.  You can add other methods to your API, define the param and return types there, then define the logic in the controller in the appropriate method.  Once you get the basics down, you're on your way and the sky is the limit.  Good luck developing your first piece of the Web 2.0.