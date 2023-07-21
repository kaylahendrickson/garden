---
title: Causal Inference - a language & symbols cheat sheet
author: krhendrickson
date: '2023-07-21'
slug: []
categories:
  - epidemiology
  - causal inference
tags: []
---

These notes are for those non-stats folks (me) who would like an occasional refresher on the language and symbols of causal inference concepts and statistics. 

## Language

**Marginal probability** - the probability of an event occurring, independent of any other events. 
- Causes are understood within the context of marginal distributions. A cause Y would always have some effect X, independent of other conditions. 

We understand this intuitively. If you always get a stomach ache after going to a gas station, but you always purchase and consume an entire bag of sour straws when you get gas, you aren't likely to say 'going to the gas stations causes my stomach aches'. The effect is (presumably) _conditional_ on the sour straw consumption.

**Conditional probability** - the probability of an event occurring, given another event or condition. 
- Associations are understood within the context of conditional distributions. Y is associated with X in this sample population.

Again, we intuitively understand that not everything that is associated in causal. 


**Exchangeability** - if the baseline risk of the outcome in group 1 is the same as the baseline risk of the outcome in group 2, the groups are said to be exchangeable. 
- Randomization is expected to produce exchangeability.
- Randomization makes the counterfactual outcome jointly independent of the observed treatment. 
   + This is different from saying _the observed outcome_ is independent of     the observed treatment. If the treatment has a causal effect on the         outcome, they are dependent. 
- Because the conditional risks of the outcome are expected to be equal in all random subsets defined by treatment status, they *must* be equal to the marginal risk under treatment status _a_ in the whole population. (This is the mathematical basis of an 'experimental' and 'control' group standing in for the entire target population under the exprimental or control treatment status.)

**Crossover experiment** - sequentially observing an individual's outcome under two treatment values (could be control and experimental, or two different experimental treatment values).
- Assumptions: 
  + No carryover effect 
  + The causal effect of the treatment does not depend on time
  + The counterfactual outcome under no treatment does not depend on time

**Marginally randomized experiments** - using a single unconditional randomization. 

**Conditionally randomized experiments** - using two or more assignment probabilities that depend on the value of another variable.
- Conditional randomization does not usually result in exchangeability, but there may be other reasons to employ this design. 
- But there will be exchangeability within the strata of the variable on which you conditioned. This is **conditional exchangeability**. 
- You can then compute the causal effects within strata of the conditioning variable. 
  + If the causal effects across strata are the same, we have **treatment            effect homogeneity**. 
  + If the causal effects across the strata are different, we have                   **treatment effect heterogeneity**. This is also called **effect                 modification**. 
  
**Inverse probability weighting**

## Symbols

**Pr[Y]** - The probability of event Y. 

## References 




