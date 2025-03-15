### [[Z-Test]] for population proportion can be used 

When performing a hypothesis test, the distribution of the z-statistic is assumed to be $$N\left( p_0, \sqrt{ \displaystyle\frac{p_0 (1-p_0)}{n}}\right)$$
#### The conditions that must be satisfied:
$np_0 \geq 5, n(1-p_0) ≥ 5$ where $n$ is the sample size and $p_0$ is the hypothesized proportion


#### Procedure:
1. Set the null and alternative hypotheses
	$H_0: p = p_0$
	$H_a: p > p_0 (\text{right-tailed})$
    $H_a: p < p_0 (\text{left-tailed})$
	$H_a: p \neq p_0 (\text{two-tailed})$
	
    where $p$ is the population proportion and $p_0$ is the hypothesized population proportion.
    
2. Use statistical software to find the test-statistic
#### $$z = \frac{\hat{p}-p_0}{\sqrt{\displaystyle\frac{p_0 (1-p_0)}{n}}}$$
    
3. Use statistical software or a table to find the p-value that corresponds to z.
4. Make a decision given a previously selected significance level α, typically 0.05 - OUR CHOICE
    - If the p-value is less than the significance level, sufficient evidence exists to reject the null hypothesis $H_0$ in favor of the alternative hypothesis $H_a$.
    - If the p-value is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis $H_0$.

For two-tailed alternative hypothesis:
- -If _2p-value_ is less than the significance level, sufficient evidence exists to reject the null hypothesis in favor of the alternative hypothesis
- If _2p-value_ is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis

#### Python example: 
 ```python
from statsmodels.stats.proportion import proportions_ztest
counts = 31
nobs = 50
value = 0.50
print(proportions_ztest(counts, nobs, value, prop_var = value))
```

