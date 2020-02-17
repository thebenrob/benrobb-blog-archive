---
id: 40
title: 'WSDL, Rails, &#038; Complex Data Types'
date: 2007-02-05T15:14:20-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/02/05/wsdl-rails-complex-data-types/
permalink: /2007/02/05/wsdl-rails-complex-data-types/
dsq_thread_id:
  - "3051383339"
categories:
  - Old Stuff
---
This could also be considered part three of my HowTo: Put WSDL on Rails series, but it's not really a HowTo in the strictest sense of the word.  Therefore, this article is more of a monologue than a set of instructions.

If you've stuck with me this far you've probably figured out that I'm discovering things on my own shortly before I spew them all out here.  In <a href="https://benrobb.com/2007/01/30/howto-put-wsdl-on-rails/" title="Howto put WSDL on Rails">Howto: Put WSDL on Rails</a> we built a simple web service that would accept a string parameter, modify it, and send the modified version back to the user.  In <a href="https://benrobb.com/2007/02/01/howto-put-wsdl-on-rails-part-2/" title="Howto put WSDL on Rails [part 2]">Part 2</a>, we subscribed to (and used) that same web service using only the WSDL.  At the time I thought I was done, but as I've played around a bit more, I realized that there was another major part of web services.  So now we'll cover dealing with complex data types.

I began by wondering what kinds of things besides [:string] you could pass as parameters to and from a web service.  I finally happened upon the Ruby on Rails manual that somehow I had not discovered up to this point.  Why don't these pages come up higher in the Google search results?  Rails uses ActionWebService to interact with web services of all kinds and you can find the beginning of the manual <a href="http://manuals.rubyonrails.com/read/chapter/67" title="What is Action Web Service?">here</a>.  You can find the specific answers to my questions <a href="http://manuals.rubyonrails.com/read/chapter/68" title="Defining an API">here</a> and <a href="http://api.rubyonrails.org/classes/ActionWebService/SignatureTypes.html" title="SignatureTypes">here</a>.

After reading this and mulling it over a bit, everything was pretty clear except for the so-called Structured Type parameters.  I set out to gain a better understanding of this, and this is what I accomplished.  First off, you'll want to read up an something called a <a href="http://api.rubyonrails.org/classes/ActionWebService/Struct.html" title="Struct">Struct</a>.  In essence an ActionWebService::Struct is a special kind of object that can be used for web services, but doesn't have any ties to a database like an ActiveRecord::Base object.

I first defined a new struct in <strong>app/models/weather_report.rb</strong> of my WebServiceProvider.

<code>class WeatherReport &lt; ActionWebService::Struct
member :zip, :int
member :temp, :int
member :wind_speed, :int
member :wind_direction, :string
end
</code>

I then created the proper method in my API at <strong>app/apis/weather_api.rb</strong>:

<code>api_method :get_weather, :expects =&gt; [:string], :returns =&gt; [WeatherReport]</code>

And since I was really just curious to see how this works, I defined a very dynamic method in <strong>app/controllers/weather_controller.rb</strong>:

<code>def get_weather(zip_code)
return WeatherReport.new(:zip =&gt; 84097, :temp =&gt; 55, :wind_speed =&gt; 5, :wind_direction =&gt; 'SW')
end</code>

And that's really all there is to it.  If you've got a database driven application you could simply pass in one of the models that corresponds to a table on your database.  So instead of an ActionWebService::Struct you could just pass in an ActiveRecord::Base object with the exact same syntax.

Now to see what comes out on the other end.  In another application, I subscribed to my web service and in my view put <code>&lt;%= debug @result %&gt;</code> with <code>@result</code> being the result of my GetWeather call to the web service.

The debugged results came out like this.

<code>#&lt;soap::mapping::object:0x14868c6 {}zip="84097" {}wind_direction="SW" {}wind_speed="5" {}temp="55"&gt;</code>

Carrying this logical line one step further, if a web service required a complex data type as input, we could build an ActionWebService::Struct object or use an appropriate ActiveRecord::Base object to pass into a third party web service.  I see the struct option being much more useful ona day to day basis, but in a B2B environment, you can start to see a place for some real hard-core service interactions passing full-blown database-drive object types around between systems.

As I began to play around with web services, I thought they were pretty neat, but I'm beginning to see the how powerful they could be given the right set of circumstances.