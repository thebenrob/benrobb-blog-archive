---
id: 371
title: 'WordPress Integration with Facebook &#038; Twitter'
date: 2012-03-10T16:18:59-07:00
author: Ben
layout: post
guid: http://benrobb.com/?p=371
permalink: /2012/03/10/wordpress-integration-with-facebook-twitter/
al2fb_facebook_image_id:
  - "372"
al2fb_facebook_link_id:
  - 569851180_10150718519126181
al2fb_facebook_link_time:
  - 2012-03-10T23:19:02+00:00
al2fb_facebook_link_picture:
  - meta=https://benrobb.com/wp-content/uploads/2012/03/wordpress-facebook-twitter-150x150.jpg
dsq_thread_id:
  - "3413509222"
image: /wp-content/uploads/2012/03/wordpress-facebook-twitter-180x160.jpg
categories:
  - Old Stuff
---
<a href="https://benrobb.com/wp-content/uploads/2012/03/wordpress-facebook-twitter.jpg"><img class="aligncenter size-full wp-image-372" title="wordpress-facebook-twitter" src="https://benrobb.com/wp-content/uploads/2012/03/wordpress-facebook-twitter.jpg" alt="" width="300" height="282" /></a>

Today, I setup a couple of WordPress plugins for automatically posting blog links to Facebook and Twitter.
<h3>WP to Twitter</h3>
The first is <a title="WP to Twitter Plugin" href="http://wordpress.org/extend/plugins/wp-to-twitter/">WP to Twitter</a>.  Instructions are pretty straightforward for creating a Twitter app for integration.  Small hitch was that after creating my Access Token I had to reload the page in order for the access tokens to actually show up.  Now whenever I create a new post, it will post a Tweet using my Twitter account with a link back to my post.  Bit.ly integration is supported, WP tags are converted to Twitter hashtags and there are a few other options as well.
<h3>Add Link to Facebook</h3>
The second plugin is <a title="Add Link to Facebook Plugin" href="http://wordpress.org/extend/plugins/add-link-to-facebook/">Add Link to Facebook</a>.  The name of this one is somewhat of a misnomer because it does way more than just add links.  It appears to integrate blog comments and Facebook comments as well as a host of other features.  For now, I'm only planning on using it to post links, but I will probably explore some of the other features later on.

Setup for this one was a bit more complicated.  The plugin page has a setup guide as well as an FAQ.  When attempting to authorize the application within the WP setup, I kept getting a redirect_uri error on setup end eventually ended up deleting the plugin, deleting the Facebook app I had created and starting from scratch a second time.  The second time through creating the Facebook app I caught a message that said the app had been created, but could take "several minutes" to replicate across their servers.

I decided to wait for awhile.  After 15 minutes or so, I was still receiving the error, so I went to play Legend of Zelda for awhile, and tried again an hour or so later.  This time, it went to Facebook and authorized just fine, and now I'm just playing with different settings.