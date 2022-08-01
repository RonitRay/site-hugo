+++
title= "On Reinventing the Wheel"
date= 2020-11-30
description="Or, why I did what I did with this site"
[extra]
listed=true
+++


[On an interesting thread in HN today](https://news.ycombinator.com/item?id=25227181), there was much discussion on the idea of reinventing the wheel in software projects and writing one's own static site generators. As someone fresh out of college where reinventing the wheel is not only encouraged but mandated in several areas to learn concepts, and also as someone who has "written" their own "static site generator", I feel like it's worth exploring this a little.

I've had blogs in some shape or form before. Blogger, WordPress, Ghost, and more recently Jekyll, Hugo and Zola. On the surface they all produce a good enough output, and have a ton of features. I could have stuck to any of them and called it a day, I'm sure the tens of thousands (?) of bloggers who do aren't particularly dissatisfied with their weapon of choice, mostly because they have bigger things to be concerned about, like the content. And yet, I'm happier with my solution today than I ever was with any of these, and here's why:

I've found that for simple blogs, especially hobby projects, you don't really need a WYSIWYG editor or an elaborate design or all kinds of funky tools, plugins and features that established CMS tools provide. Hell, I believe most of them don't even need to load several hundred kilobytes to a few megabytes of JavaScript to the user for eye-candy/obscure features either. If you can serve a static page with some minimal styling for readability, it's incredibly lightweight, likely doesn't need a CDN to be served quickly to viewers, and is just good design in general. This is my argument for using a static site generator. But why your own? 

I've found the Unix philosophy to be a nice guideline for a number of decisions in life. This is true for a blog workflow as well:

* _Let each component do one thing, and do it well_: Posts are text files, written entirely in a text editor. The static site generator exclusively takes the post content and turns it into HTML. 

* _Expect the output of every program to become the input to another_: Again, posts are text files. They can be fed into any template for any formatting for the final site. The outputted HTML can be viewed locally in a browser as a file, served on a local server for live refresh, and uploaded directly to GitHub/GitLab pages or your own site for hosting. Each component's involvement is only in one step of the process, and each component is designed to be replaceable should it stop working or should a better option present itself in the near future. For instance, I could use something other than Markdown for formatting text, something other than vim for editing, something other than Python (or indeed the entire generator) for building the site, and some other hosting provider for, well, for hosting it.

What these afford is simplicity- I get to know exactly what every step of my blog workflow does, and extensibility- if I want more features I can code them myself or seek assistance or contributions from the community. I prefer this minimal approach to the jack of all trades approach where the tool you use is already full of features you may never need, but they're there if you need them. This is why I wrote my own generator instead of using the several awesome ones available. There are merits to both approaches and I wouldn't be surprised that for commercial endeavours the established tools likely do the job better, are more reliable, and save time, effort, and money 90% of the time. And yet there are power users who swear by their own solution since they know it end-to-end and are not held back by arbitrary limitations of some other platform.

I end this ramble with some quotes from the HN thread, with credit.

[arpyzo's comment](https://news.ycombinator.com/item?id=25249963)


_I completely understand the desire to build something practical that's your own.
I just built a small web application framework that I can build some basic personal apps on top of. Just like the author's, it's "shitty". It lacks features, doesn't handle edge cases, isn't particularly secure or performant.
None of that matters. It's locked up behind HTTP authentication and it's for my use only. It has exactly the features I desire, and none that I don't. I understand it top to bottom. It was fun to write and extend. It serves my needs perfectly. I didn't have to fight with, or conform to someone else's notion of how software should be built._

[411111111111111's comment](https://news.ycombinator.com/item?id=25251110)

_"don't reinvent the wheel" is specifically for projects which other people will be forced to maintain.
You can reinvent the wheel as many times you want. If you however do that at work, your colleagues and your replacement after you left the job likely won't think too kindly of you._

[bogwog's comment](https://news.ycombinator.com/item?id=25250012)

_I spent about a day migrating my personal site from grav to hugo, and the main takeaway I got from that experience is that both of these "simple" static site generators are ridiculously over-engineered.
I could slap something together with a few lines of Make or Python that does exactly what I need, in an hour or two. I could even hook it up to AWS and have it update automatically.
Doing all of that is less time consuming and requires less effort than reading through the grav or hugo documentation, installing and setting everything up, and troubleshooting the inevitable problems.
The only issue I have is that doing front-end web development/design is not something I enjoy, so grav and hugo's existing library of themes is very convenient. Convenient enough to put up with the other annoyances._

[JasonFruit's comment](https://news.ycombinator.com/item?id=25250648)

_For me, the reason was simpler: it took less effort to write an SSG than it did to learn any existing one, and I got the fun of doing it._

