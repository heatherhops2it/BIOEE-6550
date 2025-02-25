Lecture 2: Uncertainty and Probability
================
Hopper
2025-01-27

<br>

## 

Uncertainty in your measurements/data: what causes it?

- Small sample size
- Diversity/heterogeneity
- Other variables! (Things you didn’t measure)

<br>

Deterministic vs stochastic processes

- Deterministic:
- Stochastic: there are factors you didn’t consider, and these cause the
  variability in the data. You are accidentally measuring different
  things each time you sample your system. (These things can be small!)

We can think about observed data as containing signal (effect) and noise
(uncertainty).

- This is a great metaphor for a bioacoustician

Signal + variation = noise Noise can help guide future studies. You can
consider questions that look at what was, in another question, noise and
makes it into signal. It’s important to be able to distinguish between
the signal and the noise when trying to answer your questions. General
trend: signal. Residuals in regression: noise.

Looking at your data:

- Connect signal to deterministic processes.
- Think about what potential questions lead to the noise.

<br>

## Fundamentals of Probability

Comparing across categories when looking at how distribution of data is
laid out: use percentages. (e.g., looking at flight height of different
bird spp.)

Terminology

- Experiment: A repeatable data collection process that has well-defined
  possible outcomes
- Events: Collections of experimental outcomes
- Event/sample space: All possible outcomes from an experiment (x-axis
  of a typical probability distribution)

So what is probability?

- Non-negative real number associated with each event that reflects the
  frequency or degree of beliefs of the events.
- Frequency: Frequentist
- Degree of beliefs: Bayesian

Probability distribution: Used when we’re looking for the probability
associated with every possible value across the event space.

Deterministic processes run a peak in a probability dist’n, and
stochastic processes run a width across a probability dist’n.

Sum of probability distribution = 1

Discrete variables: Probability Mass Function (PMF) fx(x) = P

Continuous variables: Cumulative Density Function (CDF) \[FILL IN\] and
then define \[fill in\]

### PDF vs CDF

When do you use one or the other?

Focusing on a specific range: easier to use PDF

Easier to see median of distribution with CDF

PDF useful in identifying modes and discussing small range of values

CDF easier to directly estimate quantiles

<br>

## Descriptive Statistics

Recall: mean, mode, range, percentile/quantile, inter-quartile range
(IQR)

If you’re looking at your probability distribution and you see a single
peak, you might think that there’s a deterministic process that explains
it. If you see two peaks, you might think that there are a couple of
explanatory deterministic processes.

*Expectation*

- Additional characteristics of distributions can be more formally
  derived using the concept of expectation.
- It’s like a weighted average using the PDF.

Moments are generated by expectations.

Moments are taken to four orders, which are used to describe different
aspects of the distribution.

*Mean* (First order moment)

(You know about mean)

*Variance* (Second order moment)

Measures the dispersion/variability of the random variable.

Comparing to the mean.

Called standard deviation.

*Skewness* (Third order moment)

Positive (tail on right), symmetrical (even tails), negative (tail on
left)

*Kurtosis* (Fourth order moment)

Shows peak of distribution

If you want to show how concentrated your data are around a central
value.

<br>

## Review Common Theoretical Distributions

Uniform distribution

- Everything is evenly spaced in the event space.
- Interpretation: Equal probability to get value between a and b
- Applications: Useful for bootstrapping

Bernoulli Dist’n

- Can only have 2 outcomes (1 or 0, failure or success, etc.)
- Can be used to model discrete processes
- Interpretation: Simplest experiment that has one of only 2 outcomes
- Example: coin toss
- Applications: Special case of Binomial dist’n

Binomial Dist’n

- Describes *n* consecutive Bernoullis
- Interpretation: Probability of *x* number of successes in *n*
  independent Bernoulli trials
- Example: \# of success of 10 predations from a lion, or \# of success
  of predations from 10 lions
- Applications: Model discrete occurrence among discrete trials,
  counting (occurrence) data, demographic processes (birth and death).
- Useful for me? Counting occurrences of fish sounds?
- Commonly used in ecology
