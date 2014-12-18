---
layout: post
title:  Nonsensical lme output
author: Sean Anderson
---

> I'm stumped right now, and am wondering if anyone has run into this issue before:

> I'm doing mixed-effects model selection, and if I divide my response variable by 1000, the model selection results change.  The fixed effect coefficients are the same (just divided by 1000), but the model ranks and deltaAICc values are different.

> In my mind, this shouldn't happen because dividing the response variable by 1000 is the same as measuring it in, say, millimetres instead of metres.  Same value, different units.

I don't know if this is the problem here, but many optimization algorithms struggle with very large or very small values.

The `?nlme::lme` help page reiterates this in a note: "The function does not do any scaling internally: the optimization will work best when the response is scaled so its variance is of the order of
one."

This is probably even more of a problem for estimating accurate random
effect variances than fixed effects, partly because the data are usually
just less informative about this.

So, I'd start by looking at the fixed and random effect estimates from
your two models and checking that they make sense. Plot them out against
the data. It's quite possible that the original models (before dividing
by 1000) are just wrong.

This is one reason why Andrew Gelman pushes for scaling of data (by
dividing by 1 or 2 standard deviations) as a default approach because it
ensures that your variables are on approximately the right scale. But
you can also use variables on a meaningful unit scale as long as they
have a variance of ballpark 1. In reality it's usually pretty forgiving
until you get a few orders of magnitude off.

Also, make sure you're fitting with maximum likelihood if you're
comparing AIC. And possibly (probably) switching to restricted maximum
likelihood for your final fits. Zuur's books cover this well.

