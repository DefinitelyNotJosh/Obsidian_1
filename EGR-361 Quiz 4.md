
### Problem 1
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


### Problem 2
Testing safety of cars during 35 mph frontal barrier impact test. Using new female crash test dummies and comparing them to legacy male version. Looking at head accelerometer readings, trying to tell if they are significantly greater than male version.
- Historical Male dummies - acceleration normally distributed, mean of 50 g, variance of 3 g.
- Female dummies - 4 samples, acceleration mean of 52 g, variance of 3 g. 
- $\alpha = 0.01$ (99% confidence specified)
- Right-tailed Type II error (fail to reject Hypothesis, in this case need value greater than hypothesis)
- $\sigma = \sqrt{3}$
A. Probability of making type II error with only 3 dummies:

First find z  corresponding to 0.01, $z_\alpha = 2.33$

	$$beta=\phi \left(z_{\alpha}-\frac{\delta\sqrt{n}}{\sigma} \right)-0$$
$$beta=\phi \left(2.33-\frac{(52 - 50) \sqrt{3}}{\sqrt{3}} \right)-0$$
$$\beta = \phi(0.33) = 0.6293$$
The probability of making a type II error with only 3 dummies is abou 0.63, or 63%.


B. What's the sample size needed to reduce the probability of making a type II error to 5% (hoping to find statistically significant difference to justify design changes to make your cars safer for female drivers)
$$n \approx \frac{(z_{\alpha}+z_\beta)^2\times\sigma^2}{\delta^2}$$
$z_\beta = 1.645$
$\sigma^2=3$
$$n \approx \frac{(2.33+1.645)^2\times 3}{(52-50)^2}=11.85 \approx12$$
The sample size should be at least 12 in order for there to be a statistically significant difference



### Problem 3
Designing new carbon dioxide filtration/processing system for industrial complex. Will collect/analyze gas levels in air from 5 different locations.
- First batch of samples yields proportion of 0.07% carbon dioxide in the air

What's the 90% confidence interval on true proportion of carbon dioxide in the air at the complex?

$$m = z^* \sqrt{\frac{\hat{p}(1 - \hat{p})}{n}}$$
90% confidence $z^*=1.645$

$$m = 1.645 \sqrt{\frac{0.0007(1 - 0.0007)}{5}}=0.0195$$
(0.0007 - 0.01945, 0.0007 + 0.01945)
Interval: (-0.01875, 0.02015)
Final interval:  (0, 0.0202) -> negative doesn't make sense

The 90% confidence interval is (0, 0.0202) or (0, 2.02%).