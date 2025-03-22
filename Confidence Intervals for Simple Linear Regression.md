#### Interpretations of fitted values
- $\hat{Y}$ represents estimated mean of probability distribution of $Y$ for a fixed value of $X$
- $\hat{Y}$ represents predicted value of an individual instance of $Y$ from the probability distribution of $Y$ for a fixed value of $X$

#### Simple linear regression confidence interval for the mean: $$\hat{Y} \pm t_{n-2}^* s_y \sqrt{\dfrac{1}{n} + \dfrac{(x^* - \overline{x})^2}{(n-1)s_x^2}}$$
where $s_y$ is the Residual Standard Error ([[Interpreting Simple Linear Regression]])
an interval around $\hat{Y}$ that quantifies sampling uncertainty when $\hat{Y}$ is used to estimate $E(Y)$ for any fixed value $X=x^*$ 

#### simple linear regression prediction interval for an individual response: $$\hat{Y} \pm t_{n-2}^* s_y \sqrt{1 + \dfrac{1}{n} + \dfrac{(x^* - \overline{x})^2}{(n-1)s_x^2}}$$
where $s_y$ is the residual standard error
n interval around $\hat{Y}$ that quantifies sampling uncertainty when $\hat{Y}$ is used to predict $Y$ for a fixed value of $X=x^∗$ 


### Python
Find the regression parameter estimators, b0 and b1, and the residual standard error, _s_, for the alcohol and reaction time data using Python by using the code below.

After initializing and fitting a linear regression model, `model`, the regression parameter estimates are stored in `model.params`, and the residual standard error can be found by taking the square root of `model.scale`.

To find the predicted value for a given X, first a data frame should be created and then the `predict` method should be used. The code below defines a data frame where X = 4 and uses this value to predict the Y.

To find the confidence and prediction intervals for a given X, the `get_prediction` method should be used.

In the output below, `mean_ci_lower` and `mean_ci_upper` are the lower and upper bounds for the confidence interval respectively, while `obs_ci_lower` and `obs_ci_upper` are the lower and upper bounds for the prediction interval respectively.
```python
import statsmodels.formula.api as smf
import pandas as pd 
import numpy as np

df = pd.read_csv('Reaction.csv')
model = smf.ols('Reaction ~ Drinks', data = df).fit()

# Regression parameter estimators b0 and b1:
print('Parameter estimates:\n', model.params)

# Residual standard error:
print('\nResidual standard error:\n', np.sqrt(model.scale))

# Predicting Y (Reaction) when X (Drinks) is 4:
x0 = pd.DataFrame(dict(Drinks=[4]))
print('\nPrediction:\n', model.predict(x0))

# Alternative code to predict Y when X = 4:
#model.predict(exog=x0)

intervals = model.get_prediction(x0)
print('\nIntervals:\n', intervals.summary_frame())
```


### Confidence interval for the slope
interval around $b_1$ that quantifies the sampling uncertainty when $b_1$ is used to estimate $\beta_1$
#### $$[b_1 - t^*(SE), b_1 + t^*(SE)]$$
where $SE$ is the standard error, and $t^*$ depends on the degrees of freedom and confidence level of interest, can be found in the [[T-Table]]
