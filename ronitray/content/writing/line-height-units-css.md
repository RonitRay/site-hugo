+++
title= "Don't Use Units for Line Height (Txti Please!)"
date= 2021-03-25
description= "Units are important and necessary in most CSS use cases, but not line height. Here's why."
[extra]
listed=true
+++


[Line height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) is an important CSS property. I feel like either I'm getting old or the system/browser default line height is just not good enough for most modern websites. When you're reading large walls of text, single-line spacing can get pretty fatiguing quite fast. MDN specifically has an "Accessibility Concerns" section on its line-height documentation, stating:

>*Use a minimum value of 1.5 for line-height for main paragraph content. This will help people experiencing low vision conditions, as well as people with cognitive concerns such as Dyslexia. **If the page is zoomed to increase the text size, using a unitless value ensures that the line height will scale proportionately.***

The second sentence here is one that s really important. [On early versions of this site, even early this month](https://github.com/RonitRay/personalwebsite/commit/05f012f89fbb1b54160629b69e7e6c33d7b349d2#diff-36e64f19f57a05c8cd5b6bf7eff72703b4bbab19def7832eb4e686e7fa482eef), I had kept the line height as "1.5em". Now, relative units (em/rem) are well and good and have their place in web design. In fact, I continue to use them for setting font-size on this site, for example. And logically, there's no reason for 1.5em to not work in line spacing. It means you want the site to render lines spaced out at 1.5x whatever the system's default line spacing setting. Or at least, it should mean that, but CSS is odd. For whatever reason, the line height property doesn't seem to inherit parent values very well, which means scaling them with multipliers and relative units doesn't get you the expected results. See the example below, also from MDN:

![Comparison of HTML pages using relative units and no units for line height. When no units are used, text that overflows or are longer than a single line on screen are rendered as expected with the defined line height. But when relative units are used, the line height value does not reflect, resulting in ugly vertically-conjoined text'](/img/cssunitcomparison.png)

I urge anyone writing their own CSS to remember not to use units when setting line height. In this context, it's worth mentioning txti. [Txti](https://txti.es) is a great little service for hosting and sharing text-based pages quickly over the internet. It was created by [Barry T. Smith](http://barrytsmith.com/), and is a culmination of the series of motherfucking websites [[1]](https://motherfuckingwebsite.com/) [[2]](http://bettermotherfuckingwebsite.com/) [[3]](https://thebestmotherfucking.website/) [[4]](https://bestmotherfucking.website/) [[5]](https://thebestmotherfuckingwebsite.co/), which is both informative and hilarious.

Txti is great for anonymous blogs or public pastes. I love everything about it, except... it falls prey to the same line spacing issue that I did. It uses 1.5em line-spacing. Seriously, [have a look at any of the txti.es posts from HN](https://hn.algolia.com/?dateRange=all&page=0&prefix=true&query=txti.es&sort=byPopularity&type=story). From what I gather, Txti doesn't seem to be an open-source project so I can't submit a PR. I've sent an email to Smith, but that's besides the point. What I'm trying to say is, use unitless values for line height in CSS. Cheers.
