Want to show that electric vehicle model is statistically faster than prior model
- prior model 0-60: 2.7s
- current model 0-60: 2.6s
7 cars produced (sample size)
Current sample standard dev of 0.09 seconds
Can we claim statistical improvement?
$\alpha=0.05$

Must use T-Test, population standard deviation isn't given and sample size is under 30

1. Parameter of interest: Average 0-60 mph
2. Null Hypothesis: average 0-60 mph is 2.7s
3. Alternative hypothesis: 0-60 mph is < 2.7s
4. Test statistic: t-score
#### $t = \displaystyle\frac{\bar{x}-\mu_0}{\frac{s}{\sqrt{n}}}$ and $df = n - 1$
5. $H_0$ will be rejected if p-value is less than 0.05
6. Computation:
#### $t = \displaystyle\frac{2.7-2.6}{\frac{0.09}{\sqrt{7}}}$ and $df = 7 - 1=6$ $$t=2.9397$$ p-value $\approx 0.01$ (from t-table)
7. Conclusion: P-value of 0.01 is greater than 0.05. Thus, you cannot make the claim that statistically there is an improvement in 0-60 time in the current model.


