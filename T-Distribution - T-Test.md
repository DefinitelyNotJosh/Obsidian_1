Also known as Student's t-distribution

The [[Central Limit Theorem (CLT)]] is a useful tool to calculate probabilities associated with non-normal distributions assuming sample sizes are large enough. In practice, getting a large enough sample isn't possible or the standard deviation of the population is unknown. In both cases, the sample standard deviation divided by the square root of the sample size can be used in place of the population standard deviation. 
##### The Student's t-distribution or t-distribution is used in place of the normal distribution in situations where the sample size is too small or the population standard deviation is unknown. The t-distribution has one parameter, degrees of freedom or $d⁢f$, which is equal to $n−1$. As the sample size $n$ (and consequently $d⁢f$) increases, the t-distribution approaches the normal distribution with a mean of $0$ and standard deviation of $1$. 

- A t-distribution has the same shape as the normal distribution, but has a wider spread because of the slightly larger standard deviation

#### t-statistic
obtained from a sample assumed to have a t-distribution and involves the population mean and a larger variability from estimating the population standard deviation. The formula is 
#### $$t=\frac{\overline{x}-\mu}{\frac{s}{\sqrt{n}}}$$where $\overline{x}$ is the sample mean, $\mu$ is the population mean $s$ is the sample standard deviation, and $n$ is the sample size

### Use the t-test when you have the population mean but don't have the standard deviation

#### [[T-Confidence Intervals - T-Test]]



### T-Test example
Given:
s = 25 MPa
$\overline{x}$ = 1470 MPa
n = 7
$\mu$ = 1500 MPa
 
#### $$*t=\frac{1470-1500}{\frac{25}{\sqrt{7}}}=-3.175$$ $df$ = 7 - 1 = 6
See [[T-Table]]

#### $P(\overline{x} < t)= 0.01 <-> 0.005$, 99%-99.5% chance that the tensile strength is under 1500 MPa
