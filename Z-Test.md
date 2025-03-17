#### hypothesis test in which the z-statistic follows a normal distribution. Can be used to determine whether the population mean is the same as the hypothesized mean $\mu_0$, assuming the population standard deviation $\sigma$ is known

When performing a hypothesis test involving the mean of a single population with a known std dev, the distribution of the t-test statistic $\left(\displaystyle\frac{\bar{x} - \mu_0}{\frac{\sigma}{\sqrt{n}}} \right )$ is assumed to be $N(0,1)$. in practice population std dev is rarely known, so more useful test involves [[T-Distribution - T-Test]] because the std dev of a sample can always be computed

#### Conditions for performing z-test:
- Randomness - Data should be collected randomly by means of simple random sampling, stratified random sampling, or cluster sampling. For the examples presented in this material, this condition can be assumed.
- Independence -Each observation should not affect other observations. In most surveys, sampling is performed without replacement, which means that a person or an observation is not used twice. For sampling without replacement, the sample size should be less than 10% of the population size to guarantee independence.
- Normality -The sampling distribution should be approximately normal, which is guaranteed either when the sample size is at least 30 by the CLT or when the data's parent distribution is also normal


#### Hypothesis Z-testing for population means

Given a randomly selected sample taken from a population with a known population standard deviation σ

1. Set the null and alternative hypotheses
	$H_0: \mu = \mu_0$
	$H_a: \mu > \mu_0 (\text{right-tailed})$
    $H_a: \mu < \mu_0 (\text{left-tailed})$
	$H_a: \mu \neq \mu_0 (\text{two-tailed})$
	
    where μ is the population mean and $\mu_0$ is the hypothesized population mean.
    
2. Use statistical software to find the test-statistic
#### $z = \frac{\bar{x}-\mu_0}{\frac{\sigma}{\sqrt{n}}}$
    
3. Use statistical software or a table to find the p-value that corresponds to z.
4. Make a decision given a previously selected significance level α, typically 0.05 - OUR CHOICE
    - If the p-value is less than the significance level, sufficient evidence exists to reject the null hypothesis $H_0$ in favor of the alternative hypothesis $H_a$.
    - If the p-value is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis $H_0$.

For two-tailed alternative hypothesis:
- -If _2p-value_ is less than the significance level, sufficient evidence exists to reject the null hypothesis in favor of the alternative hypothesis
- If _2p-value_ is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis



#### Python code

The code below loads the exam scores data and finds the z-test statistic and two-tailed p-value for the following hypotheses about the Exam 1 scores: $H_0:μ=86$ and $H_a:μ≠86$.
```
from statsmodels.stats.weightstats import ztest
import pandas as pd
scores = pd.read_csv('ExamScores.csv')
print(ztest(x1 = scores['Exam1'],  value = 86))
```


### [[Hypothesis Testing Examples]]
