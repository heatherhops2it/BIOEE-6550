Lab 4 notes
================
Hopper
2025-02-26

working on circular data

<br>

#### 0.1 correlation

need to replace -9999 data, which indicates missing values, with `NA`

`kde_plots` becomes a *list* of figures. You can save figures within a
list and call them up(?)

<br>

#### 0.2 circular data

in ggplot, you basically make a regular plot, but then use
`coord_polar()` to make the plot on a circular plane

when you are using circular data for a year, you can choose whether to
use 365 or 366 for the number of days. you can also re-calculate for
leap years individually. it’s up to you and your willingness to incur a
certain amount of error/data gap.

for circular data:

- first need to convert the data into radians
- `circlin.cor()` and `cor.circular()` (I do not understand what the
  difference is. He did not say. Python had different functions for
  circular-linear data and circular-circular data, so maybe this has to
  do with that.)

<br>

#### 0.3 regression

includes diagnostic tests

`resid()` gets the residuals.

NB he accidentally overwrote `resid()` with an object `resid` on line
298. He notes that this is bad practice!

if Cook’s distance is larger than 1, that’s not good (for reasons??).
There’s a note on this in the Python code, but not in the R code \>:/

<br>

#### 0.4 multiple linear regression

two ways to quickly make a correlation matrix (visually)

`:` is for *interactive* effect ⬎

`SW_IN * VPD` is the same as `SW_IN + VPD + SW_IN : VPD`

the plot of the residuals (with homoscedasticity) that makes a heart
shape with the data: because we’re trying to fit a linear model to a
curved dataset. This indicates that something is wrong with our model.

when there’s an interaction term with high collinearity, you might want
to try removing it from the calculations to see whether the individual
factors are having significant effects.

ignore the VIF of the intercept (this might be a Python-only note?)
