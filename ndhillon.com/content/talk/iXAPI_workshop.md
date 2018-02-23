+++
date = "2017-06-01"
title = "Market Data API Workshop"
abstract = "An Fixnetix Workshop on tools and methods for using the Market Access iXAPI"
abstract_short = "Dive into tools and methods for integrating applications to receive Market Data"
event = "iXAPI Workshop"
event_url = "https://github.com/nsdhillon/iXAPI_workshop"
location = "Fixnetix Inc, Boston, Massachutsetts"

selected = true
math = true

url_pdf = ""
# url_slides = "slides/blogdown-workshop-slides.html"
url_slides = ""
url_video = ""
[[url_custom]]
    name = "GitHub"
    url = "https://github.com/nsdhillon/iXAPI_workshop"
	
# [[url_custom]]
#    name = "Pre-work"
#    url = "html/ixAPI-workshop-meetup.html"	

# Optional featured image (relative to `static/img/` folder).
[header]
image = ""
caption = ""

+++

{{< figure src="/img/talk/iXAPI_workshop.png" >}}

The iXAPI is lightweight integration layer used to access Fixnetix's Low Latency Market Data system. It enables users to develop high-performance, event driven applications with builtin monitoring and resilency.

At its core iXAPI is designed to enable developers to write topic based publisher/subcriber messaging applications. Publishers send messages to a given topic, typically a string identifier such as "BNP", without any knowledge of the recipients (subscribers). Subscribing applications create subscriptions on topics of interest and receive all messages from all publishers for that topic. How the messages are constructed and transported is completely opaque to the client application (both at the publisher and subscriber side), meaning they do not need to understand the details of the underlying messaging system.

## Business Benefits:
* Reduce total cost of ownership through consolidation on a single messaging API
* Protect your technology investment and reduce time to market with new innovations
* Simplify the replacement of aging technologies
* Reduce complexity enabling your resources to apply greater focus on your core business
* Backed by major financial institutions and technology vendors

Sound complicated?  Join us on June 1st from 9:00AM to 4:00 PM for a discussion with iXAPI engineers on the evolving landscape of low latency communication.  We’ll explore iXAPI use cases and best pratices to create a low latency event driven application.
 
The workshop will be followed by food, drinks from 4:00 - 5:30PM:

iXAPI Workshop is a *work in progress*. We created [this repository](https://github.com/nsdhillon/iXAPI_workshop) as an education and demonstration tool for clients curious about how documentation, open science workflows, and tools like Github can contribute to a healthy and productive implementation. 

Your ideas and contributions are welcome!
