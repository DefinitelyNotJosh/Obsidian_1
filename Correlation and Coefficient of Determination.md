#### Correlation
Describes association/dependence between two variables
- positive - one var increases, other increases
- negative - one var increases, other decreases
##### Can be measured using the correlation coefficient
- Population corr. coeff - $\rho$
- sample corr. coeff - $R$
Strength described as $|R|$$

#### Strength of correlation

| Value of $\|R\|$     | Strength of correlation |
| -------------------- | ----------------------- |
| $0<\|R\| \leq0.4$    | Weak                    |
| $0.4<\|R\| \leq0.8$  | Moderate                |
| $0.8<\|R\| \leq1.00$ | Strong                  |
#### $$R = \displaystyle\frac{n \sum xy - \left(\sum x\right) \left(\sum y\right)}{\sqrt{n\left(\sum x^2\right) -\left(\sum x\right)^2} \sqrt{n\left(\sum y^2\right) - \left(\sum y\right)^2}}$$
#### correlation matrix
table that shows correlation coefficients between each pair of variables

### Python correlation
The correlation function `DataFrame.corr()` calculates the pairwise correlation of the columns in the dataframe and outputs a correlation matrix.

The code below uses the Exam1 and Exam2 columns of the ExamScore dataset and produces a 2×2 correlation matrix.

The code below uses the Exam1, Exam2, Exam3, and Exam4 columns of the ExamScore dataset and produces a 4×4 correlation matrix.
```python
import pandas as pd
scores = pd.read_csv("ExamScores.csv")
print(scores[['Exam1','Exam2']].corr())
print(scores[['Exam1','Exam2','Exam3','Exam4']].corr())
```

### [[T-Test for Population Correlation Coefficient]]

#### coefficient of determination
shows how well a regression equation represents the data
- denoted as $R^2$
Gives ratio of the variance in the response variable explained by the predictor variable
#### $$R^2 = \dfrac{\displaystyle\sum \left(\hat{Y}_i - \overline{Y}\right)^2}{\displaystyle\sum \left(Y_i - \overline{Y}\right)^2}~~ \text{or}~~ R^2=\frac{\text{explained variance}}{\text{total variance}}$$
where $\hat{Y}_i$ is he estimated value of $Y_i$ and $\overline{Y}$ is the mean of the $Y_i$'s
Since the coefficient of determination is the square of the correlation coefficient, $0 \leq R^2 \leq 1$

### Python $R^2$
Suppose a teacher wants to see whether Exam4 scores can be predicted using Exam1 scores. The value for R2 means that only 6.8% of the variance in Exam4 scores can be explained by the variance in Exam1 scores. The low value for R2 suggests that Exam1 is not a good predictor for how well a student would do in Exam4.
```python
# The necessary packages are imported
import pandas as pd
import scipy.stats as stats
import statsmodels.api as sm
from statsmodels.formula.api import ols

# The ExamScores dataset is loaded
scores = pd.read_csv('ExamScores.csv')

# Creates a linear regression model
results = ols('Exam4 ~ Exam1', data=scores).fit()

# Creates an analysis of variance table
aov_table = sm.stats.anova_lm(results, typ=2)

# Prints the analysis of variance table and results
print(aov_table)
print(results.summary())
```

