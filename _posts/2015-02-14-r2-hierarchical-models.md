---
layout: post
title: R-squared for hierarchical models
author: Joel Harding
---

For anyone struggling with calculating a proper R-squared for hierarchal models: (see [this paper](doi.org/10.1111/j.2041-210x.2012.00261.x) where the associated code was not straight forward)

There is a function embedded inside the MuMIn package (`r.squaredGLMM`) that calculates both marginal (fixed effects only) and conditional (fixed and random effects) R-squared values for you instead of having to follow the mind-numbing coding in the paper. See following link for info:

<https://ecologyforacrowdedplanet.wordpress.com/2013/08/27/r-squared-in-mixed-models-the-easy-way/>

Part of the issue with using [...] AIC is that it only gives a measure of relative model performance. Whereas some form of R-squared gives a better sense [in absolute terms] of how well a model fits the [...] data (which AIC alone does not address).

Combining the two; competing models in AIC then presenting an R-squared of the top model, is a decent way to address this issue, especially for those itching to see an R-squared in lieu of a dreaded p-value!

Unfortunately the current function does not work with the glmmADMB package. I believe it covers non-normal distributions with the exception of Poisson.

As a follow-up:

Two papers worth the read if you haven't already, and always worth a re-read if it's been a while, are attached. They provide digestible overviews of information theoretics and issues to be aware of.

Read the Richards paper first...

Richards, S. A. (2005). Testing Ecological Theory Using the Information-Theoretic Approach: Examples and Cautionary Results. Ecology, 86(10), 2805–2814. doi:10.2307/3450706 <http://www.jstor.org/stable/3450706>

Anderson, D. R., & Burnham, K. P. (2002). Avoiding Pitfalls When Using Information-Theoretic Methods. The Journal of Wildlife Management, 66(3), 912–918. doi:10.2307/3803155 <http://www.jstor.org/stable/3803155>

