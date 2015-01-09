---
layout: post
title: ANOVA vs. regression
author: Sean Anderson
---

> From a linear model in R, I always report the summaries so I have coefficients and their p-values. Granted I need to think hard about what these mean in a multivariate model, especially when there are interactions, etc., but usually it makes sense when I plot the slopes on the data.

> But I have run into a culture of reporting ANOVA tables. Why are p-values in ANOVA tables different from in the summary statistics? I thought I understood linear models, but I guess don’t understand ANOVAs.

They are typically the same model but set up and reported slightly differently. Which is preferable largely comes down to what comparison you want to make. Seems to me like there's a trend towards the regression approach, but there's still room for the ANOVA interpretation.

I think this quote from the first link below sums it up well:

"In the ANOVA, the categorical variable is effect coded, which means that each category's mean is compared to the grand mean. In the regression, the categorical variable is dummy coded, which means that each category’s intercept is compared to the reference group's intercept."

Three links with answers of increasing complexity:

<http://www.theanalysisfactor.com/why-anova-and-linear-regression-are-the-same-analysis/>

<http://stats.stackexchange.com/questions/555/why-is-anova-taught-used-as-if-it-is-a-different-research-methodology-compared>

Andrew Gelman: Analysis of variance—why it is more important than ever:
<http://arxiv.org/abs/math/0504499>

Also, a fantastic paper on improving the interpretability of categorical 
coefficients in regression:

"Simple means to improve the interpretability of regression coefficients", Holger Schielzeth,
<http://onlinelibrary.wiley.com/doi/10.1111/j.2041-210X.2010.00012.x/abstract>

> Thanks for the timely feedback. I'm actually using mixed effects models.
Does that make a difference?

No, I don't think so. They're still just two ways of slicing the same thing.

(Although I don't know what model you're fitting, so maybe I'm not
understanding.)

This is all assuming that you have a balanced design, which, if I
remember correctly, is an assumption for the ANOVA but not the mixed
effect model.

If you're having trouble understanding what's going on, one approach
is to simulate some data and fit it different ways.

Another link I stumbled on:
<http://conjugateprior.org/2013/01/formulae-in-r-anova/>
