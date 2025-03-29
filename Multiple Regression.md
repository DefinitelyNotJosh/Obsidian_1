Way to model the linear relationship between **one** quantitative response variable and **multiple** predictor variables

#### response variable
the variable being modeled or predicted
#### predictor variables
variables used to predict response

#### Multiple regression model has 2 parts:
1. Population linear regression function - represents expected value of Y for a given set of values for $X_1, X_2, ...X_n$. Function is: $$\mathrm{E}(Y) = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \ldots + \beta_n X_n$$ where $\beta_0, \beta_1, \beta_2, \ldots, \beta_n$ are regression parameters
2. Regression error term $\epsilon$ - represents difference between actual value of $Y$ and the expected value of $Y$ given a particular set of values for $X_1, X_2, ... X_n$ 
### The model is: $$Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \cdots + \beta_n X_n +  \epsilon$$
which is the sum of the pop. regression function and the regression error term

#### Once a population model is proposed, the next step is to estimate the model using sample data to find 

### Sample multiple regression function: $$\hat{Y} = b_0 + b_1 X_1 + b_2 X_2 + \ldots + b_n X_n$$
Where $\hat{Y}$