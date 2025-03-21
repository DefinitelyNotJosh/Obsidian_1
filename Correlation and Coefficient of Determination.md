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
Gives ratio of 