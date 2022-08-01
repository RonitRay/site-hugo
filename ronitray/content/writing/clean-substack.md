+++
title= "Turn Substack articles into distraction-free blog posts in 60 seconds"
date= 2021-09-12
description= "Substack is nice and all, but I like a clean reading experience. Here's how you can get the best of both worlds."
[extra]
listed=true
+++

Substack seems to be the new hotness for a variety of established as well as enthusiast writers and bloggers, and I understand the appeal. They seem to provide a fairly good monetization plan and have an easy enough process for even less technical people to get started.

I have no interest in moving to Substack and have not bothered creating an account either. My experience with the site comes from having authors' Substack links show up on HN or Reddit feeds. My understanding is authors have granular control over whether they want to put their entire body of work or just the latest N posts behind a paywall or at least a subscription. Substack's entire business model revolves around these subscriptions. As a result, on the vast majority of Substack pages, there are several calls to action carefully strewn to get you to subscribe. Some of these calls to action are:

1. On the header
1. After a couple of paragraphs of text in the post
1. After a few more paragraphs of text
1. Popups
1. At the end of the article
1. After the comments and before the footer

and so on. 

These are not as egregious as some news sites, or as irritating as the antipatterns found on Medium.com. It also seems like Substack give authors some modicum of control over which, if any, of these that they want to display on their content, because not every Substack based site I have come across has all of them. It doesn't change two fundamental things about me, however:

1. When I view a webpage, I want the content and nothing more. I want to be off the site when I am done.
1. I am unlikely to subscribe to random Substack pages, and even if I were to, I would prefer using RSS and not their mechanism. I have enough tech smarts and agency to do that without having to be nagged repeatedly.

If both of these apply to you as well, or if you came across [my post on cleaning up the average StackOverflow page](/stackoverflow-faster) and are interested in applying these principles to other websites, you've come to the right place.

I have come up with a uBlock Origin cosmetic filter list that should do away with most random intrusive content on Substack pages and leave only the content you came for. The below steps assume you are using a supported browser (Firefox, Chrome, or Chromium derivatives like Brave, Edge, Vivaldi, Opera), and have installed uBlock Origin already.

1. After installing uBlock, click on the settings icon ![The icon for settings in uBlock Origin](/img/ublock_settings.png)
1. In the tab that opens, click on My Filters on the top bar.
1. Add the following lines to the text box:
    ```
    ! 2021-07-27 https://substack.com
    substack.com###nojs-banner
    substack.com##.subscribe-btn.subscribe-cta.primary.button
    substack.com##.notification-container.menu-button.button > svg
    substack.com##.footer
    substack.com##.subscribe-footer
    substack.com##div.single-post-section:nth-of-type(3)
    substack.com##div.single-post-section:nth-of-type(2)
    substack.com##.page-nav
    substack.com##[href^="/subscribe"] > .subscribe-btn.primary.button
    substack.com##td.icon.post-meta-item:nth-of-type(1)
    substack.com##div.subscribe-widget:nth-of-type(3)
    substack.com##div.subscribe-widget > .form > .sideBySideWrap > input
    substack.com##div.subscribe-widget > .form > .sideBySideWrap
    substack.com##td.icon.post-meta-item:nth-of-type(2)
    substack.com##td.icon.post-meta-item:nth-of-type(3)
    ```
1. Click on 'Apply Changes', close the tab and try opening any Substack page.

Welcome to clean textual goodness, the way God intended it.

## Notes:

1. This isn't some kind of hack that suddenly enables you to bypass paywalls and view restricted content for free. It only cleans up pages that are already available to you.
1. These rules apply only to Substack.com and author.substack.com kind of subdomains. However, a number of authors use Substack on their custom domains, so you might need to add these rules to your filter list again, substituting substack.com for the relevant domain.
1. Since Substack's business model is directly tied to subscriptions you make on the platform, these steps could be construed as attacking their income. And honestly, I'm fine with that. If I come across a writer whose work I am inclined to support, I will go out of my way to seek appropriate channels to do that. And Substack can forget about my money as long as they keep platforming and making money from the likes of Graham Linehan.

Ta.