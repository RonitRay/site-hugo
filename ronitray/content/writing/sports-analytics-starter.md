+++
title= "Getting Your Feet (and mine) Wet in the World of Sports Analytics"
date= 2021-11-05
description= "A list of resources for data analytics and visualization, specifically in the sports world thanks to Tom Worville and a number of awesome people on Twitter."
[extra]
listed=true
+++
##### Personal note: I love football. I didn't get into the game very early in my life, but since age 12 or so, I have been absolutely obsessed. Earlier this year, I got a subscription to <a href="https://theathletic.com/">The Athletic</a> and was exposed to some of the best football coverage I've ever read. While I cannot afford the subscription anymore, I still have access to a lot of their content through podcasts and partner YouTube channels like the excellent <a href="https://www.youtube.com/c/TifoFootball">Tifo Football</a> and <a href="https://www.youtube.com/c/TifoIRL">Tifo IRL</a>. Tom Worville, their data analytics writer, has consistently put out superb work that is informative and interesting. More recently, he has featured in a series of videos by Tifo, comparing players in Europe's top leagues across several dimensions using scattergrams.

##### Very recently, Tom has signed as a Data Scientist for RB Leipzig, one of the hottest projects in Europe (Congratulations, Tom!). I think it's fair to say his work has impressed me and maybe even inspired me to dip my toes in the field. Thankfully, Worville himself and a number of awesome people on Twitter have compiled more resources than I can get through in quite some time. This post is an attempt to document the same. 99% of the effort is from the people who actually created the materials and compiled them. All I have done is removed Twitter's stupid tracking links and cleaned up the formatting a little so it's actually readable. I will hopefully be visiting some of these materials in the future and writing about what I learn from them.

<hr>

## [Thread](https://twitter.com/Worville/status/1275732993819250688) by [Tom Worville](https://twitter.com/Worville/status/1275732993819250688)

