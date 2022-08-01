+++
title= "Building a Sustainable Personal Wiki for Free"
date= 2021-07-11
description= "I like the idea of a personal wiki, but everything is expensive, over-engineered, or likely to disappear within 5 years. Here's how I navigate through this."
[extra]
listed=true
+++

Order is beautiful. My mind is an absolute mess, and the idea of offloading some of it into a structured place that I may never revisit, but can if I want to, is extremely appealing to me at the moment. I've also greatly been inspired by incredible public archives like [Nikita Voloboev's](https://wiki.nikitavoloboev.xyz/) and [Rasul Kireev's](https://rasulkireev.com/brain/). I think they're incredible and would very much like to build a personal repository that will outlive me and might bring value to someone after I'm gone. This is why I've been thinking about having a knowledge base/personal wiki for a while.

Personal wikis aren't exactly new, they've been around for as long as the web has, if not longer. However, my understanding is that fancy new tools like Notion, Roam, Obsidian etc. have caused a giant uptick in adoption for this habit over the last couple of years. It's hard to navigate YouTube without finding productivity channels talking about their "life OS" or "second brain" built on top of Notion nowadays. And I'm all for it.

## I don't want to use Notion, though. 

It's not that it isn't good, it's pretty great and people who call it a glorified text editor will have to jump through many hoops to name something that brings in the stuff that Notion does on top of basic Markdown. That said, I don't need most of those things, [plain text is perfectly good for me](/notes-workflow). 

Notion is free for personal use now, pretty good looking, easy to use, extensible, and all the other things their marketing department and army of promoters can tell you. That said, I just don't feel like it is for me. [Their TOS and Privacy Policy](https://www.notion.so/Terms-and-Privacy-28ffdd083dc3473e9c2da6ec011b58ac) are pretty transparent about the fact that privacy isn't exactly their priority. That's fine, it's their prerogative to prioritize functionality and the ability to make the platform free for so many users. It's just a trade-off I am not willing to make. 

Further, because Notion adds a whole lot of functionality over basic text or rich(er) text like Markdown, it's all too easy to get tied down and locked into the platform. To their credit, they allow [export to HTML, Markdown, or PDF](https://www.notion.so/Back-up-your-data-1a8eb5bdfce34d19a6360fd015c0075f), but you would lose out on the fancy bits that aren't directly compatible. You could just not use them and maintain a discipline to treat it as just a plaintext platform, but it's not easy to resist the charm, especially when it may actually be easier to use some of it than have to work around the limitations of just text files. 

The other problem here is that it seems their export functionality doesn't work very well. As seen in [this HN post](https://news.ycombinator.com/item?id=27612894) and the [follow-up from Notion's CEO](https://news.ycombinator.com/item?id=27613632), their export feature doesn't work at scale. And a personal wiki is likely to scale pretty quickly if you're diligently adding entries to it over a few years. I don't want to be locked in. I don't want to be reliant on a completely online service to have to do something as simple as writing. And I don't want to have to trust some random company to store my data or to *not* do something not to my taste or outright malicious with it.

So where do I go?

## My requirements

I'm not very picky, but here's what I need.

1. Free (libre), as in beer: I'm not above paying for something that brings great utility to my life and work, but I'm strapped for cash at the moment, and I would much rather use something that provides 90% of the utility for free than something else which offers spit and polish and marginal extra utility for a subscription or a lump sum price.
2. Preferably free, as in freedom: I like free software. I like what it stands for, I like what it can be and I like what the world could be if it was the default. I may not be qualified or interested in reading, understanding, and auditing the code for every FOSS tool that I use, but the social contract of the dev putting it out in the open, and the prospect of a community of which at least a subset might actually be both interested and capable of doing this means, at least in my opinion, that free software will always be superior to proprietary competitors. 
3. Plain text or Markdown support: Plain text stands the test of time. A whole lot of things could render your personal wiki inaccessible or unusable, but Unicode or ASCII going out of fashion or support is highly unlikely, or at least unlikely enough to be a gamble I am willing to take. Even if the tool of choice for viewing, editing, and searching the wiki goes out of support or disappears off the face of the earth, I can read, edit, understand and manipulate plain text just fine.
4. Sustainable: I should be controlling the data. This boils down to me having access to the files upon which the wiki is built. I should be able to back up, transfer, delete or do whatever I want with these files freely.
5. Relatively frictionless: I'm just going to be using it less and less if it's slow to start up or involves navigating a bunch of menus every time I have to capture a simple idea. 
6. Preferably cross-platform or easily shareable: I want to be able to edit or at least view the wiki from my phone, or share a relevant page with someone easily.

I think this isn't too much to ask for. I've basically been doing this with a folder structure and markdown files for personal notes anyway, but elevating that to a Wiki might take just a little more work.

## My Options

Let's review some of the popular options in the wikispace and see how they fare against my metrics.

### Notion (3/6)

Notion isn't really a dedicated personal wiki tool, but it very much finds application there. It actually fared better than I expected. Notion is pretty frictionless (once you get past the trap of continuously optimizing your templates for MAXIMUM PRODUCTIVITY(TM)). It is a web app, so works on anything that is relatively modern. It is now free for personal use, but wasn't always, and there aren't any guarantees that it is always going to be. I've already decided against it so there isn't much more to talk about here.

![Screenshot of a personal wiki template for Notion](/img/notion.webp)
[Image courtesy of notionpages.com]

[Check out Notion here!](https://notion.so)

### Obsidian (3.5 to 5/6)

Obsidian is probably really close to what I want because it is a dedicated knowledge base tool. It's great for privacy and control because it works on a local folder of Markdown files. It has some really beautiful power features and it allows for networked/linked visualization that is attractive and probably very useful too. It is cross-platform, and free for personal use without any major caveats. However, it is proprietary software, and costs $8/month/site, soon to become $16/month/site to publish your wiki to the web. Still pretty darn fantastic, I would say.

![Screenshot of an Obsidian screen](/img/obsidian.webp)
[Image courtesy of Obsidian's homepage]

[Check out Obsidian here!](https://obsidian.md/)

### MediaWiki (4/6)

MediaWiki is an incredibly robust piece of software, but it really isn't targeted at projects of a scale as small as my personal wiki. Everything about it screams the fact that it is aiming for large Wikipedia or project wiki style projects, with collaboration and many other great features. It is  completely free software released under GPLv2 and is designed to run on a server I own and maintain myself, so sustainability is a check mark too. My main issues with it are:

1. It's super over-engineered for what I need. I don't need (yet) or want to use a local web server or VPS (it's not really free of cost then, is it?). I don't think my wiki will be of the scale that it will ever need to run on a database.
2. I'd have to learn their markup which is fine and would probably pay off if I stuck to it, but again it adds to friction.
3. While the end product is somewhat viewable on any web browser, it is a far cry from responsive. [Their own wiki](https://www.mediawiki.org/wiki/Manual:Mobiles,_tablets_and_responsive_design) states that it is not at all optimized for mobile, but there are some workarounds that can make the experience a little more pleasant.

![Screenshot of the MediaWiki homepage](/img/mediawiki.webp)

I just don't think it's a good fit for me.

[Check out MediaWiki here!](https://www.mediawiki.org/wiki/MediaWiki)

### TiddlyWiki (4.5/6)

TiddlyWiki is fantastic. At first glance it ticks every box and should be the only thing I consider, and yet... very few things have boggled my mind as much as trying to understand it. It was incredibly overwhelming to wrap my head around it, and honestly I want something that gets out of my way rather than needing me to understand its intricacies and idiosyncrasies for a long time before getting any value out of it. Still, the scope of things that seem achievable with it is incredible, and it does seem to be capable of a perfect score if I toughen up and just get past the learning curve. It's a no, but only for now. We may yet have a wonderful time together.

![Screenshot of a TiddlyWiki page](/img/tiddly.webp)

[Check out TiddlyWiki here!](https://tiddlywiki.com/)

### Wiki.js (4.5/6)

It's about the same as MediaWiki in terms of metrics...Please don't make me have to maintain a database and a container and an application and a server/VPS for a pet project just yet.

![Screenshot of a Wiki.js page](/img/wikijs.webp)

[Check out Wiki.js here!](https://js.wiki/)

### GitBook (4.25/6)

GitBook is a SaaS. I'm not too keen on using something that can change the ToS on me. It's still good that it is based on markdown files that are super easy to shift elsewhere, but it's not exactly ideal to be at their mercy. At least with an executable you can use it as long as you have it, or downgrade to an old version if they introduce malicious elements or anti-features. Still, GitBook is one of the prettiest solutions I've seen, and I won't lie and say I'm not tempted.

![Screenshot of a GitBook page](/img/gitbook.webp)
[Check out GitBook here!](https://www.gitbook.com/)

### XWiki (5/6)

Again, very good but not for me. Hosting, database, so on and so forth. XWiki is Java based too, which is a language and platform I am fairly comfortable with. But I'll give it a miss for now.

![Screenshot of an XWiki page](/img/xwiki.webp)
[Check out XWiki here!](https://www.xwiki.org/xwiki/bin/view/Main/WebHome)

### DokuWiki (5/6)

This is another piece of software that really, really impressed me. Short of the fact that I don't want to self-host, it demolishes all of my criteria with flying colours. It's simple and seemingly great to use and navigate around. I had a great feeling reading their docs and can confidently say that if my present solution is ever inadequate and I find myself moving to a hosted solution, DokuWiki will most likely be at the top of my list of options to switch to, even ahead of TiddlyWiki due to sheer simplicity. Easily the best candidate so far, but I'm tempted to explore a little bit more before I consider coughing up the money for a cheap VPS.

![Screenshot of a DokuWiki page](/img/dokuwiki.webp)
[Check out Dokuwiki here!](https://www.dokuwiki.org/dokuwiki)

### Docusaurus and other static site generator-based solutions (5.5/6)

Docusaurus is a static site generator based on React, geared to churn out documentation-style webpages quickly. It's pretty good, I've toyed with it at work, but even the few commands here and there add to the friction for me. You can find documentation-style templates for any static generator of your choice. My own site is on a static site generator, and for the few posts a month I think it's perfectly fine. But I expect to use and update my wiki more than that. Still, very solid.

![Algolia's DocSearch, built with Docusaurus](/img/docusaurus.webp)
[Check out Docusaurus here!](https://docusaurus.io/)

[Check out Hugo documentation templates here!](https://themes.gohugo.io/tags/docs/)

[Check out Jekyll documentation templates here!](https://jekyllthemes.io/jekyll-documentation-themes)

### Org-Mode (5/6)

I'm not an emacs user. That alone is disqualifying for org mode, I think. I have been exposed to some great demonstrations on org-mode [1](https://www.youtube.com/watch?v=oJTwQvgfgMM) [2](https://www.youtube.com/watch?v=Ea_-TaEGa7Y) [3](https://www.youtube.com/watch?v=SzA2YODtgK4), so I have no illusions about the fact that it is an incredible tool. I actually spent a couple of months in emacs too, and enjoyed it. Part of this period was spent moving over my small notes database (poor choice of words, it was basically a bunch of text files) to org mode. While I enjoyed it, there was too much of it that I felt I didn't understand and had to memorize, and a whole lot of untapped potential as is the case with emacs in general. I've never been exposed to Lisp, and don't have the time or, at the moment, the inclination to learn elisp to get things to work the way I want. For this reason I almost gave negative points to org mode in terms of "friction", but settled on a 0. In another life, or perhaps in a few years... who knows.

![A screenshot of org-wiki for org-mode in Emacs](/img/orgmode.webp)
[Check out Org-Mode here!](https://orgmode.org/)

### VimWiki (4/6)

VimWiki is a newer project that aims to bring some of the org-mode like functionality to Vim, and it's pretty good. I'm much more comfortable with vim, so I considered this seriously for a while. There are some issues, though.

1. The markup is kind of messed up. I'd have to learn it and use it for wiki entries while simultaneously using Markdown for writing posts on my site for example.
2. The file structure sucks. At least when I used it, no matter the level of nesting of a particular document, everything was dumped in the root folder. Doesn't bode well if I have to move away from VimWiki in the future.

It does have an (albeit rudimentary) export to HTML feature, which is not bad for shareability. But I was left underwhelmed by it.

![A screenshot of VimWiki](/img/vimwiki.webp)
[Check out VimWiki here!](https://vimwiki.github.io/)

### Zim (6/6) WINNER WINNER!

I did it, I found it! And it is beautiful.

My first exposure to Zim was a few years ago in [Average Linux User's video about note-taking programs on Linux](https://www.youtube.com/watch?v=HFeW4Cj5k1s). At the time it was a little at loggerheads with what I was looking for; I still maintain a different notes workflow because I want the private stuff to be encrypted and synced but not using a SaaS, and preferably not over the internet at all. However, it seems absolutely perfect for my wiki requirement.

![A Zim wiki demo image](/img/zim.webp)

Zim is a remarkable little graphical editor that allows for hierarchical text/hybrid document storage. It's available on every major desktop platform, looks fair enough and is easy to get into. Even beyond the surface simplicity that is so attractive, there's a good deal of features that "power users" might want to make use of from time to time. 

[Show some love for Zim here.](https://zim-wiki.org/)

What I love:

1. It's just simple.
2. The WYSIWYG editor is pretty great, but it also supports Markdown and standard keybindings for bold, underline etc.
3. The folder and file structure is sane.
4. It isn't usable directly on phone, but there's nothing stopping me from syncing the folder using Syncthing and then editing the files using an editor of my choice.
5. HTML export is there and it works great! It's pretty quick and simple, and while the default formatting is not responsive, it supports external templates. There are a [handful of templates available already](https://github.com/jaap-karssenberg/zim-wiki/wiki/Templates). I've decided to use the [Eight-Five-Zero](https://github.com/jrm4/Eight-Five-Zero) theme, but have removed useless (according to me) jQuery stuff, added a CSS rule to make code blocks play well with smaller screens, and fixed an issue with line height that I explained in some detail in [this post](/line-height-units-css).
    1. Yes, the templating language is really simple, and you can just wrap it with good old HTML! [Here's a link to my template](https://github.com/RonitRay/Zim-Wiki-Template-850)
    2. Zim goes so far as to generate an index for all my content, which is just wonderful.

What I don't love:

What's not to love? Zim is superb and everything I asked, and potentially could ever ask for. The only thing I can think might be a shortcoming compared to other items listed here is the fact that the web output cannot be searched, but the caveat is that it is served as static HTML that is simpler and much faster. I think I can take that deal. Besides, the actual tool has full-text search in it, it's just the web output which doesn't.

## The Result

I'm pleased to announce that I've started my wiki on Zim, and I'm really delighted so far. It works great for my use case. 

[My Personal Wiki!!](https://wiki.ronitray.xyz/)

![Screenshot of my wiki index.](/img/wikiscreen.webp)

It's pretty scanty now, but I'm hoping to make good use of it in the days and years to come. Overall, I'm really pleased with my workflow and the result.

## What I Learned

It's still early days, so I don't know if maintaining an extensive and well-documented wiki is something that I will take to. That said, I'm rather excited about it. I've been very pleasantly surprised with the variety of options available to me. If one thing has impressed me so far in my search, it is how many of these are free and open-source. It's a solid refutation of the narrative that you need proprietary or commercial tools to get a job done well, and gives me a lot of hope. I am taking away this hope along with the confidence that I have no dearth of options to switch to if the present arrangement doesn't work out, and the expectation to be able to build the discipline and make something that is not just useful to me, but might also serve as a long-lasting repository of conventional and unconventional knowledge, available to anyone willing to seek it out. Until next time!