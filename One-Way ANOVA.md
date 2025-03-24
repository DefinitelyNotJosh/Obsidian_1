### One-way analysis of variance (one way [[ANOVA]])
#### [[ANOVA F-Test]]
#### One-way ANOVA Controls the errors associated with comparing multiple population means (Can also use predictor variables - ex, test scores,. Determines whether a statistically significant difference exists among the means of three or more populations.

In practice, no population parameters, only have a few sample populations, no "prior thing" to analyze

#### Hypothesis test follows same process as previous tests
Null hypothesis: All group means are equal
Alternative hypothesis: Two groups with unequal means exist

#### Assumptions for one-way ANOVA.

- Independence. Samples should be independent and drawn randomly.
- Normality. The underlying distribution of the populations from which the samples are drawn should be approximately normal.
- Homogeneity. The variances of the population distributions should be equal.

#### Procedure:
#### Procedure:
1. Set the null and alternative hypotheses
	$H_0: \mu_1 = \mu_2 = ... = \mu_k$
	$H_a: \mu_i \neq \mu_j, ~\text{for some}~ i \neq j$
	
    where $\mu_1, \mu_2...\mu_k$ are means from independent populations
    
2. Use statistical software to find the test-statistic ([[F-Distribution]])
#### $$F = \frac{MSB}{MSW}$$
    
3. Use statistical software to find the p-value that corresponds to F. the p-value is found from the F-distribution
4. Make a decision given a previously selected significance level α, typically 0.05 - OUR CHOICE
    - If the p-value is less than the significance level, sufficient evidence exists to reject the null hypothesis $H_0$ in favor of the alternative hypothesis $H_a$.
    - If the p-value is greater than or equal to the significance level, insufficient evidence exists to reject the null hypothesis $H_0$.


### Post-hoc tests
If null hypothesis is rejected, further analysis is required because the F-test does not determine which groups have different means. Post-hoc analysis determines which groups have different means, which group has highest mean, lowest mean, etc.
#### [[Tukey Honestly Significant Difference (HSD)]]
Gives the 95% confidence intervals for the mean difference between pairwise groups and determines which mean difference is statistically significant. If 0 falls in the confidence interval, then difference between means is not statistically significant

#### Python code:
`f_oneway()` function performs a one-way ANOVA. The function takes a number of lists of data as parameters, and returns the F-statistic and the p-value. The scipy.stats and statsmodels.formula.api libraries must be imported to use `f_oneway()`.

If the data is labeled according to group, `ols()` can also be used to generate an ANOVA table, which also gives the F-statistic and the corresponding p-value.

```python
import pandas as pd
import scipy.stats as st

# Import data
scores = pd.read_csv("ExamScores.csv")

# Statistics of each exam
exam1_score = scores[['Exam1']]
exam2_score = scores[['Exam2']]
exam3_score = scores[['Exam3']]
exam4_score = scores[['Exam4']]

print(st.f_oneway(exam1_score, exam2_score, exam3_score, exam4_score))

# Import packages for ols
import statsmodels.api as sm
from statsmodels.formula.api import ols

# Import data
df = pd.read_csv('http://data-analytics.zybooks.com/ExamScoresGrouped.csv')

# Perform ANOVA
mod = ols('Scores ~ Exam', data=df).fit()
aov_table = sm.stats.anova_lm(mod, typ=2)
print(aov_table)

# Import seaborn for plotting
import seaborn as sns

# Making a box plot
sns.boxplot(x="Exam", y="Scores", data=df)

```


