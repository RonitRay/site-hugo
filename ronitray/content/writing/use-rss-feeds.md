+++
title= "Reclaim Control Over Your Content Consumption with RSS Feeds"
date= 2021-02-09
description= "RSS feeds have been around forever, and remain as relevant today as they were years ago. They might be a way out of the social dillemma, and here's how you can start using them."
[extra]
listed=true
+++

This is part 1 in a two-part series on RSS feeds.

The early internet was, I believe, truly ahead of its time. We have a lot more eye candy and fancy functionality today, that's for sure, but some of the most enduring ideas at the foundation of the internet are just a little younger than the internet itself. One of these is the RSS feed. No
matter what your site is, what content you post, or how it looks, an RSS feed is able to standardize its contents into a single XML file that can then be used to track updates, or what we have come to call "follow" you.

My understanding is that RSS feed usage peaked during the peak of Google Reader in the mid-2000s. It seems to have all been downhill since then. Today, RSS has a small but faithful fanbase, and though it is seeing a silent resurgence by being the backend for podcasts, it has largely been
relegated to oblivion. I feel like there are two major reasons to this. 

The first is that RSS being simple yet flexible means it affords a great deal of control to the site owner as well as the follower over how they want to follow and consume content. You can view the entire post without leaving your feed reader, or can see a short summary and then jump straight to the site to read the rest of the post. This freedom and control is antithetical to the foundation of modern social networks, which rely heavily on addictive patterns and engaging UX shenanigans to keep you immersed and engaged on the platform for as long as possible. They need you to let them curate what you see, and to keep scrolling so they can serve you ads and make money off you. It was never about the content, or at least it hasn't been for a while and is likely never going to be
unless the economic structures underlying these systems are overhauled completely. 

The second, less controversial reason is that the web is just a lot more diverse than it was before. It can be hard to reduce an entire website to a single feed of updates, although it really shouldn't be and this feels like a design flaw that can be remedied today itself. It is of course worth making a distinction between the "document web"- your news sites, blogs, personal websites, job listings, classifieds and so on- and the "application web"- intensive, interactive applications that aren't just read-only and typically require user input. The application web certainly has a place in the online landscape, but the document web undoubtedly deserves to be simpler to browse and access.

If you want to escape the social dillemma and regain control over your consumption habits, there is nothing better than RSS. Here's how you can get started.

**Picking a client**

You need a client to view RSS feeds, and there are some great options out there for any platform of your choice.

Cross-platform: There's a lot of cross-platform RSS services that let you follow your news and subscriptions on any device of your choosing, and even sync reading history so you are always up to date and never see any redundant information. Of these, my recommendations are [TinyTinyRSS](https://tt-rss.org/) or [Miniflux](https://miniflux.app/) if you can self-host, or [TheOldReader](https://theoldreader.com/), [BazQux](https://bazqux.com/), [Feedly](https://feedly.com/), [InoReader](https://www.inoreader.com/) and [NewsBlur](https://www.newsblur.com/) otherwise. All very solid services.

Desktop: For Windows, [NewsFlow](https://www.microsoft.com/en-us/p/newsflow/9nblggh58s5r?activetab=pivot:overviewtab) seems to be a pretty good option. Mac users can use [Reeder](https://www.reederapp.com/), which is pretty popular. Linux users have quite a few options available to them. For a more traditional GUI experience, I recommend [NewsFlash](https://gitlab.com/news-flash/news_flash_gtk), [Liferea](https://lzone.de/liferea/) or [QuiteRSS](https://quiterss.org/). However, terminal users will find a lot of value in [newsboat](https://newsboat.org/) or [elfeed](https://github.com/skeeto/elfeed) if you use emacs.

Mobile: On Android, the best reader I have found is [Flym](https://play.google.com/store/apps/details?id=net.frju.flym&hl=en_US&gl=US). [Reeder](https://www.reederapp.com/) (linked above for MacOS) has an iOS client as well. If you're using any cross-platform service, their app/PWA is likely to be good too, and some 3rd party clients also let you hook them up to these services to sync your reading history.

**Finding RSS Feeds**

Modern RSS readers and services have search inbuilt that will let you add several sources without having to context-switch. A lot of sites you go to will put the RSS feed up front, typically in a header/footer or on the front page. However, this may not be true for quite a few sites due to the declining influence of RSS on the modern web. Fear not; all is not lost. A number of sites just have so much content that they might not put up the RSS link in a noticeable spot, or might just leave it in the source but not advertise it at all. Several websites are built on modern content management systems that all provide RSS feeds, while others still follow standard web practices and can be scraped to create feeds. It is worth trying the following:

1. Add a /feed, or /rss, or /rss.xml or /feed.rss to the URL and see if it returns an XML file.
2. On desktop, view the source for the site's front page and Ctrl+F to search for the words "feed". "rss", or "atom".
3. For reddit, you can add a ".rss" to the URL for any subreddit to get a feed for it.
4. HackerNews RSS feeds are available at [HNRSS](https://hnrss.org)
5. Finally, you can use [RSSBox](https://rssbox.herokuapp.com/), [rss.app](https://rss.app/), or [FetchRSS](http://fetchrss.com/) to generate feeds for a variety of sites, social networks, and other services. The likes of [dato.rss](https://www.datorss.com/) are also pretty useful if you want to search for feeds.

**Conclusion**

By relying on social media and big tech to curate our feeds for us, we become subservient to them, and very willing to stay within the bubbles they create for us. You can use RSS to reclaim this control, curate your own feeds, and read on your own terms. 

PS: If you're running a site of your own, keep an eye out for my next post, where I highlight how you can add an RSS feed to your site.
