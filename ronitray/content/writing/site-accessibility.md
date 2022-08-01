+++
title= "What I'm Doing to Improve this Site's Accessibility"
date= 2021-03-07
description= "Accessibility needs to be a core tenet for the internet."
[extra]
listed=true
+++

One of the things I've had on my mind from the very beginning for this site is accessibility. I don't expect huge viewership now or ever, but making the content accessible to as many users as possible is something I greatly value and want to achieve. The internet wasn't built for a handful of people who have perfect eyesight and gigabit internet, and I'm not going to let my site be reduced to that. Accessibility should not be a luxury or a secondary concern. It needs to be a first-class citizen of every website if we want the web to truly be the open paradise for everyone it was envisioned to be. 

Here's what I'm doing to this end.

### Speed

This site is as light and fast as I've been able to make it. Static pages. <1.5 KB of CSS. Zero JavaScript. The entire site is (as of today) under 250KB, and no individual page is larger than 17kB. I'm serving it through [Netlify](https://netlify.com), and their CDNs are more than adequate for static sites. I'm working on minimizing the footprint further, but short of plaintext served via, say, [gopher](https://en.wikipedia.org/wiki/Gopher_(protocol)) or [gemini](https://gemini.circumlunar.space/), I think this is fairly light and loads quick enough even on 2G cell data.

### Contrast

I've implemented the prefers-color-scheme media query in my CSS to present a light or dark themed site based on the user's existing preference (typically read from their phone theme or desktop theme or browser flag). For light mode, it is black text on a white background. Not the most exciting thing in the world but it's as readable as can be. I've preferred dark mode in a lot of my personal applications but serving only white text on black can be pretty jarring for a lot of people, and grey text comes at the cost of reducing contrast and general readability for visually impaired users if it is the only option available. I haven't come across a convincing way to implement a dark mode toggle without JS, which is why I haven't given the explicit option. 

### General Readability

On desktop, the content is centered and will cover 50% of the screen width,which translates to roughly 70-85 characters per line depending on the size of your monitor. This goes up to 90% on portrait displays (like phones) to minimize wastage of limited vertical real estate. There is just enough of a margin to ensure content doesn't overflow for phones with silly curved displays and leave room for swipe based gestures. I'm using 1.125em font size (translates to 18pt on *most* browsers by default); I think it is fairly large for those who need it without being too huge for those who don't. The site is fully zoom-compatible, so text sizes can be changed without hassle using your browser's zoom functionality. I've opted for a line height (spacing) of 1.5 as well. I don't (and won't) use all caps or justified alignment.

### Font

I'm sticking to sans serif fonts with high availability and generally clean typefaces. I'm also looking at slab fonts because they're the most attractive to me, but I'm not sure how legible or accessible they are in general. I wasn't able to find any definitive source on the most accessible fonts. The ones that market themselves as being specifically designed for visually impaired users tend to have the following issues.

1. Convoluted commercial licenses, which I can't afford to use and am opposed to in general.
2. Lack of availability, as in they are unlikely to be installed on the vast majority of systems. Would need to be embedded with the site, increasing the size of each page by at least 100kb. 
3. From what I understand, these also tend to be not-as-good for general use (OpenDyslexic for example seems to be difficult to read for me) or for people suffering from disabilities other than the one they target, and the data proving their efficacy is a little scarce, although that can well be attributed to the general lack of data for people with disabilities.

### Links

If you visited my site earlier this month you might recall that the text was all-black. The links were the same color as the text, with only the underline to distinguish them. I still really like the look, especially when it is done well on blogs like those maintained by [Tom MacWright](https://macwright.com) and [Jan-Lukas Else](https://jlelse.dev), for instance. But with my shoddy CSSwork it just didn't look right. 

1. Data strongly also suggests that users associate blue with links because it is the default choice in HTML, and has good contrast with black or white text. It also provides another critical factor to distinguish links from the rest of the text content. I didn't like the default blue choice for HTML, so I've gone for a more mellow #0d47a1 (light mode) and #4bbaff (dark mode) instead.
1. Now, one thing I absolutely hate is underlines on links, because for letters which have descenders/tails that go below the line, the underline goes right through them and the result is really ugly. Underlines are important though, especially if your visitor isn't able to clearly distinguish your link color from the other elements. To avoid this, I've removed underlines and gone for a 1px bottom border instead, which is drawn below the descender. I think that is an acceptable compromise.

### Screen Reader Compliance

I've kept all formatting as basic and standard as possible, and there are no convoluted maneuvers that will interfere with screen readers. I've tested this with Microsoft Narrator and it works fine. 

It's worth remembering that aside from images having alt tags, it is also important for your tables to have alt tags for each column as this allows the screen reader to describe the column before talking about the data in it. I've only got tables on one page (Library) right now, but that follows this already. 

I'm using HTML5 semantic elements like header, nav, section, footer etc as well. I've also kept a lang=en on the html declaration which I've read helps screen readers parse the content.

### Alt text on Images

This is important not only for screen readers but also for people in poorly connected areas who are unable to load anything beyond the text content. It also helps years down the line if you are linking to external images that may not be there. The link may break but your alt text is there to stay.

### CSS and Mouse Independence and Terminal Based Browsers
The site looks fine without loading the CSS file. I don't rely on any fancy CSS shenanigans, mostly because I don't know or need them. I'm a big fan of terminal-based browsers, and have checked the site with links, lynx, and w3m. Looks pretty good, if I may say so. I don't hijack clicks or scrolling so users are free to navigate using their keyboard.

### Proper HTML Structure
I use very basic HTML structure in my Jinja templates but adhere to all the hits: semantic elements, ordered heading tags, alt text, meta descriptions and so on.

### Forms

I only have one form on this site for the contact page, and it is very basic. It is labelled and visible.

### Concluding

If you are looking to implement accessibility features on their site can refer to [DotCMS's excellent accessibility checklist](https://dotcms.com/blog/post/website-accessibility-checklist-10-steps-towards-website-compliance) or [another great guide from websitesetup.org](https://websitesetup.org/web-accessibility-checklist/).  If you have any suggestions for how I can improve accessibility, please [contact me.](/contact)
