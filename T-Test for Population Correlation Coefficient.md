#### Hypothesis Testing

1. Set the null and alternative hypotheses
	$H_0: \rho = 0$
	$H_a: \rho > 0 (\text{right-tailed})$
    $H_a: \rho < 0 (\text{left-tailed})$
	$H_a: \rho \neq 0 (\text{two-tailed})$
	
    where $\rho$ is the population correlation coefficient
    
2. Use statistical software to find the test-statistic and the degrees of freedom $df$
#### $t = \displaystyle\frac{R\sqrt{n-2}}{\sqrt{1-R^2}}$ and $df = n - 2$
    
1. Use statistical software or a table to find the p-value that corresponds to t. The p-value is found using the [[T-Table]] with $df=n-1$
2. Make a decision given a previously selected significance level α, typically 0.05 - OUR CHOICE
    - If the p-value is less than the significance level, sufficient evidence exists to reject the null hypothesis $H_0$ in favor of the alternative hypothesis $H_a$.
    - If the p-value is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis $H_0$.

For two-tailed alternative hypothesis:
- -If _2(p-value)_ is less than the significance level, sufficient evidence exists to reject the null hypothesis in favor of the alternative hypothesis
- If _2(p-value)_ is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis 


### Python
The Pearson correlation coefficient function `pearsonr(x,y)` takes in two arrays or DataFrames x and y and outputs the Pearson correlation coefficient and the corresponding two-tailed p-value. The function requires the `scipy.stats` library.

The code below uses the Exam1 and Exam4 columns of the ExamScore dataset and outputs the correlation coefficient and the two-tailed p-value obtained.

Note that this two-tailed p-value (0.067) is twice the one-tailed p-value obtained in the example above (0.033).
```python
import pandas as pd
import scipy.stats as st
scores = pd.read_csv("ExamScores.csv")
print(st.pearsonr(scores['Exam1'],scores['Exam4']))
```
