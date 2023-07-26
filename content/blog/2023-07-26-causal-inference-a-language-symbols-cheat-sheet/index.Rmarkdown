---
title: Causal Inference - a language & symbols cheat sheet
author: krhendrickson
date: '2023-07-21'
slug: ["causal-inference-cheat-sheet"]
categories:
  - epidemiology
  - causal inference
  - notes
tags: ["causal inference"]
series: ["causal inference"]
---

>**The "notes" category indicates that much of this post is my summary and interpretation from sources I'm using to learn about a topic of interest. As such, most of the following are not my original thoughts.**

Learning hard stuff is hard, and it continues to be hard long after you would like it to have become easier.

It's that 'I know this but I also don't KNOW this" feeling. 

This is where I'm at with causal inference. I have a handle on some of it, but every now and then I find myself in a forest of "the joint probability on theta given the marginal conditions of Y presupposes independence from A" trees and I need to come up for air, a cup of tea, and a refresher.  

And maybe you do KNOW it, but it's still nice to have backup. 

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


### Observational Studies

>"The best explanation of an association between treatment and outcome in an observatinal study is not necessarily a causal effect of the treatment on the outcome" -What If? by Miguel Hernan and James M. Robins 

Analytically, we treat observational studies as conditionally randomized experiments, where we conditioned the treatment assignment on a set of covariates L. This works under the following assumptions:
  1. The values of the treatment under comparison correspond to well-defined         interventions that correspond to versions of the treament in the data            (**consistency**)
  2. The conditional probability of receiving every value of treatment depends     only on measured covariates L (**conditional exchangeability**)
  3. The probability of receiving every value of treatment conditional on L is     greater than 0 (**positivity**)
  
Together, these three assumptions are termed the **identifiability conditions**. 

In experimental studies, exchangeability and positivity are built into the design. Observational studies, in contrast, do not guarantee either. Selection biases can create conditions in which only one type of person is experiencing a given treatment level. 

Back to the stomach ache example: when you go to the gas station you always eat a pack of sour straws and chug a Mountain Dew. You then get a stomach ache. You have no way of knowing whether the sour straws or Mountain Dew is responsible for this because you *always* consume them together. You have no data on what happens if you only drink a Mountain Dew, and therefore have no comparison to make. 


## Symbols

- **Pr[Y]** - The marginal probability of event Y. 
- **Pr[Y|A]** - The conditional probability of event Y given A. 

## References 

1. [Hernán MA, Robins JM (2020). Causal Inference: What If. Boca Raton: Chapman & Hall/CRC.](https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/)
