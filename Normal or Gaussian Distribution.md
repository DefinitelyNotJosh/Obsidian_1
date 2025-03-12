Continuous probability distribution, bell shaped probability function, symmetric around mean $\mu$. Pervasive because the distribution is a model for quantities that are computer as sums (totals) or average. Often data is summarized using either the total or average. Occurs in many settings

#### [[Central Limit Theorem (CLT)]]
#### [[Empirical Rule]]

| Models          | Averages, totals, many natural phenomenon such as measurement errors, test scores, body measurements.                                                        |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Notation        | X∼N⁡(μ,σ), read "X has a normal distribution with parameters μ and σ."  <br>The distribution N⁡(0,1) is known as the standard normal distribution Z∼N⁡(0,1). |
| Parameters      | μ: Mean of the distribution  <br>$\sigma$: Standard deviation of the distribution  <br>$\sigma^2$: Variance of the distribution                              |
| Possible values | All real numbers.                                                                                                                                            |

#### [[Z-Score]]
#### [[Z-Table]]


#### Ex. Problem
X is normally distributed with $\mu = 20$ and $\sigma=2$. determine the following:
1. P(X<18) = 0.158655
2. P(X>18) = 1 - P(18) = 0.841345
3. P(18<X<22) = P(22)-P(18) =  0.68269
4. repeat using python

```
import scipy.stats as st

sigma = 2
mean = 20
print(st.norm.cdf(18, mean, 2))
print(1-st.norm.cdf(18, mean, 2))
print(st.norm.cdf(22, mean, 2) - st.norm.cdf(18, mean, 2))
```

### Ex. Problem
1. Diameter of a shaft in a storage drive is normally distributed with a mean of 0.2508 inches and a std dev of 0.0005 inches. The specs on the shaft is 0.2500 +/- 0.0015 inches. What proportion of the shafts conform to specification?

Range in spec -> 0.2485-0.2515
Mean - 0.2508

Using Python, 0.91924122831152, or 91.9%
```
import scipy.stats as st

sigma = 0.0005
mean = 0.2508
print(st.norm.cdf(0.2515, mean, sigma) - st.norm.cdf(0.2485, mean, sigma))
```
Can also use [[Z-Score]] method
$$Z_{lower}=\frac{0.2485-0.2508}{0.0005}=-4.6,~~~~ Z_{higher}=\frac{0.2515-0.2508}{0.0005}=1.4$$

Ends up being: $$0.91924-0=0.91924$$
2. If the process is centered so the process mean is equal to the target value of 0.2500, what proportion of the shafts will conform to spec?
Follows [[Empirical Rule]], 99.7% will conform to spec


#### Related to [[Z-Confidence Intervals]]
