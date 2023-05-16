# P-Values and the Null Hypothesis


## Introduction

In this lesson, you'll dig deeper into the relationship between p-values and the null hypothesis, and their role in designing an experiment. 


## Objectives

You will be able to:

* Describe what it means to "reject the null hypothesis" and how it is related to p-value
* Identify examples of null and alternative hypotheses, including one-tail and two-tail tests

## Understanding the Null Hypothesis

As stated previously, scientific experiments actually have 2 hypotheses:

**_Null Hypothesis_**: There is no relationship between A and B   
Example: "There is no relationship between this flu medication and a *reduced* recovery time from the flu."

The _null hypothesis_ is usually denoted as $H_{0}$

**_Alternative Hypothesis_**: The hypothesis traditionally thought of when creating a hypothesis for an experiment  
Example: "This flu medication reduces recovery time for the flu."

The _alternative hypothesis_ is usually denoted as $H_{1}$ or $H_{a}$

An easy way to differentiate between the null hypothesis and the alternative hypothesis is that the null hypothesis is the more conservative choice. It always assumes that there is no difference between some variables of interest, and therefore when it is represented mathematically, it should always contain an equals sign ($=$, $\geq$, or $\leq$).

The alternative hypothesis is whatever claim you are trying to prove with an experiment. It posits that there is some difference between some variables of interest, and therefore when it is represented mathematically it should never contain an equals sign, but rather some symbol representing inequality ($\neq$, $<$, or $>$).

Whenever you are performing a statistical test, you are determining whether you have enough evidence to reject the null hypothesis. If you do not have enough evidence, you fail to reject the null hypothesis.

## p-Values and Alpha Values

No matter what you're experimenting on, statistical tests come down to one question: Is your p-value less than your alpha value? Let's dive into what each of these values represents, and why they're so important to experimental design. 

**_p-value_**: The probability of observing a test statistic at least as large as the one observed, by random chance, assuming that the null hypothesis is true.

If you calculate a p-value and it comes out to 0.03, you can interpret this as saying "There is a 3% chance of obtaining the results I'm seeing when the null hypothesis is true."

A low p-value means that either *the null hypothesis is false* or *the null hypothesis is true and a highly improbable event has occurred*. It is impossible to know which of these is what actually happened! So the best practice is to set an $\alpha$ prior to conducting the experiment, to establish what level of this particular kind of incorrectness you are willing to tolerate.

$\alpha$ **_(alpha value)_**: The marginal threshold at which you're okay with agreeing that the null hypothesis is implausible enough to be rejected. 

If you set an alpha value of $\alpha = 0.05$, you're essentially saying "I'm okay with accepting my alternative hypothesis as true when we expect that the null hypothesis would randomly cause the results I'm seeing less than 5% of the time."

When you conduct an experiment, your goal is to calculate a p-value and compare it to the alpha value. If $p < \alpha$, then you **_reject the null hypothesis_** because the idea that there is "no relationship" between the variables of interest has become too implausible.  Note that any good scientist will admit that this doesn't prove that there is a _direct causal relationship_ between some chosen "independent" and "dependent" variables, just that they now have enough evidence to the contrary to show that they no longer believe that there is no relationship between them.

In simple terms:

$p < \alpha$: Reject the _null hypothesis_ and in favor of the _alternative hypothesis_

$p >= \alpha$: Fail to reject the _null hypothesis_.

So for example, if you set an alpha of 0.05 and your statistical test produces a p-value of 0.02, you reject the null hypothesis. (You would say *we reject the null hypothesis at a significance level of 0.05*.) If you set an alpha of 0.05 and your statistical test produces a p-value of 0.06, you fail to reject the null hypothesis. (You would say *we fail to reject the null hypothesis at a significance level of 0.05*.)

***Whether something is statistically significant depends on the specified alpha value.*** Statistical significance is not a purely objective measure; it is dependent on the design choices you make as you set up your experiment.

### Choosing an Alpha Value

An alpha value can be any value set between 0 and 1. However, the most common alpha value in science is 0.05 (although this is somewhat of a controversial topic in the scientific community, currently).

Choosing an alpha value is also known as choosing a **significance level**. Much like choosing the confidence level for a confidence interval, you are attempting to balance between two undesirable outcomes.

* Confidence level trade-offs (review)
  * If a confidence level is too high, there is a higher risk of creating a range of values that is too wide to be useful. In other words, failing to produce any "interesting" confidence interval.
  * If a confidence level is too low, there is a higher risk of the true value being outside of the interval. In other words, producing an "interesting" confidence level that doesn't actually capture the true value.
* Significance level trade-offs (new concept)
  * If an alpha is too low, there is a higher risk of failing to reject the null hypothesis even though it is false. In other words, accidentally missing an "interesting" finding about the differences between variables.
  * If an alpha is too high, there is a higher risk of rejecting the null hypothesis even though it is true. In other words, accidentally claiming that you have an "interesting" finding about the differences between variables, even though that finding isn't true.
  
