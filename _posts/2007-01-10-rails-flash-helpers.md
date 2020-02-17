---
id: 6
title: Rails Flash Helpers
date: 2007-01-10T11:17:34-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/10/rails-flash-helpers/
permalink: /2007/01/10/rails-flash-helpers/
dsq_thread_id:
  - "3089028820"
categories:
  - Old Stuff
---
Rails allows for the posting of errors through use of flashes. Calling something like

flash[:notice] = "Login Successful"

in your controller will allow you to display it in your view by calling the following code in your view.

<%= flash[:notice] %>

The types of flashes you can use are not pre-defined so if you wanted to use

flash[:pearl_jam]

you could. That being said, there are some generally recognized types of flashes that folks are standardizing around. The most common flashes that I've seen are:

flash[:notice]
flash[:message]
flash[:warning]
flash[:error]

I found some code at http://www.bigbold.com/snippets/posts/show/2348 that helped me out. You can edit it to suit your own needs. All you need to do is put thes code in your application_helper.rb file. It will allow you to call

<%= display_standard_flashes %>

in any of your views to display all flash types. This code also adds CSS class definitions that match the flash name, which will allow you to define a different look for your different flash types.