[[7-Step Method]]
[[Z-Test]]
[[T-Test]]


Question: Want to test a manufacturer's claim that their phone runs at least 28 hours

Null Hypothesis: The phone runs at least 28 hours a day

Alternative Hypothesis: the phone runs more than 28 hours a day (right tailed)


Question: Drug manuf. wants to determine if a new drug decreases blood pressure

Null Hypothesis: The average blood pressure doesn't change whether they take the drug or not

Alternative Hypothesis: Average blood pressure decreases (left-tailed)


 Test Statistic: t-statistic
 $t = \displaystyle\frac{\bar{x}-\mu_0}{\frac{s}{\sqrt{n}}}$ and $df = n - 1$
 
 Calculate the p-value using t-table


### Z-Test example
Benzene is a toxic chemical. A manufacturer claims that its wastewater meets the federal regulation w a mean concentration of 7980 ppm. 10 Random samples collected and are found to have an average of 7906 ppm. Assume the benzene concentration in plant wastewater have been normally distributed with a standard deviation of 80 ppm. Use a significance level of 0.01

std dev - 80 ppm
n = 10
sample mean = 7980
$\mu$ = 7906
alpha = 0.01

1. Parameter of interest - mean concentration of benzene
2. Null hypothesis: Wastewater benzene is 7980 ppm
3. Alternative hypothesis: benzene < 7980 ppm
4. test statistic: z test (sample is less than 30, but normally distributed)
5. Reject $H_0$ - will be rejected if p-value is less than 0.01
6. Computation
#### $z = \frac{\bar{x}-\mu_0}{\frac{\sigma}{\sqrt{n}}}$
 where $\bar{x}$ is the sample mean, $\mu_0$ is the hypothesized population mean, $\sigma$ is the population standard deviation, and $n$ is the sample size 
##### $z = \frac{7906 - 7980}{\frac{80}{\sqrt{10}}}$
$z = \frac{-74}{25.298}$
$z = -2.93$
Get p-value from [[Z-Table]]
p ~ 0.0017

7. Conclusion: p is less than 0.01, reject the null hypothesis. The benzene concentration does indeed meet the federal regulation


### T-Test example
A machine produces metal rods used in automobiles, a random sample of 12 rods is selected and diameters measured in mm:
8.23, 8.29, 8.19, 8.14, 8.31, 8.19, 8.29, 8.32, 8.42, 8.24, 8.3, 8.4

1. Describe why t-test is required for this hypothesis
No population standard deviation given
Sample size is under 30 and the population isn't said to be normally distributed

2. Is there strong evidence to indicate that the mean rod diameter is not 8.2 mm with $\alpha$ = 0.05

//
1. Parameter of interest - mean rod diameter
2. Null hypoth. - The mean rod diameter is 8.20mm
3. Alternative hypoth. - The mean rod diameter $\neq$ 8.20mm
4. Test statistic - t-score
#### $t = \displaystyle\frac{\bar{x}-\mu_0}{\frac{s}{\sqrt{n}}}$ and $df = n - 1$
5. $H_0$ will be rejected if 2\*p-value is less than 0.05
6. Computation
#### $t = \displaystyle\frac{8.28-8.2}{\frac{0.08}{\sqrt{12}}}$ and $df = 12 - 1=11$ $$t=3.177$$ p-value = $0.088$, 2* 0.0088 = 0.0176
7. Conclusion - 0.0176 < 0.05, sufficient evidence to reject null hypothesis, mean rod diameter is not 8.20mm
