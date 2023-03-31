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


#### I'm spending the last semester of my masters working on an independent study project on causal mediation analysis. It seemed a perfect opportunity to try this Learning in Public thing (add citation here). 
---

Mediation analysis is usually conducted to evaluate specific causal mechanisms after a general cause and effect relationship has been established by theory and experiments. 

Let's say I've established a causal relationship in my life between going out and drinking and having a bad hangover the next day. I'm confident in the overall connection between these two variables (have tested it many times), but I can think of multiple _reasons_ that going out drinking might lead to a hangover. Below is one potential causal chain: 

![](dag1.png)

The value of a mediation analysis is being able to estimate _how much_ of an observed effect is going through a specific pathway. The full directed acyclic graph (DAG) would look like this: 

![](featured.png)
Our scientific question is: **how much of my hangover is due to the fact that alcohol consumption disrupts my sleep?**

In terms of the DAG - we're interested in pathway 'b' & 'c'. Pathway 'a' would be all the other causal mechanisms by which alcohol can cause a hangover. 

## Distinguishing moderation and mediation 

Another way to conceptualize the role of sleep in this causal chain is as a *moderator*. (Note: add reference)

Moderators are variables that change the strength or direction of the relationship between your exposure and outcome variables, but, importantly, they aren't on the causal pathway. In my example, if sleep quality were a moderartor, it would mean that the quality of my sleep after a night of drinking changes the relationship between drinking and my hangover, but it isn't a stepping stone between the cause and effect. 

The resulting situation would be: 
- If I drink and then get a good night's sleep, there is a diminished relationship between alcohol and a hangover. 
- If I drink and get poor night's sleep, there is an augmented relationship between alcohol and a hangover. 

But in both scenarios, alcohol is not causing the sleep quality. Sleep quality is moderating the direct effect alcohol has on my hangover. 

That can seem like it's splitting hairs, and a more intuitive exmaple comes from [this Vanderweele 2012 paper](https://academic.oup.com/aje/article/175/10/1013/89994) on gene variants and risk of smoking. 

When this study was conducted, there had been an observed relationship between:
- Gene variants on 15q25.1 and risk of lung cancer. 
- Gene variants on 15q25.1 and risk of nicotine dependence. 
- Gene variants on 15q25.1 and increased smoking behavior. 

The research question is: is their a direct effect of the gene variant on risk of lung cancer, or is the relationship primarily mediated by the gene variant causing increased smoking behavior? 

You could imagine that if the gene variant caused more smoking, then there would also be an association with lung cancer. However, it's also possible that the gene variant carries a higher risk of lung cancer _separate_ from how it influences smoking. 

And, in fact, that is what the researcher's found. Using mediation analysis, they showed that the association between the gene variant and risk of lung cancer was operating primarily through pathways OTHER than smoking behavior. 

But wait, I thought we were talking about moderation? 

If we instead change our perspective to smoking being the 'exposure' and 'lung cancer' being the outcome, this gene variant on 15q25.1 becomes a _moderator_. 



## A detour through terminology 



