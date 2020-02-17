---
id: 38
title: 'Howto: Make a Rails Environment in Ubuntu'
date: 2007-02-01T08:41:08-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/02/01/howto-make-a-rails-environment-in-ubuntu/
permalink: /2007/02/01/howto-make-a-rails-environment-in-ubuntu/
dsq_thread_id:
  - "3051383374"
categories:
  - Old Stuff
---
In class today, there was a demonstration on how to get Apache/Axis/Tomcat running to demo some SOAP web services written in Java.  As I plug Rails again, I was again amazed at the simplicity with which Rails handles all this.  I began to think that there might be some interest in Rails web services for those other members in my class, so in an attempt to help them out, I decided to provide instructions on setting up a Ruby on Rails environment.

Now I'm running mine inside a virtual machine with <a href="http://www.vmware.com/products/server/" title="vmware server">VMWare Server</a> on my Windows Server 2003 box.  I won't get into all the reasons here, but these intructions would work for any VM or for a real install as a host operating system.  There are only one or two differences and I'll point them out as we go along.

<strong>1. Start with <a href="http://www.ubuntu.com/products/GetUbuntu/download#currentrelease" title="ubuntu server">Ubuntu Server</a> distro.</strong>  I'm using Ubuntu 6.10 Edgy Eft.
Find the mirror you want, then click the Other Installation Options and find the server.  If you must have a graphical environment, you can get the desktop version, but know that youll have to install apache2 and mysql on your own.  If you choose the server option, you'll be asked what kind of install you want to do.  Pick the LAMP option.  Do all appropriate setup, naming, networks, etc., and I'll meet you again at the shell after you login.

<strong>2. Edit your sources list.</strong>

<code>sudo vi /etc/apt/sources.list</code>

Once you get inside, you'll want to uncomment 4 lines, which will enable the universe repository along with the security universe repository.  I typically comment out the cdrom: repository as well.  For those unfamiliar with vi, the letter <strong>x</strong> will delete a single character.  Pushing the letter <strong>i</strong> will put you in insert mode to comment our the cdrom line.  Pushing <strong>Esc</strong> will get you out of edit mode. Pushing <strong>:</strong>, then <strong>wq</strong>, and finally <strong>Enter</strong> will put you back at shell with an edited sources list.

<strong>3. Get SSH running</strong>
For me this is essential.  The interface through VMWare isn't the speediest thing, and when you're running over a Remote Desktop connection, things start to feel like molasses.  A few things will fix us right up, because through SSH everything runs beautifully.

<code>sudo apt-get install openssh-server</code>

This will install and start the SSH server.  Now you may need to configure port-forwarding through port 22 in order to connect to your Rails/Ubuntu server.  In addition if you need to forward traffic to your VM, then at your router point port 22 at the host OS and <a href="https://benrobb.com/2007/01/20/howto-port-forward-to-your-virtual-machine/" title="Port forwarding to a virtual machine">follow my other instructions</a> on port forwarding to a virtual machine.

If you're happy where you're at, then you can skip step 3.  If you want to do it, then SSH to your new server and continue to Step 4.

<strong>4. Update all your packages</strong>

<code>sudo apt-get update
sudo apt-get upgrade
sudo apt-get install saidar</code>

Saidar is optional, it's a neat little monitoring utility that runs at the command line, but tells you about your CPU usage, memory usage, disk usage, and everything else you'd expect from your Task Manager or Activity Monitor.  Now it's time to get down to business.

<strong>5. Install Ruby</strong>

<code>sudo apt-get install ruby ruby1.8 ruby1.8-dev ri rdoc irb libmysql-ruby libmysqlclient15-dev</code>

If you didn't choose the LAMP option earlier (or picked a desktop distro) you'll want to add Apache2 and mysql-server to this list:

<code>sudo apt-get install ruby ruby1.8 ruby1.8-dev ri rdoc irb libmysql-ruby libmysqlclient15-dev apache2 mysql-server</code>

<strong>6.  Install RubyGems</strong>
RubyGems is like the apt-get utility for strictly Ruby packages.  This series of commands at the shell will download, install, and clean up the RubyGems package.

<code>wget http://rubyforge.org/frs/download.php/11289/rubygems-0.9.0.tgz
tar -xvzf rubygems-0.9.0.tgz
cd rubygems-0.9.0
sudo ruby setup.rb
cd ~
rm -rf rubygems-0.9.0
rm rubygems-0.9.0.tgz</code>

<strong>7. Install Rails</strong>

<code>sudo gem install rails --include-dependencies</code>

This will show some errors while installing documentation, but never fear.  All is well.  We both know that you weren't planning on reading the documentation anyway.

<strong>8. Install Lighttpd with FastCGI</strong>

<code>sudo apt-get install lighttpd libfcgi-dev libfcgi-ruby1.8 build-essential
</code>

This will show an error that it tried to bind to port 80 and failed.  That's ok, because we have apache running there.  What we've done is simply install it so that our Rails apps will use Lighttpd rather than the built-in WEBRick.

If like me you really just don't like errors you can edit the lighttpd.conf file so that it binds to a different port.  This is not necessary at this point, but if you plan on running Rails apps in production you'll have to play with the lighttpd config file at some point anyway.

<code>vi /etc/lighttpd/lighttpd.conf</code>

Find and uncomment the line that says

<code># server.port = 81</code>

Now we'll run Stop just to make sure and then Start it up again.

<code>sudo /etc/init.d/lighttpd stop
sudo /etc/init.d/lighttpd start</code>

Now install the fcgi RubyGem:

<code>sudo gem install fcgi</code>

<strong>9. Make sure that your FastCGI bindings and MySQL bindings are working properly.</strong>
Now to make sure that our fastcgi and mysql libraries are working properly, we'll fire up IRB.  IRB stands for Interactive Ruby.  It basically gives us a functional, yet empty ruby environment to play around.

<code>irb
irb(main):001:0&gt; require 'mysql'
=&gt; true
irb(main):002:0&gt; require 'fcgi'
=&gt; true</code>

Now, unless you want to do all your mysql configuration from the command line, you'll need to be able to connect as root to your mysql database from a remote host.  See <a href="https://benrobb.com/2007/01/15/howto-remote-root-access-to-mysql/">my instructions</a> on how to do that.  You may need to set up port forwarding through port 3306 in order to get this to work.