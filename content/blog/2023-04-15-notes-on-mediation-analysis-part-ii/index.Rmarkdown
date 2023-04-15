---
title: Notes on Mediation Analysis, Part II
author: krhendrickson
date: '2023-04-15'
slug: ["mediation-analysis-notes-2"]
categories: ["epidemiology"]
tags: ["R","data analysis"]
status: ["just planted"]
series: ["mediation analysis"]
---

#### I'm spending the last semester of my masters working on an independent study project on causal mediation analysis. It seemed a perfect opportunity to try this [Learning in Public](https://www.swyx.io/learn-in-public) thing for the first time. I'm currenlty adding to this post on an almost daily basis. 

###### This is Part II in a two-part series. [Part I](../2023-03-27-notes-on-mediation-analsis-in-r/) covers general mediation concepts and terminology. This is where I dive into some of the more complex issues in mediation analysis.


##### Corrections or requests welcome in the comments section!
---

__Note: most of these notes are not specific to analysis in any language, but if/when I use code samples they will be in R.__

__Note to self:__ This post would benefit from a Table of Contents


## Exposure-mediator interaction


## Confounding of the mediator-exposure pathway


## Confounding by baseline mediator and baseline exposure values

As someone who is sensitive to sleep habits, I know that I'm much more likely to get a good night's sleep when I've had many good night's sleep in a row. On the flip side, a poor night's sleep often leads to more bad sleep, because I've disrupted my circadian rhythm. When I have a disrupted circadian rhythm, I'm a lot more likely to stay up later and drink more, because I'm not getting the "bedtime" cues from my brain at a reasonable hour. Here is a DAG visualizing what I mean: 

![](featured.png)


## Distinguishing moderation and mediation 

This is a bit of a jump, but I read [this paper](https://www.sesp.org/files/The%20Moderator-Baron.pdf) and so it's on my mind. 

Another way to conceptualize the role of sleep in this causal chain is as a *moderator*. (Note: add reference)

Moderators are variables that change the strength or direction of the relationship between your exposure and outcome variables, but, importantly, they aren't on the causal pathway. In my example, if sleep quality were a moderartor, it would mean that the quality of my sleep after a night of drinking changes the relationship between drinking and my hangover, but it isn't a stepping stone between the cause and effect. 

The resulting situation could be: 
- If I drink and then get a good night's sleep, there is a diminished or no relationship between alcohol consumption and my hangover. 
- If I drink and get poor night's sleep, there is a large relationship between alcohol consumption and my hangover. 

But in both scenarios, alcohol is not causing the poor sleep quality. Sleep quality is moderating the direct effect alcohol has on my hangover. 

That can seem like it's splitting hairs, but moderators and mediators would be treated very differently from an intervention perspective. If a variable is a mediator, it's helping you understand _why_ an intervention works. However, if a variable is a moderator, it means the intervention may _work differently_ for different groups of people, based on strata of the moderator. 

A more intuitive example comes from [this Vanderweele 2012 paper](https://academic.oup.com/aje/article/175/10/1013/89994) on gene variants and risk of smoking. 

When this study was conducted, there had been an observed relationship between:
- Gene variants on 15q25.1 and risk of lung cancer. 
- Gene variants on 15q25.1 and risk of nicotine dependence. 
- Gene variants on 15q25.1 and increased smoking behavior. 

The research question was: **is their a direct effect of the gene variant on risk of lung cancer, or is the relationship primarily mediated by the gene variant causing increased smoking behavior?** 

You could imagine that if the gene variant caused more smoking, then there would also be an association with with that gene variant and lung cancer. This is illustrated below. 

![](dag2.png)

However, it's also possible that the gene variant carries a higher risk of lung cancer _separate_ from how it influences smoking. So in their analysis, the researchers are evaluating the following DAG: 

![](dag3.png)

And, in fact, that is what the researcher's found. Using mediation analysis, they showed that the association between the gene variant and risk of lung cancer was operating primarily through pathways OTHER than smoking behavior. In terms of the DAG, pathway a is where most of the effect is traveling, not pathway b-c. 

But wait, I thought we were talking about moderation? 

Well here's the thing: of people who have the gene variant on 15q25.1, _only those who smoke are at increased risk for for lung cancer._

In other words, if you have the gene variant, but don't smoke, you have no increased risk for lung cancer due to your genetics. But if you have the variant and DO smoke, you're at a higher risk for lung cancer. Smoking is moderating the effect of your genetics.



#Adjusting for baseline measurements in mediation analysis

At this point I'm realizing this note would probably benefit from being broken up into a series. 

"Another assumption of any mediation analysis is no unmeasured confounding for each posited causal relation." (2023, Loh & Ren)

"Systematic differences in the distribution of con- founders between different mediator levels can manifest as noncausal (i.e., “spurious”) empirical associations between the mediators, or between the mediator and outcome." (2023, Loh & Ren)

# Coming Soon Topics
* Time-varying confounding 
