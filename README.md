# econ5200-lab12-instrumental-variables
# Instrumental Variables: Weak Instruments, Compliers and the Exclusion Restriction

## Objective
I studied how instrument strength and the exclusion restriction affect instrumental variable (IV) estimates.

## Methodology
- I simulated different instrument strengths with a true effect of 1.0 and compared OLS and 2SLS estimates.
- I repeated each simulation 500 times to examine how weak instruments affect the results.
- I used Card's (1995) dataset to estimate the effect of education on wages using college proximity as an instrument.
- I tested how a direct effect of the instrument on the outcome changes the 2SLS estimate.
- I wrote my own 2SLS function using two OLS regressions and compared the results with the `linearmodels` package.

## Key Findings
- With a weak instrument (median F = 0.5), the median 2SLS estimate was 2.038, compared with the true effect of 1.0 and the median OLS estimate of 1.998.
- At this instrument strength, 21.0% of estimates were statistically significant, but 98.1% of those significant estimates differed from the true effect by more than 0.5.
- In Card's dataset, the first-stage F was 16.7. The OLS estimate was 0.0740, while the 2SLS estimate was 0.1323.
- I found that increasing the direct effect of the instrument by 0.05 increased the 2SLS estimate by about 0.111.
- My own 2SLS function matched the `linearmodels` result of 0.1323. With fewer controls, I obtained a 2SLS estimate of 0.2587 and F = 58.0.

Overall, I learned that weak instruments can produce misleading results, and a significant estimate does not always mean it is reliable. I also learned why the exclusion restriction matters for causal interpretation.
