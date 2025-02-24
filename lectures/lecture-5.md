Lecture 5: Linear Regression I
================
Hopper
2025-02-24

## Covariance and Correlation

Strength of a linear association between 2 random variables can be
formalised into the concept of **correlation**.

What can result in correlation of A and B?

- Causal relationship (A ==\> B)
- Another factor affects both (C ==\> A and C ==\> B)
- Chance

Things happening by chance may show up more often when you have a small
sample size.

<br>

To get a quantitative assessment of correlation, we first need to
calculate a quantity called **covariance**.

Covariance that is negative = negative correlation (\\). Covariance that
is positive = positive correlation (/)

By scaling covariance by the variance of X and Ym we get **Pearson’s
correlation coefficient**.

<br>

Rejecting the null hypothesis!

We need to run a t-test for the estimator of both X and Y to see if they
are normally distributed. To get confidence interval.

There are other tests/things to do for non-normal or small sample size
data.

<br>

Pearson’s *r* ==\> linear relationship

Spearman’s rho ==\> monotonic relationship

Kendall’s tau ==\> similar to Spearman, but more robust to outliers and
small sample sizes

<br>

If you have a lot of data, you are almost guaranteed to have a low
*p*-value. Just keep that in mind when making your conclusions.

If you have strong outliers, you might want to use Kendall’s tau.

<br>

# Correlation for circular data

Circular data: data measured on a circular scale. (e.g., angles, wind
direction, time of day, day or year, which has a *cyclic* nature).

AKA directional or angular data.

Often visualised in polar coordinates.
