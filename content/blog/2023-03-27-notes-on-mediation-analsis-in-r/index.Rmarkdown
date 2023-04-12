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


#### I'm spending the last semester of my masters working on an independent study project on causal mediation analysis. It seemed a perfect opportunity to try this [Learning in Public](https://www.swyx.io/learn-in-public) thing for the first time. I'm currenlty adding to this post on an almost daily basis. 

##### Corrections or requests welcome in the comments section!
---

Mediation analysis is often conducted to evaluate specific causal mechanisms after a general cause and effect relationship has been established by theory and experiments. 

As an example, let's say I've noticed a causal relationship in my life between going out drinking and having a bad hangover the next day. I'm confident in the overall connection between these two variables (having tested it many times), but I can think of multiple _reasons_ that going out drinking might lead to a hangover. Below is one potential causal chain: 

(Amusingly, I've recently [given up drinking](../2023-04-04-sober-ish/), so this post has become extremely theoretical.)

![](dag1.png)

The value of a mediation analysis is being able to estimate _how much_ of an observed effect is going through a specific pathway. In this case, how much is poor sleep mediating the effect of drinking on my hangover. If poor sleep is the only reason drinking alcohol affects how I feel the next day, then we would expect all of the observed effect to travel through that causal chain. However, there are probably multiple reasons I have a hangover after drinking, such as dehydration, or the direct effect of consuming alcohol making me feel ill. The directed acyclic graph (DAG) for this question would look like this: 

![](featured.png)
Our research question is: **how much of my hangover is due to the fact that alcohol consumption disrupts my sleep?**

In terms of the DAG - we're interested in disentangling pathway 'b' to 'c' from the 'total effect'. Pathway 'a' would be all the other causal mechanisms by which alcohol can cause a hangover (again, like dehydration).

## A detour through terminology 

One of the challenging parts about learning mediation analysis is the jargon associated with all the ways to break down the 'total effect' into alternate pathways. What is the difference between the 'natural direct effect' and the 'controlled direct effect'? What about the 'average casual mediated effect'? It's the kind of thing that you think you understand right up until you have to say it in your own words. Which explains how I'm feeling about it right now...

To start simply, the _direct effect_ is how much alcohol consumption is causing a hangover without going through an intermediary step.It's no secret that alcohol isn't good for you. According to the [Mayo Clinic website](https://www.mayoclinic.org/diseases-conditions/hangovers/symptoms-causes/syc-20373012#:~:text=Alcohol%20increases%20the%20production%20of,mood%20disturbances%20and%20even%20seizures.), alcohol irritates the lining of your stomach, which can cause pain, nausea, or vomiting. For the purposes of this example, we'll consider this a direct effect, or part of pathway 'a' in the DAG. 

_Indirect effects_, in contrast, are effects that go through the mediator of interest. They are called 'indirect' because without a change in the mediator, you don't see a subsequent change in the outcome. Intuitively, you would expect a total effect to be able to be broken down into a set of indirect effects and a leftover direct effect, assuming your understanding of the causal structure is correct.

This is where is starts to get complicated. The problem is that there can be an interactive relationship between the exposure and the mediator. (This is called "exposure-mediator interaction"). So when you want to quantify the relationship between these two variables, it's _dependent on_ what value you set the mediator. 

I haven't defined yet how I might measure sleep quality, but based on my rudimentary knowledge there are two main aspects to a good night's sleep: how much total time you spent sleeping and how much time you spent in deep sleep. Now, anyone who has had a little too much to drink one night can tell you that there is a world of difference for how you feel the next day if you get 9 hours of sleep rather than 4 hours of sleep. There is something about the combination of many drinks and little sleep that produce a particularly bad state of being the next morning (or afternoon..). In contrast, a night of drinking followed by many hours of sleep may leave you feeling only marginally fatigued the next day, especially if you went to bed hydrated (another exposure-mediator interaction!). I also haven't defined how I'm measuring the exposure. To keep things focused on the mediator, I'm going to say that having more that 2 drinks is "exposed" and having two or fewer drinks is "unexposed". 

This brings us to what are called "controlled" effects and "natural" effects. 

A Controlled Direct Effect is the effect that exposure to alcohol has on your hangover the next day *when we set the mediator to a specific value*. The Controlled Indirect Effect is the effect exposure to alcohol has on your hangover going through the mediated pathway and when the mediator is set to a specific value. 

Note to self: change mediator to hours of sleep so that measuring it makes more sense. 


## Confounding by baseline mediator and baseline exposure values

At first, I didn't think my drinking-sleep-hangover example would have any exposure-mediator interaction, but after dwelling on it I changed my mind. As someone who is sensitive to sleep habits, I know that I'm much more likely to get a good night's sleep when I've had many good night's sleep in a row. On the flip side, a poor night's sleep often leads to more bad sleep, because I've disrupted my circadian rhythm. When I have a disrupted circadian rhythm, I'm a lot more likely to stay up later and drink more, because I'm not getting the "bedtime" cues from my brain at a reasonable hour. Here is a DAG visualizing what I mean: 

![](dag5.png)


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







