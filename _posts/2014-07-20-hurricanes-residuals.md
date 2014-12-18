---
layout: post
title:  Deadly hurricane re-analyses and the importance of plotting those residuals
author: Sean Anderson
---

During this temporary summer holiday from Stats Beerz meetings I thought I'd pass this on.

You might have heard of a recent paper in PNAS purporting that hurricanes with female names are more deadly than hurricanes with male names:
<http://www.pnas.org/content/111/24/8782>

It gained a lot of press and a number of statistical big guns jumped in.

Ignoring most of the back and forth debate and ethical accusations, this re-analysis by Bob O'Hara (senior editor of Methods in Ecology and Evolution) is an excellent window into an experienced statistician tackling an applied modelling problem:

<http://rpubs.com/oharar/19171>

Which was written up in the Guardian here:
<http://www.theguardian.com/science/grrlscientist/2014/jun/04/hurricane-gender-name-bias-sexism-statistics>

If you take away one thing, notice the importance of plotting your residuals against everything under the sun. Plot them against fitted (predicted) values and plot them against all your predictors. For valid inference, there shouldn't be noticeable trends, clumping, or changes in spread. The presence of any of these can suggest a different structure to the model, clumping can also suggest the need for a correlation structure or random effect, changes in spread can also suggest the need for a variance structure.

Extra links for those interested:

Follow-up analysis by Bob O'Hara:

<http://rpubs.com/oharar/20012>

Andrew Gelman comments:

<http://andrewgelman.com/2014/06/06/hurricanes-vs-himmicanes/>
<http://andrewgelman.com/2014/06/17/hurricaneshimmicanes-extra-problematic-nature-scientific-publication-process/>
<http://andrewgelman.com/2014/06/18/jeremy-freese-adds-new-item-lexicon/>

Jeremy Freese comments:

<http://scatter.wordpress.com/2014/06/03/my-thoughts-on-that-hurricane-study/>
<http://scatter.wordpress.com/2014/06/10/the-hurricane-name-study-gets-worse/>
<http://scatter.wordpress.com/2014/06/16/the-hurricane-name-people-strike-back/>
<http://scatter.wordpress.com/2014/06/17/the-hurricane-name-study-tries-again/>
