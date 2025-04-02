Occurs when 2+ predictors in multiple regression model are so highly correlated the estimated model becomes unstable (regression parameter estimates become unreliable with inflated standard errors)
- If perfect multicollinearity is present in a dataset, least squares method fails and software used to perform the regression will probably crash
If predictor variables are not perfectly multicollinear but still highly correlated but still highly correlated, estimates for corresponding regression parameters will be unreliable and sensitive to small changes in the model
- Severe multicollinearity makes regression coefficients less precise, results in misleading significance levels

Only effects regression parameters of the variables that are multicollinear. Parameters that aren't multicollinear in a dataset are still valid


#### Detecting multicollinearity
has many methods
#### Using [[Correlation and Coefficient of Determination]]
1. Do Correlation analysis, follow table with resulting R-Value
#### Using [[Coefficient of Multiple Determination]]
1. $R^2$ statistic calculated for each predictor var with respect to other predictor vars ($R^2$ calculated for each predictor var as if the predictor var were the response var)
2. $R^2 \geq 0.8$ generally indicates potential issues with multicollinearity, $R^2 \geq 0.9$ shows enough to cause severe problems
#### Using [[Variance Inflation Factor]]
- Higher VIF = greater problem
- 1 shows no multicollinearity
- greater than 4 or 5 = multicollinearity problems
- greater than 10 = serious issues


### Dealing with Multicollinearity
If multiple regression fit only being used to predict response variable from predictor variables, multicollinearity not an issue
- However, must be eliminated for any interpretation of regression coefficients (from [[Correlation and Coefficient of Determination]]) to be meaningful
Options:
- If data produced from experiment
	- change experiment to eliminate multicollinearity
	- Increase sample size
- Remove one of the multicollinear variables
- Linearly combine the multicollinear variables
