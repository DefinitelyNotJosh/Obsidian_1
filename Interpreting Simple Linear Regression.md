#### Regression parameters
- $b_0$ - represents estimated simple linear regression Y-intercept
- $b_1$ represents estimated linear regression slope

### Python - find estimates for slope and regression 
The code below loads the Reaction data and then obtains the sample linear regression equation.

From the output, the estimated reaction time in milliseconds is Y^=4+6⁢X where X is the number of alcoholic drinks.
```python
import pandas as pd
import scipy.stats as st
import statsmodels.formula.api as smf
df = pd.read_csv('Reaction.csv')
print(st.linregress(df['Drinks'],df['Reaction']))
```

#### Residual standard error
A number of quantities use the residuals, $\varepsilon_i = Y_i - \hat{Y}_i$

### Sum of square residuals: $$SSE = \sum_{i=1}^n (Y_i - \hat{Y}_i)^2$$
This is SSE, notation SSR used for regression sum of squares
### Residual degrees of freedom: $$n-p$$
where $p$ is the number of regression parameters
### Residual mean square: $$MSE = \frac{SSE}{n-p}$$
Residual sum of squares divided by degrees of freedom
### Residual standard error: $$s=\sqrt{\text{MSE}}$$
Estimates standard deviation of the residuals
Used in [[ANOVA]]/[[One-Way ANOVA]]

