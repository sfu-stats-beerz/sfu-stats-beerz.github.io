---
title:  Propensity score matching
author: Jillian Dunic
---

## Question

We had a great question from a Dr. (the medical kind!) about choosing comparable sample populations.

In this example, the situation was as follows:

- 26 patients were already determined, these patients had been subject to treatment A
- an existing pool of 700 patients could be selected, which had been subject to treatment B
- needed to control for covariates such as age, gender, medication, etc.,

The question boiled down to: How can I select the 26 most comparable patients from the pool of 700 to the 26 patients that were predetermined?


## Solution

A potential solution was to use **propensity score matching** to objectively select from the pool of 700 treatment B patients, the most similar ones to the already determined 26 patients from treatment A. Another suggestion to limit any bias in the data, was to first remove any extreme cases/patients from the pool of 700 before applying propensity score matching. Such that patients with special circumstances (e.g., patients with risk factors for complications) were removed. 


## Example
Jess Walsh provided us with an example from her own research:

"Does recovery planning improve the status of threatened species? Bottrill et al. 2011 Biological Conservation.

In this study, we wanted to test the difference in recovery between threatened species with and without a recovery plan. We took the species with recovery plans and matched them with species that were similar without a recovery plan, across all other factors that might change the probability of recovery. 

Direct explanation from the paper:
Propensity-score matching attempts to reduce the confounding effects of covariates (Rosenbaum and Rubin 1983). We calculated the propensity score by conducting a logistic regression in which presence of a plan is the response variable (Z = 1 with plan; Z = 0 with no plan).

‘Matching’ was the technique used to select species with plans and without plans based upon the similarity of their propensity score. We used the software extension package, MatchIt (Ho et al., 2009) to the statistical program, R (R Development Core Team, 2005) to match sets of species with and without plans using a propensity score nearest neighbor matching estimator without replacement."


## Relevant R packages
[MatchIt Vignette](https://cran.r-project.org/web/packages/MatchIt/vignettes/matchit.pdf)

[MatchIt Documentation](https://cran.r-project.org/web/packages/MatchIt/MatchIt.pdf)