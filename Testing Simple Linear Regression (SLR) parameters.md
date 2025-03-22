Population regression line denoted with $\beta_1/\beta_0$, sample regression line denoted with $b_1/b_0$ 

### Test slope parameter 
To determine whether $b_1$ is sufficiently far from 0 to reject the possibility that $\beta_1=0$ in the population, the t-test can be used:
#### t-test for slope 

1. Set the null hypothesis, $H_0:β_1=0$, versus the alternative hypothesis, $H_a:β_1≠0.$
2. Use statistical software to find the t-statistic, which is $b_1$ divided by the standard error of $b_1$.
3. Use statistical software to find the p-value that corresponds to the t-statistic. The p-value is the probability of observing a t-statistic at least as far from 0 as the one observed, if the null hypothesis were true. The reference t-distribution has n−p degrees of freedom, where n is the sample size and p is the number of regression parameters (typically the number of predictor variables plus one for the intercept).
4. Make a decision based on a previously selected significance level, typically 0.05:
    - If the p-value is less than the significance level, reject the null hypothesis, $H_0:β_1=0$, in favor of the alternative hypothesis, $H_a:β_1≠0$. Conclude that $β_1$ is statistically significantly different from 0, which means that a statistically significant linear relationship exists between Y and X.
    - If the p-value is greater than or equal to the significance level, fail to reject the null hypothesis, $H_0:β_1=0$, in favor of the alternative hypothesis, $H_a:β_1≠0$. Conclude that $β_1$ is not statistically significantly different from 0, which means that a statistically significant linear relationship does not exist between Y and X.

### Python
The `ols()` function performs ordinary linear regression, and the `fit()` function fits the data to the regression line. These functions require the statsmodels.formula.api library to be imported. `ols()` takes two parameters. The first parameter is in the form 'Y ~ X', where Y is the response variable and X is the predictor variable. The second parameter is the dataset that contains the variables.

The `summary()` function returns a summary including estimates for the parameters, t-statistics, p-values, and confidence intervals.

All of the above functions require the statsmodels.formula.api library to be imported.
```python
import pandas as pd
import statsmodels.formula.api as smf
scores = pd.read_csv('ExamScores.csv')

model = smf.ols('Exam4 ~ Exam2', scores).fit()
print(model.summary())
```

