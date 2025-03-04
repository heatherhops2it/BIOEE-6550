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

#### Correlation for circular data

Circular data: data measured on a circular scale. (e.g., angles, wind
direction, time of day, day or year, which has a *cyclic* nature).

AKA directional or angular data.

Often visualised in polar coordinates (like a graph around a point)

It’s important that we have special tests for circular data, because
regular linear analysis might not catch patterns that exist.

<br>

Circular vs. linear variables: makes sense for my brain. A single circle
graph.

Circular vs. circular variables: difficult for me to visualise.

<br>

There are other circular statistics, too.

**Circular mean**. TK

**Circular variance** and circular standard deviation. E.g., is wind
direction more variable in this month than that month?

<br> <br>

## Simple Linear (bi-variate) Regression

Purpose of regression:

TK

<br>

We can’t use the correlation coefficient to answer questions such as “if
we increase radiation by 10W, the Net Ecosyste Exchange will change by
how much?”

We need to use the **regression coefficient** for that.

Seeing how a change of a given amount will affect another variable is
the **sensitivity**. Note that the sensitivity can change across the
range of your variables. (e.g., a 10W change in radiation might change
NEE by A amount at 200W, but by B amount at 400W).

<br>

The *error* of a regression model is called the **residual**.

Residuals are often assumed to be normally distributed with a zero mean
and fixed variance.

<br>

#### Diagnostics

You want some way to assess whether your model is good.

TK

<br>

OLS models are built on certain assumptions:

- **Linearity**. Visually tested through scatter plot but be careful
  with extrapolation! (Linearity might not hold true outside of your
  sample range)

- **Normality of residuals**. Use a Q-Q plot and Shapiro-Wilk test.

- **Homoscedasticity** (equal variance across all X/Y values). Formal
  tests are available; can also plot residuals against predicted Y.

- **Outliers** (errors/other processes, which have a *disproportionate*
  effect on OLS results). Use Cook’s distance to diagnose.

- **Independence** (experimental design, temporal autocorrelation,
  spatial autocorrelation). Autoregressive models can help to capture
  some of the effects.

You can see these tests using `lm()` in R.

You can also compare Pearson’s *r* and Spearman’s *r* to test for
normality of residuals. If they are noticeably different, you have
problems.

<br>

#### Prediction

TK

<br> <br>

## Multivariate regression (adding more X)

What do we do when there are multiple factors that may impact the
result? (Y as a result of X1 and X2 and X3 …)

Additive effects

- Y ~ X1 + X2

<br>

For multiple independent variables:

- All assumptions for simple linear regression hold
  - Linearity, independence,
  - TK

<br>

Interactive effects

- Y ~ X1 + X2 + X1 \* X2

<br>

**Overfitting**: Over-explanation of the error term that leads to
reduced predictive power of a model.

Always try to link coefficients/variables with data generating
processes.

<br>

**Collinearity**

It is less worrisome if the main purpose is for predictions (especially
within the range of your training data).

It is more problematic if the main purpose is for inference of causal
relationships/sensitivity.

A common sign of problematic collinearity is large changes in parameter
coefficient when removing/adding explanatory variables.

We can use the **Variance Inflation Factor** (VIF) to quantify the
degree of collinearity.

VIF \> 5 indicates mild collinearity. VIF \> 10 indicates severe
collinearity.

^ These are, however, a little subjective.

Collinearity is easy to detect. Hard to deal with it, though. :/

There are a number of recommendations:

- Check the variables with high linearity and make sure they provide
  different information/represent different hypotheses in your model
- Separate your data into smaller subset and use regression model from
  one subset to predict another (aka *cross-validation*). This helps to
  estimate the imapct of collinearity to out-of-sample predictions.
- Leave the variables as they are if both of them are significant, which
  TK
- TK
- TK

<br> <br>

## Path Analysis/Structural Equation Modelling (adding more Y)

Path analysis is structural equation modelling which can test a set of
regression equations simultaneously.

The diagrams you get can be pretty crazy.

You need *a priori* definition of causal flow (directional acyclical
graph). Usually you need to compare multiple graphs to see which one is
the best.

TK
