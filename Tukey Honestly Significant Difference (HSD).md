#### Gives the 95% confidence intervals for the mean difference between pairwise groups and determines which mean difference is statistically significant. If 0 falls in the confidence interval, then difference between means is not statistically significant



#### Can use [Section 22.7 - EGR 361: Analysis of Engineering Data | zyBooks](https://learn.zybooks.com/zybook/UPEGR361ZuendelWinter2025/chapter/22/section/7)

#### Python code:
The `MultipleComparison()` function take the data frame column that contains the values and the data frame column that contains the levels as inputs and builds the models. The `tukeyhsd()` function displays the 95% Tukey's confidence intervals. The statsmodels.stats.multicomp library must be imported to use these functions.
```python
import pandas as pd
from statsmodels.stats.multicomp import (pairwise_tukeyhsd,MultiComparison)
df = pd.read_csv('ExamScoresGrouped.csv')
mod = MultiComparison(df['Scores'], df['Exam'])
print(mod.tukeyhsd())
```

