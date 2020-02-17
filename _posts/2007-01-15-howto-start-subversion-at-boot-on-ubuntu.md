---
id: 12
title: 'Howto: Start Subversion at Boot on Ubuntu'
date: 2007-01-15T11:25:19-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/15/howto-start-subversion-at-boot-on-ubuntu/
permalink: /2007/01/15/howto-start-subversion-at-boot-on-ubuntu/
dsq_thread_id:
  - "3051383207"
image: /wp-content/uploads/2007/01/Ubuntu-87x90.png
categories:
  - Old Stuff
tags:
  - featured
---
I don’t know if I’ve extolled the virtues of Ubuntu on this blog yet, but they are many. They are, however, not the topic of this post. Every once in a while, I like to try different operating systems on my server, and at the moment, I’m just coming back to an Ubuntu server after a brief fling with Windows Server 2003.

On the list of things to do after install was to get Ubuntu to start the svnserve daemon at boot. I’ve taken the time to look this up enough times that I figured I’d just add it here. This procedure holds for anything you’d like to do at boot, I’m simply running my svn daemon.

<strong>Step 1 - Create your script.</strong>
Simply create a new file (I called mine svnserve) and type the command you’d like to run

<code>cd /etc/init.d/ # (thanks Alfonso)
sudo touch svnserve
sudo vi svnserve
svnserve -d -r /usr/local/svn/repository_name</code>

<strong>Step 2 - Save the script in the /etc/init.d/ folder</strong>

<strong>Step 3 - Make the script executable</strong>
<code>sudo chmod +x svnserve</code>

<strong>Step 4 - Add the script to the boot sequence</strong>
<code>sudo update-rc.d svnserve defaults</code>

That’s it. When you’re done you should see some output similar to

<code>Adding system startup for /etc/init.d/svnserve ...
/etc/rc0.d/K20svnserve -&gt; ../init.d/svnserve
/etc/rc1.d/K20svnserve -&gt; ../init.d/svnserve
/etc/rc6.d/K20svnserve -&gt; ../init.d/svnserve
/etc/rc2.d/S20svnserve -&gt; ../init.d/svnserve
/etc/rc3.d/S20svnserve -&gt; ../init.d/svnserve
/etc/rc4.d/S20svnserve -&gt; ../init.d/svnserve
/etc/rc5.d/S20svnserve -&gt; ../init.d/svnserve</code>