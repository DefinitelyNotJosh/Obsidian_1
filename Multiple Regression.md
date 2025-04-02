Way to model the linear relationship between:
- **one** quantitative response variable and 
- **multiple** predictor variables

#### response variable
the variable being modeled or predicted
#### predictor variables
variables used to predict response


##### Own dataset has many X's that will be used to build [[Machine Learning]] model

### [[Coefficient of Multiple Determination]]
### [[Interpreting Multiple Regression Models]]


#### Multiple regression model has 2 parts:
1. Population linear regression function - represents expected value of Y for a given set of values for $X_1, X_2, ...X_n$. Function is: $$\mathrm{E}(Y) = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \ldots + \beta_n X_n$$ where $\beta_0, \beta_1, \beta_2, \ldots, \beta_n$ are regression parameters
2. Regression error term $\epsilon$ - represents difference between actual value of $Y$ and the expected value of $Y$ given a particular set of values for $X_1, X_2, ... X_n$ 
### The model is: $$Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \cdots + \beta_n X_n +  \epsilon$$
which is the sum of the pop. regression function and the regression error term

#### Once a population model is proposed, the next step is to estimate the model using sample data to find 

### Sample multiple regression function: $$\hat{Y} = b_0 + b_1 X_1 + b_2 X_2 + \ldots + b_n X_n$$
Where $\hat{Y}$ is the fitted response value and $b_1,b_2,...b_n$ are the estimates for $\beta_0, \beta_1, \ldots, \beta_n$


### Python - multiple regression
The multiple regression model for the body fat example above is constructed using the code below.
```python
import pandas as pd
import statsmodels.formula.api as sms

fat = pd.read_csv('fat.csv')

# Response variable
Y = fat['body_fat_percent']

# Generates the linear regression model
# Multiple predictor variables are joined with +
model = sms.ols('Y ~ triceps_skinfold_thickness_mm + midarm_circumference_cm + thigh_circumference_cm', data = fat).fit()

# Prints the summary
print(model.summary())
```


### Fitted Values and Residuals
#### multiple regression fitted value: $$\hat{Y}_i = b_0 + b_1 X_{1i} + b_2 X_{2i} + b_3 X_{3i} + \cdots + b_n X_{ni}$$
predicted value of $Y$ for the $i$'th sample value of $X_1,X_2,X_3...$ based on the sample regression function
#### multiple regression residual - $$e_i=Y_i-\hat{Y}_i$$
is the $i$'th estimated regression error base don the sample multiple regression function

### Python - multiple regression residuals
```python
import pandas as pd
import statsmodels.formula.api as sms

fat = pd.read_csv('https://static-resources.zybooks.com/fat.csv')

# Response variable
Y = fat['body_fat_percent']

# Generates the linear regression model
# Multiple predictor variables are joined with +
model = sms.ols( 'Y ~ triceps_skinfold_thickness_mm + midarm_circumference_cm + thigh_circumference_cm', data = fat ).fit()

# Prints a list of the fitted values for each sample
print(model.fittedvalues)

# Prints a list of the residuals for each sample
print(model.resid)
```

#### Multiple regression assumptions
Considered valid only if the following assumptions can be made of the population. The sample residuals are used to determine whether each assumption is violated
- Mean of zero: The mean of each residual for each set of values for the predictor variables is zero. Equivalently, this assumption says that the response variable is a linear function of each of the predictor variables.
- Independence: The residuals are independent. This condition can be difficult to assess. A common way to determine independence is by plotting residuals with respect to the time in which the data is collected. If a trend exists, then the independence assumption is potentially violated.
- Normality: The residuals of each set of values for the predictor variables form a normal distribution. If the plotted points lie reasonably close to the diagonal line on the plot then one can conclude that the normality assumption holds.
- Constant variance: The residuals of each set of values for the predictor variables should have equal or similar variance. A common term for this condition is _homoscedasticity_. If the variance does not remain constant throughout the plot, then the model exhibits _heteroscedasticity_.

#### Examples - $Y =$ percentage body fat using predictor variables $X_1=$ triceps skinfold thickness, $X_2=$ midarm circumference, $X_3=$ thigh circumference. 
Sample size of 20 smaller than typically used, but used for illustration

A residual plot with a non-linear shape suggest violation of the linearity assumption

Nonlinear dataset - left                                         no evidence of nonlinearity - right
![[Pasted image 20250329141249.png]]

Residual plot with a fan-shaped distribution suggest some data points have a smaller variance than others. Variance not constant suggest violation of homoscedasticity

Heteroscedastic dataset (left)                                      Homoscedastic (right)
![[Pasted image 20250329141428.png]]

Q-Q used to visually evaluate assumption of normality - plot that deviates from diagonal line suggest violation of normality

non-normally distributed (left)                                      Normally distributed (right)
![[Pasted image 20250329141725.png]]

##### Remember:
- Assessing is subjective - question an assumption when a clear non-random pattern exists, don't be concerned w weak patterns
- Graphically checking requires sample size $\geq 30$
- All 4 assumption should hold for validity
- Multiple regression models reasonable robust to mild violations of the assumptions
- Severe violations can be addressed through complex models

#### Issues w multiple regression
Individual data observations can have a strong influence on multiple regression models
- Outlier - observations Y value either much larger/smaller than predicted by model
- High leverage observation - observation in multiple regression analysis that has an extreme combination of predictor values. Could be particularly high or low. High leverage observation has potential to be highly influential on the results of the MRA
- [[Multicollinearity]] - Occurs when 2+ predictors in multiple regression model are so highly correlated the estimated model becomes unstable (regression parameter estimates become unreliable with inflated standard errors)

