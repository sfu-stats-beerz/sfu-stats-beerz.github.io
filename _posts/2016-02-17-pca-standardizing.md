---
layout: post
title: PCA 101 and standardizing variables
author: Amanda Kissel and Pascale Gibeau
---


Summary of stats beerz discussions from February 16, 2016: 

Thanks to Pascale for writing this up! 

**Choosing variables to include in models:** 

- one way PCAs are useful is to summarize the information contained in a set of highly correlated explanatory variables that would 
anyway not be included together in a model because of their high correlations. PCAs allow reducing the dimensionality in the data, 
and produce composite axes that maximize the variation in that set of variables. You can then use these axes as the explanatory variables in your model, instead of all the individual variables. However, PCA won't be useful if one is specifically interested in given variable(s)and their explanatory power. In that case, it is better to use these variables directly in the model (and use stepwise approaches with AIC, e.g.).That question goes back to the difference between descriptive and predictive models; I would argue that PCAs are particularly helpful in the case of descriptive models, but may not be for predictive models (in general, there are always exceptions). And both approaches can be used together too, depending on the question(s) asked! For more on PCAs, you can see this entry on the Stats beerz archives Pascale wrote about multivariate stats [a little while back]({% post_url 2014-12-17-multivariate %}).

- One way to choose between two variables that are highly correlated and have the same (or similar) explanatory power, and are equally biologically relevant, is to decide which one is the most practical to estimate in the field (e.g. cheaper, easier to sample).

- Overall, I would say that there are no single ways to choose which variables to include in models, and it can always be argued that things should be done differently... As long as the reasoning is clear! ;-)

**On centering, scaling, and standardizing variables** (a re-occuring discussion we periodically have at stats beerz)

- Centering + scaling = standardizing; we do that to our explanatory variables before running models to ensure that the coefficients are easily and meaningfully comparable. When data are standardized, models report units of change in Y that are due to 1 SD of the Xs, all Xs having the same SD -- therefore making the comparison of effect sizes straightforward.  
- Centering is important even for binary variables.
- Standardizing is important when we have explanatory variables that are in different units and dimensions, for e.g. if comparing kms and meters, or temperature to areas, etc... SO most of the time for what we do ;-)
- We should standardize by 2 SD when including both qualitative and quantitative variables in models.

Here is a [blog entry](http://seananderson.ca/2014/07/30/centering-interactions.html) by Sean Anderson that explains standardizing. Also, a link to the always important [Schielzeth 2010 paper](http://onlinelibrary.wiley.com/doi/10.1111/j.2041-210X.2010.00012.x/abstract), Rylee and Danielle recommend paying attention to the example with birds. 

You can use a function in the package arm called [rescale](http://www.inside-r.org/packages/cran/arm/docs/standardize) to standardize by 2 SD, written by Andrew Gelman. 

And here is the [Greuber paper](http://onlinelibrary.wiley.com/doi/10.1111/j.1420-9101.2010.02210.x/full) mentioned yesterday by Danielle, and the [paper](https://palenlab.files.wordpress.com/2015/05/murray-et-al-2015-predicting-patchily-distributed-species.pdf) published by Rylee et al. in which he created candidate model sets for each of his hypotheses and then used the top models to run a set of mixed-hypotheses models -in relation to the first part of our discussion around Richard's work yesterday. 
