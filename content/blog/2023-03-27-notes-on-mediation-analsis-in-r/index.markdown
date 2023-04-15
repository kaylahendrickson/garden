---
title: Notes on Mediation Analysis, Part I
author: krhendrickson
date: '2023-03-27'
slug: ["mediation-analysis-notes"]
categories: ["epidemiology"]
tags: ["R","data analysis"]
status: ["just planted"]
series: ["mediation analysis"]
---

#### I'm spending the last semester of my masters working on an independent study project on causal mediation analysis. It seemed a perfect opportunity to try this [Learning in Public](https://www.swyx.io/learn-in-public) thing for the first time. I'm currenlty adding to this post on an almost daily basis. 

##### Part I covers general mediation concepts and terminology. [Part II](../2023-04-15-notes-on-mediation-analysis-part-ii/) covers more complex issues in mediation analysis.

###### Corrections or requests welcome in the comments section!
---

__Note: most of these notes are not specific to analysis in any language, but if I use code samples they will be in R.__

Mediation analysis is often conducted to evaluate specific causal mechanisms after a general cause and effect relationship has been established by theory and experiments. 

As an example, let's say I've noticed a causal relationship in my life between drinking beer and having a bad hangover the next day. I'm confident in the overall connection between these two variables (having tested it many times), but I can think of multiple _reasons_ that drinking might lead to a hangover. Below is one potential causal chain: 

(Amusingly, I've recently [given up drinking](../2023-04-04-sober-ish/), so this post has become extremely theoretical.)

![](dag1.png)

The value of a mediation analysis is being able to estimate _how much_ of an observed effect is going through a specific pathway. In this case, how much is less sleep mediating the effect of drinking on my hangover. If less sleep is the only reason drinking alcohol affects how I feel the next day, then we would expect all of the observed effect to travel through that causal chain. However, there are probably multiple reasons I have a hangover after drinking, such as dehydration, or the direct effect of consuming alcohol making me feel ill. The directed acyclic graph (DAG) for this question would look like this: 

![](featured.png)
&nbsp;
&nbsp;

Our research question is: *how much of my hangover is due to the fact that alcohol consumption disrupts my sleep?*

In terms of the DAG - we're interested in disentangling pathway 'b' to 'c' from the 'total effect'. Pathway 'a' would be all the other causal mechanisms by which beer consumption can cause a hangover (again, like dehydration).

## A detour through terminology 

One of the challenging parts about learning mediation analysis is the jargon associated with all the ways to break down the 'total effect' into alternate pathways. What is the difference between the 'natural direct effect' and the 'controlled direct effect'? What about the 'average casual mediated effect'? It's the kind of thing that you think you understand right up until you have to say it in your own words. Which explains how I'm feeling about it right now...

To start simply, the __direct effect__ is how much beer consumption is causing a hangover without going through an intermediary step.It's no secret that alcohol isn't good for you. According to the [Mayo Clinic website](https://www.mayoclinic.org/diseases-conditions/hangovers/symptoms-causes/syc-20373012#:~:text=Alcohol%20increases%20the%20production%20of,mood%20disturbances%20and%20even%20seizures.), alcohol irritates the lining of your stomach, which can cause pain, nausea, or vomiting. For the purposes of this example, we'll consider this a direct effect, or part of pathway 'a' in the DAG. 

__Indirect effects__, in contrast, are effects that go through the mediator of interest. They are called 'indirect' because without a change in the mediator, you don't see a subsequent change in the outcome. Intuitively, you would expect a total effect to be able to be broken down into a set of indirect effects and a leftover direct effect, assuming your understanding of the causal structure is correct.

This is where it starts to get complicated. The problem is that when you want to quantify the relationship between the exposure and outcome variables, it's _dependent on_ the distribution of the mediator variable. 

So what should that be? Here are two common approaches: 

#### Controlled Effects 

A "controlled (in)direct effect" is the effect the exposure has on the outcome when the mediator is held to a specific value. This may be most useful and intuitive when we are trying to quantify how well an intervention works to create a desired outcome. For me, I want to know if I sleep at least 9 hours, does it make my hangover decrease or go away? I might (in-advisably) test that by drinking different amounts of beer each night, but getting 9 hours of sleep every night. I have "controlled" my mediator, and am seeing how the exposure affects the outcome under those conditions. If my original hypothesis is correct, that lack of sleep is an important mediator in the causal system, then we should observe a significant decrease in my hangover symptoms from baseline. As a result, controlled (in)direct effects are often useful in designing interventions or making policy decisions. 

![](dag2.png)

#### Natural Effects 

However, what if we want to know a more general, real-world impact of drinking beer on my wellbeing? If I don't normally get 9 hours of sleep every night after I drink beer, then the controlled effects don't inform what I will observe in my day-to-day life once this hypothetical experiment is over. This is where natural effects come in. Natural (in)direct effects are the effects observed when the mediator is set to an average level that is observed in a population of interest. My population is just me, so the average amount of sleep I get each night is what might be considered my "natural" level of the mediator.

![](dag3.png)

In the case of an experiment, there is the average value of the mediator observed in the control group and the average value observed in the intervention group, so there are two different "natural" effects: 

* __Pure natural (in)direct effects__ are natural effects measured when the mediator is set to the average value of the control group.
* __Total natural (in)direct effects__ are natural effects measured when the mediator is set to the average value in the intervention group. 

&nbsp;
&nbsp;

# Coming soon: 

## Method for simple mediation analysis 

## Assumptions required to conduct a typical mediation analysis

#### But what about when those assumptions do not hold? See [Part II](../2023-04-15-notes-on-mediation-analysis-part-ii/) in this series for more about the complexities of causal mediation analysis.





