---
id: 39
title: 'Howto: Put WSDL on Rails [Part 2]'
date: 2007-02-01T23:22:12-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/02/01/howto-put-wsdl-on-rails-part-2/
permalink: /2007/02/01/howto-put-wsdl-on-rails-part-2/
dsq_thread_id:
  - "3051384034"
categories:
  - Old Stuff
---
In <a href="https://benrobb.com/2007/01/30/howto-put-wsdl-on-rails/" title="howto put WSDL on rails">the first article</a> about WSDL on Rails we created our own web service that accepted a string, modified it, and returned a new string.  Now we'll take a look at creating another application that can consume or subscribe to our web service.  This is almost too easy.  I figure the best way to demonstrate the simplicity is to keep this article as short as possible.

<strong>1. Fire up the old WebServiceProvider application that we created in Part 1</strong>

From the application root directory type <code>./script/server</code>

<strong>2.  Create a new WebServiceConsumer application</strong>

In a new terminal window type <code>rails WebServiceConsumer</code>

<strong>3. Create a controller for your service consumer</strong>

<code>cd WebServiceConsumer
./script/generate controller consumer</code>

<strong>4. Subscribe to your WebServiceProvider using its WSDL</strong>

Open up your consumer_controller.rb in app/controllers.  It will be empty and it needs to look like this:

<code>class ConsumerController &lt; ApplicationController</code>

<code>  require 'soap/wsdlDriver'</code>

<code>  def subscribe
if params[:terms] == nil
@service_output = ""
else
url = "http://localhost:3000/subscription/service.wsdl"
factory = SOAP::WSDLDriverFactory.new(url)
service = factory.create_rpc_driver
@service_output = service.Subscribe(params[:terms])
end
end
end
</code>
This is where the magic happens.  The line <code>require 'soap/wsdlDriver'</code> brings in the needed Ruby library.  The subscribe method is simply an action like any other in your application.  We're going to create a form that accepts some user input and then we'll pass them on to our WebServiceProvider.  The url, factory, and service lines could all be done in one line, but I've broken them out here to demonstrate.

If the box is left blank, we don't do anything.  If the user inputs some data, then we have a little bit of work to do.  We create a new service object based on the WebServiceProvider's description of itself as defined by its WSDL.  Then our local <strong>service</strong> object acts as a proxy and any method calls we make on the local object are simply passed on to it the actual WebServiceProvider.

We can then define our <code>@service_output</code> as a variable we can then call in our view.  Now for testing.

<strong>5.  Create two views for testing</strong>

In app/views/consumer create an index.rhtml file as follows:
<code>
&lt;html&gt;
&lt;head&gt;
&lt;title&gt;WebServiceConsumer&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;h1&gt;WebServiceConsumer&lt;/h1&gt;
&lt;p&gt;
Enter your terms below. They will be passed on to our web service and you'll be able to see the response.
&lt;/p&gt;</code>

<code>    &lt;%= start_form_tag :action=&gt; 'subscribe' %&gt;
&lt;p&gt;&lt;label&gt;Terms&lt;/label&gt;&lt;br/&gt;
&lt;%= text_field 'terms', '' %&gt;&lt;/p&gt;
&lt;%= submit_tag "Subscribe" %&gt;
&lt;%= end_form_tag %&gt;
&lt;/body&gt;
&lt;/html&gt;</code>

Also in app/views/consumer create subscribe.rhtml as follows:
<code>
&lt;html&gt;
&lt;head&gt;
&lt;title&gt;WebServiceConsumer&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;h1&gt;WebServiceConsumer&lt;/h1&gt;
&lt;p&gt;
The web service returned: &lt;br /&gt;&lt;br /&gt;
&lt;%= @service_output %&gt;
&lt;/p&gt;
&lt;/body&gt;
&lt;/html&gt;</code>

6.  Now fire up your WebServiceConsumer app on a different port

Depending on your particular setup this may be different.  I use lighttpd, so you'll need to open app/config/lighttpd.conf and change the <code>server.port = 3000</code> to say something like <code>server.port = 3100</code>.  Then you can run <code>./script/server</code> to fire up your app on port 3100.

Now point your browser to http://localhost:3100/consumer

Enter your terms into the text box, click <strong>Subscribe</strong>, and pat yourself on the back.  You've just subscribed to a web service.