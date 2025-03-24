### Simple Linear Regression [[One-Way ANOVA]] F-Test

A method or testing $H_0:β_1=0$ versus $H_a:β_1≠0$. For simple linear regression, the ANOVA F-test is equivalent to the slope t-test

ANOVA table includes the following:
![[Pasted image 20250322102031.png]]

### SLR Anova F-test steps
- Set the null hypothesis, $H_0:β_1=0$, versus the alternative hypothesis, $H_a:β_1≠0$.
- Use statistical software to find the F-statistic, which is the regression mean square divided by the residual mean square. The ANOVA F-statistic is the same as the square of the slope t-statistic.$$F=\frac{M⁢S⁢R}{M⁢S⁢E}$$
- Use statistical software to find the p-value that corresponds to the F-statistic. The p-value is the probability of observing an F-statistic at least as far from 0 as the one observed, if the null hypothesis were true. The reference F-distribution has p−1 numerator degrees of freedom and n−p denominator degrees of freedom. The ANOVA F-test has the same p-value as the slope t-test.
- Make a decision based on a previously selected significance level, typically 0.05:
    - If the p-value is less than the significance level, reject the null hypothesis, $H_0:β_1=0$, in favor of the alternative hypothesis, $H_a:β_1≠0$. Conclude that $β_1$ is significantly different from 0, which means that a statistically significant linear relationship exists between Y and X.
    - If the p-value is greater than or equal to the significance level, fail to reject the null hypothesis, $H_0:β_1=0$, in favor of the alternative hypothesis, $H_a:β_1≠0$. Conclude that $β_1$ is not significantly different from 0, which means that a statistically significant linear relationship does not exist between Y and X.

### Python
The `ols()` function takes two parameters, 'Y ~ X1' where Y is the response variable and X1 is a predictor variable, and a data frame. The sm.stats.anova_lm command takes in a linear model and an ANOVA type as parameters and outputs an ANOVA table. The different types of ANOVA are beyond the scope of this material. To give the correct output, the parameter for the ANOVA type, denoted as typ, is set to 2.

In the code below, Exam4 is the response variable and Exam1 is the predictor variable.
```python
from statsmodels.formula.api import ols
import statsmodels.api as sm
import pandas as pd
df=pd.read_csv("ExamScores.csv")

mod = ols('Exam4 ~ Exam1',df).fit()
print(sm.stats.anova_lm(mod, typ=2))
```

ANOVA table composition
![[Pasted image 20250322102447.png]]
