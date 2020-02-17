---
id: 19
title: 'Howto: Port forward to Your Virtual Machine'
date: 2007-01-20T11:36:49-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/01/20/howto-port-forward-to-your-virtual-machine/
permalink: /2007/01/20/howto-port-forward-to-your-virtual-machine/
dsq_thread_id:
  - "3051383942"
categories:
  - Old Stuff
---
So sometimes I do things just for the fun factor. As mentioned in a previous post, I like having Windows server, but I prefer Linux for web-hosting. I finally found the solution to do both at the same time on one machine. In the real world people have been doing this for years, but it’s a first for me.

After doing all my installing, I then installed VMWare’s now free VMWare Server. I downloaded the Ubuntu Server distro and decided on the 6.10 release dubbed Edgy Eft. It doesn’t have the LTS, but is perfect for my needs because the repositories include everything I need for my Ruby on Rails setup (including Lighttpd).

Then I just had to figure out how to get traffic from my host to my virtual host. I wanted to use Bridged Ethernet and did that originally, but even though my VM grabbed an IP address on my Lan, when trying to access it from another computer, I was told that there was:

No route to host

If you’re smarter than I am, you can probably figure out a way around this, but I was just trying to get it to work. I turned to NAT. Go to VM &gt; Settings &gt; Ethernet in your VMWare Server Console, select NAT, and click OK.

Now boot your VM log in, and run an

ifconfig

to see what your IP Address is. Again in your server console go to Host &gt; Virtual Network Settings. Select the NAT tab. Make sure to move this window so you can clearly read your VM’s IP address. VMNet8 is the default virtual adapter for NAT, so if this is your only VM go ahead and click the Edit button (if you have others, make sure to select the proper adapter for your VM from the dropdown menu, then click edit). Now click the Port Forwarding button and then the Add button. Fill in the host port, the VM ip address, and the VM port. For me this meant forwarding port 80 from the host to port 80 on the VM. Don’t forget a nice description. Click OK 4 times. Now just forward traffic through your router (as needed) and you’re good to go.

My Ubuntu VM is now serving Apache2+MySql+PHP5 to the world. Soon it will be serving Ruby on Rails.

For a graphical tutorial see:
<ul>
	<li><a href="http://www.vmware.com/support/ws55/doc/ws_net_nat_advanced.html" title="VMWare howto">The Official VMWare HowTo</a></li>
	<li><a href="http://www.howtogeek.com/howto/vmware/allow-access-to-a-vmware-virtual-machinenat-from-another-computer/" title="How-To Geek">The How-To Geek</a></li>
</ul>