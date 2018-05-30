---
title: "Building a Smart Home"
date: 2018-05-25T13:27:00+10:00

categories: []
tags: ['Home Automation', 'Vera', 'Home Assistant']
author: "Trent Scholl"

featuredImage: "/images/feature.jpg"
noSummary: false
---

This post is going to a series of blog posts about my on-going Home Automation
project.

For as long as I can remember I've always wanted to solve repeatable, manual
steps with some kind of automation. So when I bought my own house, naturally the
first thing I had to do was automate everything!

<!--more-->

Fast forward a couple of years and I've slowly been testing and trialing the
different automation products that have come on to the market. Although things
in the home automation space have come a long way in recent years, there's still
a lot to improve. One of the major issues in more recent times is the sheer
amount of solutions there are now available, and unfortunately they don't always
all play well together.

After much research on the various gateways available at the time, I decided to
purchase a [VeraLite](http://getvera.com/controllers/veralite/). The VeraLite is
hardware gateway that supports Z-Wave devices. It's relatively cheap and is a
mature product that has native support for hundreds of devices. The development
community is pretty active and it has a plugin architecture based on LUA.

![VeraLite](veralite.jpg#center "VeraLite")

The VeraLite was easy to use and a great place to start for simple auomations.
More complicated automations can be achieved with the help of the community
plugins and/or LUA code, however it becomes quite cumbersome to manage and is
incredibly difficult to debug why things weren't working.

Eventually it started crashing and rebooting at random times of the day and then
my unit would refuse to install the latest firmware (I was seriously unlucky
when my house got broken in to while my VeraLite was in a non-operating
state). After contacting their support team, I was advised that the VeraLite was
no longer able to handle the latest revisions of the firmware and it needed to
be upgraded manually (which they won't tell you how to do it yourself).

So it was time to find a new solution.

After evaluating the commercial hardware and software solutions, as well as the
free open source software solutions, I settled on
[Home Assistant](https://www.home-assistant.io/).

![Home Assistant](homeassistant.png#center "Home Assistant")

> Home Assistant is an open-source home automation platform running on Python 3. Track and control all devices at home and automate control. Perfect to run on a Raspberry Pi.

Home Assistant was a clear choice for me for a few reasons

+ I already have a HP Microserver that I can run it on
+ There is a Home Assistant component that can utilize my VeraLite as a Z-Wave hub
+ The configuration is YAML based

There are serveral options available to deploy Home Assistant (including their own OS based on [resinOS](https://resinos.io/) for Raspberry Pi), but as I already run Ubuntu on a HP Microserver, I've opted to run it inside a Docker container.

In my next post, I'll talk a bit about how I'm deploying Home Assistant and some of the devices I've set up.