To start, here’s a great thread of intro blogs for working with and plotting [@StatsBomb](https://twitter.com/StatsBomb) data in R by [@biscuitchaser](https://twitter.com/biscuitchaser)

1. [Plotting passes using and getting started in R](https://biscuitchaserfc.blogspot.com/2020/03/getting-started-in-r-with-statsbomb-data.html)
2. [Adding further information to pass plots](https://biscuitchaserfc.blogspot.com/2020/04/using-r-and-statsbomb-data-part-2.html)
3. [Comparing WSL creators](https://biscuitchaserfc.blogspot.com/2020/04/using-statsbomb-data-part-3.html)
4. [Shots maps for WSL](https://biscuitchaserfc.blogspot.com/2020/05/shot-maps-in-r-using-statsbomb-data.html)
5. [Using Wyscout data in R](https://biscuitchaserfc.blogspot.com/2020/06/using-wyscout-in-r.html)

Piece by [@GregorydSam](https://twitter.com/GregorydSam): [Getting into Sports Analytics 2.0](https://medium.com/@GregorydSam/getting-into-sports-analytics-2-0-129dfb87f5be)

Some good advice from [@smarterscout](https://twitter.com/smarterscout) in [this podcast ep about getting into the industry, along with the much needed about the relatively few jobs on offer](https://podcasts.google.com/feed/aHR0cHM6Ly9mZWVkcy5idXp6c3Byb3V0LmNvbS8xMTAyMDYxLnJzcw/episode/QnV6enNwcm91dC00NDI5NTMy?hl=en-GB&ved=2ahUKEwiI2OzLt7jqAhXVoFwKHcQ2ASYQjrkEegQIBxAE&ep=6)

Another plug for [@rweekly_org](https://twitter.com/rweekly_org), this week is by the great [@R_by_Ryo](https://twitter.com/R_by_Ryo) Including - Creating an xG model with R [@thecomeonman](https://twitter.com/thecomeonman)'s arsenal of code examples

[This](https://education.rstudio.com/blog/2020/08/spreadsheets-using-r/) is a gentle how-to guide for those who are approaching R from being excel users first and foremost. 

[This](https://towardsdatascience.com/ten-up-to-date-ways-to-do-common-data-tasks-in-r-4f15e56c92d) is a great `#Rstats` guide to making the most of recent changes to the {tidyverse} Big one for me is relocating columns in a dataframe, which dplyr::relocate() can help with now. Thanks [@dr_keithmcnulty](https://twitter.com/dr_keithmcnulty)!

The great [@thomas_mock](https://twitter.com/thomas_mock) has been on a TEAR recently with some nice blogs on building better tables using {gt}, but more relevant is [this well thought out piece on heatmap design.](https://themockup.blog/posts/2020-08-28-heatmaps-in-ggplot2/)

Shout out to [@icymi_r](https://twitter.com/icymi_r) which is a great `#rstats` content aggregator.

Not posted here for a while, but [@JanVanHaaren](https://twitter.com/JanVanHaaren)'s [excellent summary of football analytics in 2020](https://janvanhaaren.be/2020/12/30/soccer-analytics-review-2020.html) is well worth a read: 

Feel it’s quite common that people have “coding scrapbooks” of functions/tips they return to over and over again. [Sam’s here is neat](https://gustasam5.medium.com/some-useful-python-stuff-92f0b013c9a4)

Had a couple of DMs asking about coding tutorials. Have to say that [@mckayjohns](https://twitter.com/mckayjohns) is the GOAT, and a great place to get started

Also[@Soccermatics](https://twitter.com/Soccermatics)' [Friends of Tracking channel](https://www.youtube.com/channel/UCUBFJYcag8j2rm_9HkrrA7w) has tons too.

Just stumbled across [this Github repo](https://github.com/eddwebster/football_analytics) of links and various resources by [@eddwebster](https://twitter.com/eddwebster), unbelievable effort to keep on top of all of this.

Great work by [@PfaffCatherine](https://twitter.com/PfaffCatherine) pulling a list together of [female identifying sports analysts](https://mast.queensu.ca/~cpfaff/FemaleSportsAnalysts.pdf), hopefully serves as inspiration to others + good to spotlight those succeeding in such a male-dominated industry. 

## [Thread](https://twitter.com/tylermorganwall/status/1278455988920758277?lang=en) by [@tylermorganwall](https://twitter.com/tylermorganwall)

Reminder: there are hundreds of great, FREE learning resources for `#rstats` out there. There's no need to sign up to take courses with a disgusting, ethically bankrupt company with sniveling, feckless leadership.

I'm completely self-taught in R. Here's a list of the FREE, OPEN materials I've used on my journey: For data wrangling and visualization, nothing beats [Hadley's "R for Data Science"](https://r4ds.had.co.nz)

Want to learn about data visualization? Check out [@ClausWilke](https://twitter.com/ClausWilke)'s ["Fundamentals of Data Visualization"](https://serialmentor.com/dataviz/). While not a book about R specifically, it's a great resource for learning what makes a good, interpretable viz. Plus, the book's code is available!

If you want to learn about ggplot2 plotting in particular, it's best to get it straight from the source: read Hadley's ggplot2: [Elegant Graphics for Data Analysis](https://ggplot2-book.org/). I can't imagine why you'd want to learn it from anyone else.

For diving into the internals of R, [Hadley's "Advanced R"](http://adv-r.had.co.nz) is a wonderful resource. I've gone back to it several times over the years and found new nuggets of info. Confused about environments or closures, or how to debug C code or NSE? Check it out. The second edition of "Advanced R" is available at a [slightly different URL](https://adv-r.hadley.nz)

Want to learn about maps, GIS, and spatial analysis and visualization? Check out [@robinlovelace](https://twitter.com/robinlovelace) & [@jakub_nowosad](https://twitter.com/jakub_nowosad)'s ["Geocomputation with R"](https://geocompr.robinlovelace.net/), a great free resource on geographic data analysis, visualization and modeling.

Want to learn how to spin up your own data analysis cluster and do work on "big data" in R? Check out [@javierluraschi](https://twitter.com/javierluraschi)'s ["Mastering Spark with R."](https://therinspark.com/) He even shows you how to fire up a rayrender render farm for complex 3D visualizations! 

If you like the "in person" learning experience video provides and you're interested in learning more about making maps in R with rayshader, check out my open and free masterclass I taught with the [@PennMUSA](https://twitter.com/PennMUSA) program: 

* [Course](https://penniur.upenn.edu/events/musamasterclass-featuring-tyler-morgan-wall-3d-mapping-dataviz-in-r)
* [Code](https://github.com/tylermorganwall/MusaMasterclass)

Finally, the R community is the best—if you ever run into seemingly intractable problems on your journey, tweet your issue with the `#rstats` hashtag & almost certainly you'll get help. And if that fails, try the [community forums hosted by RStudio](https://community.rstudio.com/)

I'd add [Kieran Healy's Data Visualization](https://socviz.co/), available in a free online format as well as a textbook.

There is an [awesome Slack group](https://rfordatasci.com) to help work through the book (and help on all other R questions as well). People are really helpful and friendly!

Learn about solve text mining problems with ["Text Mining with R"](https://www.tidytextmining.com/)! Great introduction to the tidytext package and working with text data by [@juliasilge](https://twitter.com/juliasilge) & [@drob](https://twitter.com/drob)

Another resource - I like to tell complete beginners to check out [Swirl](https://swirlstats.com).

## [Tweet](https://twitter.com/lucystats/status/1278724184517083136) by [Lucy D’Agostino McGowan](https://twitter.com/LucyStats)

Have you checked out[@dcossyle](https://twitter.com/dcossyle)'s teacup giraffes and stats? I think it is definitely high schooler friendly! https://tinystats.github.io/teacups-giraffes-and-statistics/

## [Tweet](https://twitter.com/aggieerin/status/1278525024228573185) by [Dr. Erin Buchanan](https://twitter.com/aggieerin)

* Hi fam! If you want learn some `#sem` `#rstats` `#lavaan` for free(!) I have [my entire course on YouTube](https://www.youtube.com/playlist?app=desktop&list=PLw93TUuxrFAZkJVc5dhgTZpOT7qmTjlT7). Even better, the great [@Savvylewis15](https://twitter.com/Savvylewis15) has helped me reorganize my YouTube excel sheet so the website will include a watching order list again soon.

## [Thread](https://twitter.com/AmeliaMN/status/1152269862850506752) by [Amelia McNamara](https://twitter.com/AmeliaMN)

I’d love to gather open source interactive R lessons. I’ll start a thread here, but please chime in! `rstats` `#tidyverse` 

There are [introductory primers]((https://rstudio.cloud/learn/primers)) on [@rstudio](https://twitter.com/rstudio).

[Noam Ross's GAM Course](https://noamross.github.io/gams-in-r-course/)

[@tladeras](https://twitter.com/tladeras) and [@datapointier](https://twitter.com/datapointier)’s [intro to the tidyverse R bootcamp](https://r-bootcamp.netlify.com)

Ted’s R package to [convert DC courses](https://github.com/laderast/decampr)

[Grant McDermott](https://twitter.com/grant_mcdermott) courses:

* [Data Science for Economists](https://github.com/uo-ec607/lectures#data-science-for-economists)
* [Big Data in Economics](https://github.com/uo-ec510-2020-spring/lectures#big-data-in-economics-ec-410510)

## Tweet by [Rebecca Barter](https://twitter.com/rlbarter)

[Tidymodels: tidy machine learning in R](https://www.rebeccabarter.com/blog/2020-03-25_machine_learning/). A concise introduction to machine learning in R using the new(ish) tidymodels pipeline (essentially caret's successor). Thanks to[@topepos](https://twitter.com/topepos) and team!