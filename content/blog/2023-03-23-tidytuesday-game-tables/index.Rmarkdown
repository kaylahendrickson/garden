---
title: '#TidyTuesday: Tables'
author: krhendrickson
date: '2022-04-04'
slug: [tidytues-tables]
categories: []
tags: ["data viz"]
series: ["tidytuesday"]
status: ["growing"]
layout: single-sidebar
---

#### This started was one of my first Tidy Tuesday's and my introduction to the gt and gtExtras packages.

---

### Part I: Tables in R. 

![](10HighestBoardGames_featured.png)

Note to self: figure out how to make this table smaller. 

As this was an early #TidyTuesday, I went for a simple analysis and found the 10 highest and 10 lowest ranked board games.  I then added the year the board games came out and the average user ratings. Everything went smoothly until I tried to make the bar plots in the fifth column. Twenty-seven browser tabs later I found the gtExtras package, which has the function gt_plt_bar_pct(). This simplified the plotting massively, and the only other thing I needed to do was make a scaled user rating to use in that column.

After the content of the table was done I had a great time playing with the styling. I was at first surprised how many lines of code this took, because you have to target each piece of the table separately to style it (unless I'm mising a more efficient way). But upon refection, it's clear that's the best way to make sure the tables are fully customizable. 

Showing the 10 lowest ranked games revealed that the board game Sheep in Disguise has a low rating but a high user rating - which begs the question, how are these board games being ranked? Is it an error or is this a Rotten Tomatoes deal where the critics and the audience don't always match up? 

![](10LowestBoardGames.png)

### Part II: Recreating the game tables in Python. 

I've wanted to learn Python for awhile (and have picked up a minimal amount in the past), so one way I thought of to help myself practice was to recreate my R TidyTuesday's in Pyhton. 

