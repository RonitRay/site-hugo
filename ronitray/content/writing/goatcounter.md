+++
title= "GoatCounter- Simple, Tracking-Free Analytics"
date= 2021-05-09
description= "Basic analytics, without any reliance on money-hungry ad networks, and without any tracking or privacy encroachment."
[extra]
listed=true
+++

I like the idea of analytics. I don't think it's a bad thing to know which posts of yours are getting traction, what your readers would like to read, and so on. I am, however, staunchly pro-privacy. I will not stand for any analytics or telemetry: 

1. whose purpose goes beyond introspection
1. which is used for collecting personally identifiable information
1. which is used to profile users
1. which is used to drive ad networks or sell collected data
1. which is heavy and increases the size (and therefore the loading time) of a website.

This, for obvious reasons, rules out the likes of some of the most popular analytics tools like Google and Facebook Analytics. I like the idea of analytics, but refuse to sell my soul or the visitors on my website for it. Thankfully, I don't have to.

[GoatCounter](https://goatcounter.com/) is a great minimal, [open-source](https://github.com/zgoat/goatcounter/) web analytics tool. It collects a minimal amount of data and does not link it to identities of users in any way. One of their [stated goals](https://www.goatcounter.com/why) is to *just “count events” rather than “get as much data as technically possible”* which works for me.

Like Google Analytics and many top providers, GoatCounter can be integrated with your site using a single line of JavaScript. This adds about 3.5kB of extra data to every page, which is fairly small. However, one of my goals for this site was to completely forgo JavaScript, or at least hold off on using it unless absolutely necessary. I don't believe analytics is a good enough reason to serve JavaScript, and would perhaps have reconsidered using Goat if that was the only option. Thankfully, it is not. They allow:

1. Sending data from server logfiles- A viable option if you are self-hosting or using a VPS, but I am not.
1. API requests from middleware or app backend.
1. Tracking Pixel- This is what I use. A 1x1 GIF added to every page that works without JavaScript. It is a leaner solution too, since it adds less than 500 bytes (yes, bytes) to each page. That is a 85% load reduction to something that was already a very small size. The way this works is with an image tag:

```html
<img src="https://[USERNAME].goatcounter.com/count?p=/[PAGE_NAME]">;
```

Where `[USERNAME]` is your GoatCounter username and `[PAGE_NAME]` is the name of your page that will show up on your analytics dashboard.

I want to be very transparent with this, so this is all the data GoatCounter collects for me:

1. User Agent: To see which browser and/or devices people access the site from
1. Country and Region: Just to get an idea of the demographic makeup of my audience
1. Session: Only to eliminate duplicate pageviews. The cited example on their site is: *Track unique visitors for up to 8 hours; if you disable this then someone pressing e.g. F5 to reload the page will just show as 2 pageviews instead of 1*

If this is still too invasive for you, you are likely using an adblocker of some sort. I have noticed that most ad-blockers (uBlock Origin, Adguard, StevenBlack hosts list etc.) are tuned to block any requests to or content loaded from GoatCounter, so this will not be an issue for you. You can also block this manually using a hosts file, for example.

Also in the interest of full transparency, I am opening up my analytics dashboard to the general public. You get to see all the data that I do, with no exceptions.

[My GoatCounter Dashboard](https://ronit.goatcounter.com)
