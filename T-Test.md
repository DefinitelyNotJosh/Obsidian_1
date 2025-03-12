#### Commonly used to compare observed sample mean to a hypothesis mean

Brush up on [[T-Distribution - T-Test]]

#### Conditions for t-distribution

- Randomness - Data should be collected randomly by means of simple random sampling, stratified random sampling, or cluster sampling. For the examples presented in this material, this condition can be assumed.
- Independence - Each observation should not affect other observations.
- Normality - The t-distribution can be used if the underlying population distribution is approximately normal. In most cases, the normality of the underlying distribution cannot be determined. Thus, the sample size determines whether the t-distribution can be used.
    - If the sample size is less than 15, the t-distribution can be used if the data is not skewed or no outliers are present.
    - If the sample size is between 15 and 30, the t-distribution can be used even if the data is mildly skewed. If outliers can be removed, then using the t-distribution is also appropriate.
    - The t-distribution can always be used when the sample size is sufficiently large and extreme outliers can be removed.


#### Hypothesis t-testing 

1. Set the null and alternative hypotheses
	$H_0: \mu = \mu_0$
	$H_a: \mu > \mu_0 (\text{right-tailed})$
    $H_a: \mu < \mu_0 (\text{left-tailed})$
	$H_a: \mu \neq \mu_0 (\text{two-tailed})$
	
    where μ is the population mean and $\mu_0$ is the hypothesized population mean.
    
2. Use statistical software to find the t-statistic and the degrees of freedom $df$
#### $t = \displaystyle\frac{\bar{x}-\mu_0}{\frac{s}{\sqrt{n}}}$ and $df = n - 1$
    
1. Use statistical software or a table to find the p-value that corresponds to t. The p-value is found using the [[T-Table]] with $df=n-1$
2. Make a decision given a previously selected significance level α, typically 0.05 - OUR CHOICE
    - If the p-value is less than the significance level, sufficient evidence exists to reject the null hypothesis $H_0$ in favor of the alternative hypothesis $H_a$.
    - If the p-value is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis $H_0$.

For two-tailed alternative hypothesis:
- -If _2(p-value)_ is less than the significance level, sufficient evidence exists to reject the null hypothesis in favor of the alternative hypothesis
- If _2(p-value)_ is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis 

#### Python code
The code below loads the exam scores data and uses the `scipy.stats.ttest_1samp()` function to find the t-test statistic and two-tailed p-value for the following hypotheses about the Exam 1 scores: $H_0:μ=82$ and $H_a:μ≠82$.
```
import pandas as pd
import scipy.stats as st
scores = pd.read_csv('ExamScores.csv')
print(st.ttest_1samp(scores['Exam1'], 82))
```


