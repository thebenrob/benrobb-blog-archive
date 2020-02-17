---
id: 32
title: Convert Line Breaks in Rails
date: 2007-01-26T10:55:44-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/26/convert-line-breaks-in-rails/
permalink: /2007/01/26/convert-line-breaks-in-rails/
dsq_thread_id:
  - "3051383714"
categories:
  - Old Stuff
---
This may not be news to anyone else, but it was a surprise to me when I ran into it, so I thought perhaps someone else might find it helpful.  Let's imagine that you've got a form with a textarea that allows for a decent amount of user input, like, say a blog post or a news item on your family website.

When you push the "Enter" key it goes down to the next line.  Behind the scenes, this is stored in your database as a new line character which is represented by "\n".  The problem is that "\n" has no meaning to a web browser.  In web browser language, what you really need is a line break represented by the "&lt;br /&gt;" tag.  So how do you get all your new lines to turn into line breaks?  The answer is one simple method added to your application_helper.rb file in your Rails project.
<code>
def line_break(string)
&nbsp;&nbsp;&nbsp;&nbsp;string.gsub("\n", '&lt;br/&gt;')
end
</code>

Then in your view, you simply call the line_break method around the appropriate block of text
<code>
&lt;%= line_break(@news.body) %&gt;
</code>

and that's all there is to it!