---
id: 41
title: 'Cannot Map {objType} to SOAP/OM'
date: 2007-02-06T21:03:56-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/02/06/cannot-map-objtype-to-soapom/
permalink: /2007/02/06/cannot-map-objtype-to-soapom/
dsq_thread_id:
  - "3051384228"
categories:
  - Old Stuff
---
This was a strange exception that I struggled with for several hours this evening, but I have finally prevailed.

<strong>The Background</strong>
For my Information Architecture class, we've got to create a web service provider and a web service requester, this provided the initial impetus for my recent push into web services and the last few posts dedicated to the topic.  Now our professor has published a web service that basically dumps his database out into an array of complex data types.

His database is a weather reporting database that has zip code, temperature, humidity, etc.  The databse is small (currently 3 entries) and populated with completely fabricated data, this is a learning experience not an accurate forecaster.

Our task is to subscribe to his web service, and publish our own that will accept a string parameter as the zip code and return the single weather report for just that zip code.  I decided that I'd just subscribe to his web service in my controller, find the appropriate weather report, create my own Struct for my web service, and push it out to my subscribers.

<strong>The Problem</strong>
Once I had received my professor's SOAP object back, I stepped into it to retrieve the zip codes from each entry.  When I found the matching zip code, I mapped his keys and values to my own with a line of code like this:

<code>return WeatherReport.new(:cityzip =&gt; row.cityzip, :temperature =&gt; row.temperature, :etc =&gt; ad naseum)</code>

There are ten different attributes that my object must return to my subscribers, so it was slightly tedious to put all these things together.  I prevailed.

When subscribing to my own web service via WSDL, however, I received the following exception:

<code>Exception: Cannot map WeatherReport to SOAP/OM</code>

WeatherReport is the name of the Struct that I was using as my return type.  I began meticulously checking all my code.  I had already written code to subscribe directly to my professor's web service, so I checked the SOAP object coming back from that.  I used a copy of the same code to subscribe in my own web service and could not figure out what was going on (hours pass).

I finally ran across <a href="http://blade.nagaokaut.ac.jp/cgi-bin/scat.rb/ruby/ruby-talk/211011">this email archive</a> that had a fix, but not an answer.

<strong>The Fix</strong>
I had to change my code to this:

<code>return WeatherReport.new(:cityzip =&gt; "#{row.cityzip}", :temperature =&gt; "#{row.temperature}", :etc =&gt; "#{ad naseum}")</code>

The "#{row.cityzip}" means that the object inside the {} should be interpreted as a variable and it's value should appear in the string instead of the variable name.  It's just a shorthand way of concatenating strings with the values stored in string variables (and in case you were wondering, yes, you must use double quotes or it won't work).

Now the most interesting thing about this error is that <code>row.cityzip == "#{row.cityzip}"</code>, meaning that the expression evalutates to <code>true</code>.  For all intents and purposes, these two strings are exactly the same.

Peter (the guy with the fix) speculates on what might be the cause, but he was also using the a Struct (via SOAP4R), so I assume that the problem's source may lie in that class.  Given the dearth of readily available information on the topic, I hope you find this useful.