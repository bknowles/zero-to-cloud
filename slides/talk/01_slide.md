# From Zero to Cloud in 90 Days with Chef

<center><img src="../images/oc-chef-logo.png" height="394" width="500" /></center>

<center>Created by Brad Knowles</center>
<center>Based on materials from Chef Fundamentals OPS150-04.01 by Opscode, Inc.</center>

.notes These materials are Copyright © 2012 Brad Knowles,
All rights reserved.  Based on work that is Copyright © 2010-2012
Opscode, Inc., All rights reserved.  This work is licensed under a
Creative Commons Attribution Share Alike 3.0 United States License.
To view a copy of this license, visit
http://creativecommons.org/licenses/by-sa/3.0/us; or send a letter
to Creative Commons, 171 2nd Street, Suite 300, San Francisco,
California, 94105, USA.

# Speaker

* Name: Brad Knowles
* Company: ihiji, Inc.
* Experience: System Administrator/Engineer/Consultant: 20+ years
    * Chef user: since 2011-09-14
* Contact
    * E-mail: bknowles@ihiji.com
    * Twitter: @bradknowles
    * github: bknowles

# What does ihiji do?

ihiji invision is a web based solution that provides a secure gateway
for residential electronics systems contractors & integrators to
remotely monitor, service and maintain client's in-home electronic
systems, including but not limited to, audio & video equipment,
network devices, etc....

This comprises an on-premise appliance and back-end supporting cloud
infrastructure with web portal for dealers to remotely monitor and
manage equipment that is installed at the client site

.notes Also included are media servers, home
computers, UPSes & PDUs, printers, projectors, temperature sensors,
video conferencing equipment, lighting equipment, and so on.

# What Can Be Monitored?

* Any IP Device
    + Ping
    + Well known ports and services (e.g., HTTP, FTP, Telnet, SSH, etc...)
    + Any device supporting SNMP
    + Control4 devices
* Any RS-232, Zigbee, AMX AxLink or Crestron Cresnet Device
* Custom monitoring modules can be written to support any IP based AV device

# Problem

Company is growing fast, but old ad-hoc hand-built infrastructure
can't scale nor can it be (easily) made fault-resilient

# Problem

Company is growing fast, but old ad-hoc hand-built infrastructure
can't scale nor can it be (easily) made fault-resilient

<center><img src="../images/1024px-Overloaded_truck.jpeg" height="338" width="512" /></center>
<center>By Ferdinand Reus from Arnhem, Holland (Safari Uploaded by mangostar)</center>
<center>[<a href="www.creativecommons.org/licenses/by-sa/2.0">CC-BY-SA-2.0</a>],
<a href='http://commons.wikimedia.org/wiki/File%3AOverloaded_truck.jpg'>via
Wikimedia Commons</a></center>

# Solution

* Rebuild from scratch
* In the cloud
* Must be scalable
* Must perform well
* Must be fault-resilient
* Must be very competitive re: cost/performance
* Using repeatable automated infrastructure management systems

# Introducing Chef

<center><img src="../images/oc-chef-logo.png" height="394" width="500" /></center>

# Chef Can Help

Chef is designed to help manage this kind of complexity. You may have
met already!

* Configuration management tool
* Systems integration framework
* API for infrastructure management

.notes It is both a dessert topping and a floor wax!  ;-)

# Problem #2

I knew chef existed, but that was about it

I had a little prior exposure to configuration management tools
(cfengine, bcfg2), but only ever as a user of their services and
never as an admin or engineer who implemented them -- and I am not
a developer

However, I did have 20+ years of experience as a Unix/Linux System
Administrator/Engineer/Consultant, and I knew and trusted Matt Ray
from his days at Zenoss, and he convinced both me and the customer
that I could do this job with some training and hands-on experience

.notes I'm a mail systems guy.  I'm a DNS guy.  I'm an NTP guy.  I do
systems infrastructure.  I help design and implement highly scalable
systems.  But I had no previous cloud experience.

# Start Over Again at Zero

* Start work on August 16th, 2011
* In-depth interviews with management regarding current system design
* Reverse-engineer current systems
* Discover what needed to change and what could remain
* Working from first principles, deliver design documents:
    + High Level Architecture (40k foot)
    + Mid Level Services (10k foot)
    + Detail Level (one service @ 5k foot)
    + Project Goals
    + Rules of Thumb for Scalability
    + Next-generation Services and Service Names
* Use a couple of cloud instances to do some early testing

# Training & Consulting

* Chef Fundamentals with Matt Ray
    + September 13th, 2011
* Rapid Prototype Infrastructure
    + Afternoon of September 13th, 2011
    + My first commit was on September 14th, 2011
    + Consulting complete by evening of September 15th, 2011

# Timeline
