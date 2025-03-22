### [[Linear Regression]]
### [[Correlation and Coefficient of Determination]]
### [[Interpreting Simple Linear Regression]]
### [[Confidence Intervals for Simple Linear Regression]]
### [[Testing Simple Linear Regression (SLR) parameters]]

Way to model linear relationship between two quantitative variables using a regression line

ex - house prices, relate square footage to cost



#### response variable
variable being modeled or predicted
- dependent variable, outcome, output
#### predictor variable
variables used to predict the response
- independent variable, input, covariate

#### Simple regression function = $E(Y) = \beta_0 + \beta_1X$ where $\beta_0/\beta_1$ are regression params
- Above the line - Y > E(Y)
- Below the line - Y < E(Y)
- On the line - Y + E(Y)
#### Model: $Y=\beta_0+\beta_1X+\epsilon$ where $\epsilon$ is the error term $$\epsilon=Y-E(Y)$$
$\epsilon$ is a statistical error modeled as a [[Continuous Random Variable]] with a normal distribution that has zero mean and constant variance
Regression error is:
- Positive for points above regression line
- Negative for points below regression line
- Zero for points on regression line


regression params typically known because entire population not often observable
- instead, random sample is obtained
- Get estimates of $\beta_0/\beta_1$ from sample
#### absolute error
method to measure how far line is from points - sum of absolute error of points


#### sum of squared errors
another measurement of how far the line is from the points
- sum of the squared differences of the Y values of the data points and the values from the regression line
-
#### least squares method
another measurement, minimizes sum of squared errors. 
- For sample with $n$ observations, sum of squared error is $$\sum_{i=1}^n(Y_i-\beta_0-\beta_1X_i)^2$$
#### sample linear regression function is $\hat{Y} = b_0+b_1X$ 
where $\hat{Y}$ are the predicted or fitted response values based on the linear regression model, $b_0/b_1$ are values of $\beta_0 /\beta_1$ that minimize sum of squared errors

#### simple linear regression fitted value, $\hat{Y}_i = b_0 + b_1 X_i$
is the predicted value of Y for the i'th sample value of X based on the sample regression line

#### simple linear regression residual, $\varepsilon_i = Y_i - \hat{Y}_i$
the i'th estimated regression error based on sample simple linear regression line

### Assumptions:
at each value of the predictor, X, probability distribution of the regression error, $\varepsilon = Y - \mathrm{E}(Y) = Y -  \beta_0 - \beta_1 X$:
- Has a mean of zero
- has equal variance
- is normal
Value of $\epsilon$ for one observation is independent of $\epsilon$ every other observation
Should generally only be used if reasonable chance exists that the assumptions hold

#### mean of zero assumption
a "rising/falling" pattern or any strong linear trend indicates that the mean of zero assumption doesn't hold

LEFT- mean of zero holds    RIGHT - mean of zero does not hold
![[Pasted image 20250321102645.png]]

#### constant variance assumption
"funnel" pattern indicates variance does not hold

LEFT- constant variance holds    RIGHT - constant variance does not hold
![[Pasted image 20250321102927.png]]

#### normality assumption
If plotted points lie reasonably close to diagonal line, conclude that the "normality" assumption holds

LEFT- normality holds    RIGHT - normality does not hold
![[Pasted image 20250321103021.png]]

#### independence assumption
Arises through poor study design

LEFT- independence holds    RIGHT - independence does not hold
![[Pasted image 20250321103359.png]]



### Python
The intercept parameter estimator b0 and the slope parameter estimator b1 can be obtained by using the `linregress(x,y)` function, which takes in two arrays of equal length as input and returns b0, b1, the correlation coefficient r, the p-value for the correlation coefficient t-test, and the corresponding standard error. The `linregress(x,y)` function uses the scipy.stats library.

To find the predicted value given X=3, the code below can be used.
```python
import numpy as np
import scipy.stats as st

x = np.array([0, 3, 7, 10])
y = np.array([5, 5, 27, 31])

model = st.linregress(x,y)

print(model)

print("Predicted value for X=3:",np.dot([3, 1],[model[0], model[1]]))
```
