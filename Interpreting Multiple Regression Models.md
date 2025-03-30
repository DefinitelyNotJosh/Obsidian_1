### $\hat{Y} = b_0 + b_1 X_1 + b_2 X_2 + \ldots + b_n X_n$
- $b_0$ = Y-intercept of sample [[Multiple Regression]] function which is the fitted value of Y when $X_1=X_2=\ldots = X_n =0$
- $b_1, b_2, \ldots, b_n$ = slope in respect to particular predictor variable
##### $b_0$ has practical meaning when $X_1=X_2=\ldots = X_n =0$  are meaningful values and samples exist at/near the Y-intercept
##### $b_1, b_2, \ldots, b_n$ always has a practical meaning


#### Interpreting residual standard error
Like [[Simple Linear Regression (SLR)]], several quantities use residuals $\epsilon_i = Y_i - \hat{Y}_i$
- SSR, SSE, SSTO

Magnitude of residuals indicate strength of a model - closer they are to 0, more effective model is in predicting dependent var
RMSE at times more useful because residuals can be positive or negative
#### $$RMSE = \sqrt{MSE} = \sqrt{\dfrac{SSE}{N-p}}$$
where $N$ is the sample size and $p=n+1$ is the number of regression parameters

#### [[ANOVA F-Test]]
- RMSE is standard deviation of the residuals $$\sqrt{  \frac{\text{Residual sum\_sq}}{\text{Residual df}}  }$$
