### Formulas for Test Statistics

[Source](https://statisticsbyjim.com/hypothesis-testing/test-statistic/)

|                                               |                                                                                                                                                                          |                                                                                                        |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| **Test Statistic**                            | **Formula**                                                                                                                                                              | **Finding**                                                                                            |
| T-value for 1-sample t-test                   | ![Test statistic formula for the 1-sample t-test.](https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2022/01/1-sample_t_test_statisticb.png?resize=89%2C55&ssl=1) | Take the sample mean, subtract the hypothesized mean, and divide by the [[Standard Error of the Mean]] |
| T-value for 2-sample t-test                   | ![Test statistic formula for a 2-sample t-test.](https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2022/01/2-t_test_statistic.png?resize=129%2C77&ssl=1)          | Take one sample mean, subtract the other, and divide by the pooled standard deviation.                 |
| F-value for F-tests and ANOVA                 | ![Test statistic formula for an F-test.](https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2022/01/F_test_statistic.png?resize=61%2C57&ssl=1)                     | Calculate the ratio of two [[Variance]]s.                                                              |
| Chi-squared value (χ2) for a Chi-squared test | $$ \chi^{2} = \sum \frac{({\text{Observed} - \text{Expected}})^{2}}{Expected} $$                                                                                         | Sum the squared differences between observed and expected values divided by the expected values.       |
| [[Mann-Whitney U test]]                       | $\min_{}(U_{1}, U_{2})$    $U_{i} = n_{1}n_{2} + \frac{{n_{i}(n_{i}+1)}}{2} - R_{i}$ $R_{i} = \text{Sum of ranks, in group } i$                                          | Calculate sums of ranks and use it, does not require assumptions of normal distribution.               |
|                                               |                                                                                                                                                                          |                                                                                                        |