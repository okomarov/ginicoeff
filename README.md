# ginicoeff()
Matlab function that calculates the Gini coefficient

A simple function to measure the statistical dispersion of a distribution. This statistic is commonly used to assess inequality in income or wealth.
The coefficients ranges from 1 (total inequality, one person receives ALL) to 0 (total equality, everyone receives the same amount).
The function ignores NaNs and can be computed with or without sample correction.

### Syntax:
* `ginicoeff(in)` One input syntax, columwise gini coeffs.
* `ginicoeff(...,dim)` Dim along which to compute the coeff (1 or 2)
* `ginicoeff(...,NOSAMPLECORR)` Don't apply sample correction

`[COEFF, IDXNEG] = ...`
* `coeff`: n by 1 vector with gini coefficients where n is the number of series in In.
* `idxneg`: n by 1 logical index. True means that the computation of the gini coefficient for that series has been skipped due to negative values or insufficient elements (less than 2).

**NOTE**: this statistical measure is meant to be applied only on positive values. If a series contains negative values or the elements of the less than 2, the coefficient yields NaN and a warning is issued if IDX is not called explicitly.
