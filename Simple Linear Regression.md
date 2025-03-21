### [[Linear Regression]]
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


#### absolute error
regression params typically known because entire population not often observable
- instead, random sample is obtained
- Get estimates of $\beta_0/\beta_1$ from sample