(For a longer aside about what scientists mean by "interesting", check out the classic, irreverent paper _That's Interesting!_ by sociologist Murray S. Davis ([DOI link](https://doi.org/10.1177%2F004839317100100211), [Google Scholar search](https://scholar.google.com/scholar?cluster=4050715004907820129&hl=en&as_sdt=0,33)))

In general, we tend to think that setting an alpha too high is more worrisome than setting it too low. For example, if we set a significance level of $\alpha = 0.5$, that means that if the null hypothesis is true, we would still get a statistically significant result (indicating to reject the null hypothesis) 50% of the time! Intuitively, that is not a good idea, because it means claiming lots of relationships between variables that don't actually exist. So generally we err on the side of setting the alpha lower and possibly missing some interesting relationships, in order to minimize all of these false positives.

At the same time, setting an alpha *too* low means we will miss a lot of interesting findings. So you will rarely see an alpha set lower than 0.01, and 0.05 is fairly standard.

In future lessons we will dig deeper into defining terms like "false positive" more precisely, and also consider the "multiple comparisons problem" that comes into play when performing multiple experiments with the same alpha.

## Null and Alternative Hypothesis Examples

There are many different ways that you can structure a hypothesis statement, but they always come down to some statement of equality (null hypothesis) and some statement of inequality (alternative hypothesis).

It is important that these two hypotheses are mutually exclusive (cannot both occur at the same time, so the intersection of $H_{0}$ and $H_{a}$ is the empty set) and exhaustive (all possible scenarios are represented by the union of $H_{0}$ and $H_{a}$). (You will see some contexts where they are not defined in an exhaustive way, but for our statistical tests they will need to be.)

In all of the following examples, we will focus on **statistical tests that compare means ($\mu$ values) of normally distributed data**. This is only one kind of statistical test! There are numerous other statistical tests for comparing categorical data, comparing variances of data, comparing an observed distribution to a theoretical distribution, comparing a sample to a population, etc. that we are not digging into just yet.

### One-Tail and Two-Tail Tests

In normally distributed data, you calculate p-values from t-statistics (or $z$-scores if the population parameters are known). One of the main considerations is whether to perform a **_one-tailed_** or a **_two-tailed_** test.  

**_Example One-Tail Hypotheses_**

A **_one-tailed test_** is when you want to know if a parameter from the treatment group is greater than (or less than) a corresponding parameter from the control group.

$H_{1} : \mu_{control} < \mu_{treatment} $ The treatment group given this weight loss drug will lose more weight on average than the control group that was given a competitor's weight loss drug 

$ H_{0} : \mu_{control} \geq \mu_{treatment}$  The treatment group given this weight loss drug will not lose more weight on average than the control group that was given a competitor's weight loss drug".

In general, $<$ or $>$ in the alternative hypothesis and $\geq$ or $\leq$ in the null hypothesis indicates that this is a one-tailed test.

**_Example Two-Tail Hypotheses_**

A **_two-tailed test_** is for when you want to test if a parameter falls between (or outside of) a range of two given values.

$H_{1} : \mu_{control} \neq \mu_{treatment}$ "People in the experimental group that are administered this drug will not lose the same amount of weight as the people in the control group.  They will be heavier or lighter". 

$H_{0} : \mu_{control} = \mu_{treatment}$ "People in the experimental group that are administered this drug will lose the same amount of weight as the people in the control group." 

In general, $\neq$ in the alternative hypothesis and $=$ in the null hypothesis indicate that this is a two-tailed test.

### What Does an Experiment Really Prove?

You may be wondering **_why you need a null hypothesis_** at all. This is a good question. It has to do with being honest about what an experiment actually proves.

Scientists use the null hypothesis so that they can be very specific in their findings. This is because a successful experiment doesn't actually _prove a relationship_ between a dependent and independent variable.  Instead, it just argues that there is enough evidence to convince us that the null hypothesis regarding this relationship is implausible.

Even if you have a statistically significant result, either of these could be true:

1. The null hypothesis about this relationship is actually true, and you experienced an unlikely sampling event
2. There is a lurking confounding variable that is actually responsible for the perceived relationship

However, we can call an experiment where $p < \alpha$ a "successful experiment" because we are confident that it's statistically unlikely for the first of those to occur. Handling confounding variables is much more challenging, although we will consider this in more depth when we learn about statistical models, especially multiple linear regression.

## The Null Hypothesis Loves You and Wants You To Be Happy

You've covered a lot about the null hypothesis and how it's used in experiments in this lesson, but there's a lot more to learn about it! 

Read the following article, [The Null Hypothesis Loves You and Wants You To Be Happy](https://byrslf.co/the-null-hypothesis-loves-you-and-wants-you-to-be-happy-3189413d8cd0).  This does an excellent job of explaining why the concept of the _Null Hypothesis_ is crucial to good science.  


## Summary

In this lesson, you learned about the relationship between p-values and the null hypothesis. You'll use this knowledge in all of the upcoming lessons about hypothesis testing, as well as later lessons about interpreting linear regression models!
