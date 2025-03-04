Lecture 3: Statistical Inference
================
Hopper
2025-02-03

## Inference

“We have the data, but we don’t know what the data generating process
is”

*Descriptive stats* is only concerned with observed data/samples, and
*inferential stats* is concerned with the population/underlying natural
processes.

Descriptive stats (e.g., mean, variance, skewness, kurtosis of sample,
etc.) only needs observed data.

Inferential stats requires \[fill tk\]

<br>

## Point Estimate

**Estimator** is a formula used to calculate an estimate

- The estimator of θ is usually denoted as θ hat

You always want to find a good-quality estimator. It has many dimensions

- Bias: An estimator is unbiased if the mean value of the estimator
  under many repeated samplings from the population is equal to the
  parameter of interest.

  - bias is the distance between, for example, the sample’s mean and the
    population’s mean.

- Precision: The standard deviation of θhat under repeated sampling
  (“sample distribution”). An estimator is precise/efficient if se(θhat)
  is low.

  - sd vs se: se (standard error) only applies to the estimator. sd
    (standard deviation) applies to the distribution of data

- Consistency: An estimator θhat is consistent if its value converges in
  probability to θ when the sample size N increases indefinitely. A
  consistent estimator can be biased.

So how does that all influence our stat’l analysis?

<br>

## Summary of above

Infer population variance with sample data needs the (N-1) correction to
make the estimator **unbiased**.

Biased estimator can be consistent, which means if you have a **big
enough** sample size, a biased estimator can be very close to true
values.

**Standard error** applies for the variation of the estimator, not the
data. It usually decreases with sample size. It can be used to estimate
the necessary sample size for the desired error level.

<br>

## Confidence Interval

Since inference is imperfect, we need an interval around it. This shows
the range in which the true value should exist.

Confidence Interval (CI): Random variable to describe the interval that
can cover the true parameter value (fixed) above a given probability.

<br>

## Bootstrapping

Used when a standard error/confidence interval cannot be easily derived
analytically (e.g., median, quantiles, more complex metrics).

Key idea of bootstrapping is to estimate the properties of population
dist’n by **resampling the sample dist’n**

- Can give you some ideas about the population

General bootstrapping procedure includes:

1.  Draw *N* random samples (**with replacement**) from *N* observations

2.  Compute the estimator/parameter of interest (e.g., mean, variance,
    median, diversity indices)

3.  Repeat steps 1 and 2 for a large number of times (a few thousands or
    more) to get distribution of the estimator

4.  Calculate the properties of the estimator directly using the dist’n
    from step 3

Bootstrapping limitation: your sample dist’n needs to actually be
representative of the population dist’n.

Advantages

- Estiamte full dist’n of an estimator
- Often simple to implement under current computational resources

Disadvantages

- Not guaranteed to be consistent, esp’ly for heavy-tailed dist’ns
  (e.g., log-normal, Pareto dist’n, Student’s t-dist’n, etc.)
- Would not be effective if the samples are inherently biased.
