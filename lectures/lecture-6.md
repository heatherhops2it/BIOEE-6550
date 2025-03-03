Lecture 6 - Linear Regression II
================
Hopper
2025-03-03

Residuals: if negative, the datapoint is below average. If positive, the
datapoint is above average.

You can plot out your residuals spatially, to see if there is a link
between the residuals and some spatial distribution. This is important.
You theoretically want a random distribution of various values of
residual.

<br>

## TK?

Hierarchical data

Simpson’s paradox in ecology

- This phenomenon is called Simpson’s Paradox in statistics, describing
  the large differences between within-group variation and cross-group
  variation.

- More complex: nested groups (family/genus/species, etc)

- There might be connections between groups

Solution? Linear Mixed Models (LLMs)

- Starts with the basis that you average out each group to make a
  regression, then run within-group regressions on top of that. (This is
  a naive solution, and not good enough on its own)

- They introduce *fixed effects* (shared relationship/coefficient across
  all groups/levels) and *random effects* (stochastic part of the fixed
  effect in each group)

<br>

There’s also Random Intercept Models (RIMs (?))

<br>

Something about extracting variance will get you the percent of variance
associated with each variable you’re looking at. This is important
because it tells you which variables are most important (most
contributory to the effect you are seeing).

<br>

Another model: Model with Random Slopes

<br> <br>

### Considerations for LLM

1.  LLMs are “data hungry.” They need at least five “levels” (groups)
    for a random intercept term to achieve robust estimates of variance.
2.  Models can be unstable if sample sizes across groups are highly
    unbalanced (i.e., if some groups contain very few data, especially
    for random slope models)
3.  Difficulty in deciding the “significance” or “importance” of
    variance among groups ==\> can be overcome under Bayesian framework.
4.  Some danger of incorrectly parameterising/interpreting the random
    effects (especially with nested effects) (e.g., failure to consider
    the nested structures).

<br> <br>

## 2. Generalised Linear Models

Logistic regression

- Parametric method for regression when *Y* is binary (0/1), which has a
  Bernoulli dist’n.

- Instead of using the raw binary variable as the response variable,
  logistic regression assumes

  - TK
  - TK

<br>

Deviance residuals

- The error/residual term in OLS regressions is assumed to follow a
  normal dist’n, which might not apply in GLM

- Smaller deviance = larger probability of your model happening = better
  model

<br>

Assumptions/Diagnostics

- Linearity
  - The transformed expectation of *Y* is linearly related to *X*
  - Can evaluate by plotting residual against fitted *Y*, which should
    have no patterns.
- Response variable dist’n
  - Q-Q plots for residuals, which are expected to be quasi-normal
    dist’d
- Independence
  - TK

<br>

Different models: I think it has to do with transformations of data.
What model makes the data linear, which makes it easier to analyse? (I
think??)

Whenever your *Y* variable is non-linear, think about what GLM you can
use to transform the data (so I was right!)

<br>

Proportional data

- Bounded btwn 0 and 1, or more generally between *a* and *b*
- beta/Dirichlet regression can be used
- They are slightly different from GLM in the case that the mean and
  variance TK

<br> <br>

## 3. Temporal and Spatial Correlation

Periodic data: Data that has repeated patterns, usually in the domain of
time. The periodicity implies that data in the past can be correlated
with and thus predictive(!) of data in the future.

Periodicity strength and autocorrelation.

**Autocorrelation function (ACF)**: Autocorrelation coefficients as a
function of lag *k*

- Trend ==\> linearly declining AC (points closer in time are more
  similar)
- Seasonality ==\> peak AC at the frequency of seasonality
- White noise ==\> No significant AC

<br>

Spatial autocorrelation

- like timeseries, data collected across space might also bear some
  internal structure
- Tobler’s first law of geography ==\>
- TK

How to quantify degree of spatial autocorrelation? Moran’s *I*

- goes from -1 to 1
- -1 = perfectly dispersed (checkered plots)
- 0 = randomly distributed (no pattern)
- 1 = perfectly clustered (black-and-white cookie)

Calculate Moran’s *I* by looking at the neighbours of a given point

Obviously, Moran’s *I* will depend on the resolution of your plots. If
you draw your plots at 1m, 1km, 10km, etc., you may get different *I*
values.
