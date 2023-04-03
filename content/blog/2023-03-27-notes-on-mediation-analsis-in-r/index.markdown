---
title: Notes on Mediation Analsis in R
author: krhendrickson
date: '2023-03-27'
slug: ["mediation-analysis-notes"]
categories: ["epidemiology"]
tags: ["R","data analysis"]
status: ["just planted"]
series: ["mediation analysis"]
---


#### I'm spending the last semester of my masters working on an independent study project on causal mediation analysis. It seemed a perfect opportunity to try this [Learning in Public](https://www.swyx.io/learn-in-public) thing for the first time. 
---

Mediation analysis is often conducted to evaluate specific causal mechanisms after a general cause and effect relationship has been established by theory and experiments. 

As an exmaple, let's say I've noticed a causal relationship in my life between going out drinking and having a bad hangover the next day. I'm confident in the overall connection between these two variables (having tested it many times), but I can think of multiple _reasons_ that going out drinking might lead to a hangover. Below is one potential causal chain: 

![](dag1.png)

The value of a mediation analysis is being able to estimate _how much_ of an observed effect is going through a specific pathway. In this case, how much is poor sleep mediating the effect of drinking on my hangover. If poor sleep is the only reason drinking affects how I feel the next day, then we would expect all of the observed effect to travel through that causal chain. However, there are probably multiple reasons I have a hangover after drinking, such as dehydration, or the actual processing of the alochol making me feel ill. The directed acyclic graph (DAG) for this question would look like this: 

![](featured.png)
Our scientific question is: **how much of my hangover is due to the fact that alcohol consumption disrupts my sleep?**

In terms of the DAG - we're interested in disentagling pathway 'b' & 'c' from the 'total effect'. Pathway 'a' would be all the other causal mechanisms by which alcohol can cause a hangover. 

## A detour through terminology 

One of the challenging parts about learning mediation analysis is the jargon associated with all the analytical ways to break down the 'total effect' into different pathways. What is the difference between the Natural Direct Effect and the Controlled Direct Effect? What about the Average Casual Mediated Effect? It's the kind of thing you think you understand right up until you have to explain it. Which explains how I'm feeling about it right now...




## Distinguishing moderation and mediation 

This is a bit of a jump, but I read [this paper](https://www.sesp.org/files/The%20Moderator-Baron.pdf) and so it's on my mind. 

Another way to conceptualize the role of sleep in this causal chain is as a *moderator*. (Note: add reference)

Moderators are variables that change the strength or direction of the relationship between your exposure and outcome variables, but, importantly, they aren't on the causal pathway. In my example, if sleep quality were a moderartor, it would mean that the quality of my sleep after a night of drinking changes the relationship between drinking and my hangover, but it isn't a stepping stone between the cause and effect. 

The resulting situation could be: 
- If I drink and then get a good night's sleep, there is a diminished or no relationship between alcohol consumption and my hangover. 
- If I drink and get poor night's sleep, there is a large relationship between alcohol consumption and my hangover. 

But in both scenarios, alcohol is not causing the poor sleep quality. Sleep quality is moderating the direct effect alcohol has on my hangover. 

That can seem like it's splitting hairs, but moderators and mediators would be treated very differently from an intervention perspective. If a variable is a mediator, it's helping you understand _why_ an intervention works. However, if a variable is a moderator, it means the intervention may _work differently_ for different groups of people, based on strata of the moderator. 

A more intuitive exmaple comes from [this Vanderweele 2012 paper](https://academic.oup.com/aje/article/175/10/1013/89994) on gene variants and risk of smoking. 

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







