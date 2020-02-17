---
id: 20
title: Coupling vs. Cohesion
date: 2007-01-20T11:38:24-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/20/coupling-vs-cohesion/
permalink: /2007/01/20/coupling-vs-cohesion/
dsq_thread_id:
  - "3213363864"
categories:
  - Old Stuff
---
Coupling &amp; Cohesion are two terms often used in object-oriented software development. They sound rather similar, but have very different meetings.

Coupling refers to one components unnecessary dependence on another components implementation. Cohesion refers to multiple components linked in logical and smart ways.

Jeremy Leishman has <a href="http://jeremyl-isys532.blogspot.com/2007/01/coupling-versus-cohesion.html" title="coupling vs cohesion">shed a little more light on the topic</a>. Coupling is the degree to which modules within a program rely on each other. If the modules interact through a stable interface without having to worry about the other’s particular implementation, they are said to be loosely coupled. This is good.

Cohesion refers to how well each individual module does its job. It measures how focused the responsibilities of each class are. In good object-oriented programming, responsibilities can be specifically assigned in ways that increase reuse and code management capabilities. Modules implemented this way are said to be highly cohesive. This is also good.

An example might help to clarify things a bit more. Let’s say we had an iPod object and a Song object. If the two were highly coupled, the Song class might look something like this (Ruby style):

class Song
def do(action)
if action == 1
# code to play song...
elsif action == 2
# code to pause
elsif action == 3
# code to skip
endif
end
end

Any programmer that wants the iPod object (or the WinAmp object, or any other object) to interface with the Song object is now dependent on the special meaning of 1, 2, &amp; 3 to use the Song object correctly. The iPod object and the Song object are highly coupled. Remember that highly coupled = bad.

Now consider another implementation of the iPod and Song objects. Highly cohesive objects talk to each other semantically. In other words, they tell each other what they want the other one to do. The more descriptive your methods are, the better they are.

class Song
def new(path_to_song)
#code to get the song from the filesystem
end

def self.play
#code to play song
end

def self.pause
# code to pause song
end
end

This would allow the iPod object to call

currentSong = Song.new("/home/user/Music/1812_Overture.mp3")
currentSong.play
currentSong.pause

Now the Song object is said to be highly cohesive because it’s responsibilities are very focused and other objects that wish to interact with it can do so in a uniform way regardless of how the Song object is implemented on the backend. Other objects don’t need to know how the Song object works, they just know that it does and can talk to it in an intelligent way. Remember that highly cohesive = good.