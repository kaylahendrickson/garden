---
title: '#tidytuesday:game tables'
author: krhendrickson
date: '2022-04-04'
slug: []
categories: []
tags: []
layout: single-sidebar
---

This was one of my first times doing a #TidyTuesday and my introduction to the gt and gtExtras packages.

![](10HighestBoardGames_featured.png)

If you’re paying attention to dates, you’ll notice I’m writing this post well after having made the tables, so I don’t remember all the bumps and bruises along the way to this end result. Let’s go for my best reconstruction.

As this was an early #TidyTuesday, I went for a fairly simple analysis, and found the 10 highest and 10 lowest ranked board games.  I added on the year the board games came out and the average user ratings. As I recall, this mostly went smoothly, and it wasn’t until I tried the bar plots in the fifth column that I had to open 27 browser tabs. Extensive Googling led me to the gtExtras package, which has the function gt_plt_bar_pct(). This simplified the plotting massively, and the only other thing I needed to do was make scaled average rating to use in that column.

The other major learning point for me was the table styling. I found it surprising that you have to target each piece of the table separately (right?) to style it, but after realizing that the colors and font came together.

![](10LowestBoardGames.png)
