---
layout: post
title: Likelihood, AIC, and Frequentist vs. Bayesian parameter interpretation
author: Sean Anderson
---

Following on from the original version of [Joel's post]({% post_url 2015-02-14-r-squared-hierarchical-models %}):

To be specific, AIC is a measure of relative goodness of fit. One
component of AIC is the value of the likelihood function at the point
of maximum likelihood, but AIC is not a likelihood itself. (Keep in
mind that the word 'likelihood' has a very specific definition in
statistics but has a looser colloquial meaning.)

The likelihood can only go up as you add in more parameters (similar
to how the R-squared of a linear regression can only go up as you add more
parameters), but the model may not have superior out-of-sample
performance. Information theoretic measures (of which AIC is a common
one) provide an approximation to this out-of-sample performance. In
other words, a model with a better information theoretic measure is
expected to provide better predictive ability on a new dataset.

The important thing to remember in terms of data and parameter
probabilities is that in a frequentist interpretation the parameters
are considered fixed and the data random. We then ask questions about
the probability of observing data like we did if we hypothetically
were to sample the data from the population many many times. For
example, the p-value tells us the long run frequency of which we would
expect to view data with a test statistic at least as extreme as
observed even if the null hypothesis were true. The 95% frequentist
confidence interval around a parameter says that if we theoretically
collected the data many times and calculated the same confidence
intervals, about 19 times out of 20 those confidence intervals would
contain the true (population) parameter value. The confidence interval
we calculate is just one realization of those confidence interval*s*.
A bit of a mind twist, yes.

Bayesian inference, on the other hand, lets us flip that around and
ask what the probability of certain parameter values are given the one
fixed realization of data. The data are fixed and the parameters have
a probability distribution. This is how we usually want to intuitively
interpret our results, so be careful.

Regarding hierarchical model R-squared values, keep in mind that these don't
have the same clean interpretation as say an R-squared value in a simple
linear model. There are lots of caveats, and the end of that paper by
Nakagawa and Schielzeth outlines many of them. (Hey, I just realized
this is the same Schielzeth as that other great paper on making
regression coefficients more interpretable.) There's no substitute for
good graphical exploration of your model. In the same vein as R-squared,
predicted vs. observed plots and especially out-of-sample predicted
vs. observed plots (at various levels for a hierarchical model) will
give a good sense of model performance and if presented thoughtfully
can also illustrate what aspects of the data are being predicted
better than others. Readers can also interpret whether a given level
of scatter is meaningful on the original response scale. Sometimes
though, you, a reviewer, or a co-author will really want an R-squared-like
value to summarize a model in text, and that's fine too.
