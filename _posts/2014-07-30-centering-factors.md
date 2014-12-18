---
layout: post
title:  Centering factors for model averaging with interactions
author: Sean Anderson
---

I've worked with a number of people recently on model averaging with
interaction coefficients. Over time I developed the following blog post
to answer questions people had:

<http://seananderson.ca/2014/07/30/centering-interactions.html>

Take home message: If you average across models with and without
interactions and you don't center your predictors by subtracting their
mean, your results won't make sense. You are averaging across
coefficients that have different meanings in different models.

I work through an example with 2 and 3 factor levels, show how to
translate these coefficients into predictions on the original data
scale, and show how to combine the standard errors to derive confidence
intervals at the uncentered factor levels.

Hopefully you'll find the explanation and code helpful if you run into a
problem like this,

