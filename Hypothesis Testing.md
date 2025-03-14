#### The formal process by which a hypothesis is retained or rejected. Compares two competing hypotheses about a population, the null hypothesis and the alternative hypothesis
- Central goal - Determine whether $H_0$ can be rejected in favor of $H_a$, or see if $H_0$ fails to be rejected based on evidence in sample data

#### [[Hypothesis Testing Examples]]

### [[Z-Test]] for population means if population std dev is known
z-test - hypothesis test in which the z-statistic follows a normal distribution
### [[T-Test]] for population means if population std dev is unknown

#### Notes:
#### hypothesis
A proposed explanation of a phenomenon
- ex - If a lamp doesn't illuminate when turned on, hypothesis is "Lamp is not plugged in"

Hypothesis for one population:
A common hypothesis formed by researchers is whether the correlation of two variables in a sample suggests that those variables are correlated in the population

Hypothesis for two populations:
- ex - given samples from two populations, a hypothesis might be that the two populations have the same mean

#### null hypothesis
denoted as $H_0$, is a statement assumed to be true unless sufficient data indicates otherwise
- Typically a statement of equality between the true value of the population parameter and the hypothesized value or a statement of no difference between the params of two populations
- ex - The statement "the average salary of the residents of San Francisco is not different that the average salary of the residents of Austin" or" the average salary of the residents of San Francisco is the same as the average salary of the residents of Austin" is a null hypothesis
#### Make the null hypothesis against what you're trying to observe - if you think you'll see variation in data, make the null hypothesis that there won't be variation


#### alternative hypothesis
denoted as $H_a$, is a statement that contradicts $H_0$
- Typically asserts that the true value of the population parameter is not the same as the hypothesized value or that the params for the two populations are different
- ex - alternative hypothesis to the null hypothesis in ex above - "The average salary of the residents of San Francisco is different from the average salary of the residents of Austin, Texas."
May be left, right, or two-tailed depending on nature of difference from null hypothesis
- left-tailed alternative hypothesis - asserts that the value of a parameter is less than the value asserted in the null hypothesis.
- right-tailed alternative hypothesis - asserts that the value of a parameter is greater than the value asserted in the null hypothesis.
- two-tailed alternative hypothesis - asserts that the value of a parameter is not equal to, that is, either less than or greater than the value asserted in the null hypothesis.

#### Comparative experiments
Compare different groups
- ex - a treatment group given a treatment, a control group who is not

#### test statistic
value calculated from sample data during hypothesis testing that measures degree of agreement between the sample data and the null hypothesis
- Mathematically  - difference between the estimate and the value asserted in the null hypothesis divided by the standard error
### Hypothesis tests and associated test statistics

| Application                                      | Hypothesis test                          | Test statistic                                  |
| ------------------------------------------------ | ---------------------------------------- | ----------------------------------------------- |
| One or two population μ, p, known σ              | [[Z-Test]] - [[Z-Score]]                 | Z-statistic [[Z-Confidence Intervals]]          |
| One or two population μ, unknown σ               | [[T-Test]] - [[T-Distribution - T-Test]] | t-statistic [[T-Confidence Intervals - T-Test]] |
| Comparing a parameter among three or more groups | ANOVA                                    | F-statistic                                     |
| Comparing categorical variables                  | Chi-square test                          | χ2-statistic                                    |

#### statistically significant result
differs enough from a null hypothesis that a conclusion can be inferred about the population

#### p-value
probability of obtaining a result that is as extreme or more extreme than the data if the null hypothesis were true
- determined from the test statistic
If the p-value is less than a specified significance level, denoted by $\alpha$, then two possibilities exist:
- The null hypothesis is true and the observed data is relatively unusual with a sample statistic that is extreme simply due to chance.
- The null hypothesis is false and the alternative hypothesis provides a more reasonable explanation for the population parameter.
In most fields, $\alpha=0.05$ is used most often as the significance level for hypothesis testing
- probability that a result with an extreme deviation from the null hypothesis due to chance must be 5% or less for the result to be considered statistically significant

#### practically significant result
difference between the hypothesized value of a parameter and the sample statistic is large enough to be meaningful in real life
- statistically significant $\neq$ practically significant - number of employees showing up for work at 8am and number of employees arriving a 7:59am likely doesn't practically matter

#### type I error
incorrect rejection of a true null hypothesis - false positive
#### type II error
failure to reject a false null hypothesis - false negative


| Decision             | $H_0$ is True | $H_0$ is False |
| -------------------- | ------------- | -------------- |
| Fail to reject $H_0$ | No error      | Type II Error  |
| Reject $H_0$         | Type I Error  | No error       |

Significance level of a hypothesis, denoted $\alpha$, is the probability of making a type I error
Probability of making a type II error is denoted $\beta$, 
Power: probability $1-\beta$ of avoiding type II errors



### 7 Step Method
1. Parameter of interest - From problem context, identify the parameter of interest (mean for us most of the time)
2. Null hypothesis $H_0$ - State the null hypothesis $H_0$
3. Alternative hypothesis $H_a$/$H_1$ - Specify an appropriate alternative hypothesis, $H_a$/$H_1$
4. Test statistic - state an appropriate test statistic
5. Reject $H_0$ if: Define the criteria that will lead to rejection of $H_0$
6. Computation - Compute any necessary sample quantities, substitute those into the equation for the test statistic, and compute that value
7. Conclusion - Decide whether or not $H_0$ should be rejected and report that in the problem context. This could involve computing a p-value or comparing the test statistic to a set of critical values



