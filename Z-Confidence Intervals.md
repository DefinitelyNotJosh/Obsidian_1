Although population mean is usually unknown, the interval that quantifies the range within the true population mean lies can be calculated by the sampling population.
- ex -a 95% confidence interval means that the interval calculated has a 95% probability of containing the population mean. If the population is sampled 20 times, 19 of the 20 calculated intervals are expected to contain the pop. mean
#### $$\left[\bar{x} - z^*\frac{\sigma}{\sqrt{n}},\bar{x} + z^*\frac{\sigma}{\sqrt{n}}\right]$$

### Significance level
Area under curve outside of confidence interval

### Critical values for common confidence levels:
| Confidence level | Critical value |
| ---------------- | -------------- |
| c=0.90           | $z^*$=1.645    |
| c=0.95           | $z^*$=1.960    |
| c=0.99           | $z^*$=2.576    |

##### Margin of error $m$ for the population mean is equal to: $$z^*\frac{\sigma}{\sqrt{n}}$$

For python: norm.interval() used to find confidence interval for a normally distributed value

#### Margin of error and sample size for means when $\sigma$ is known
The width of the confidence interval is twice the margin of error. The size of the sample needed to guarantee a confidence interval with a specified margin of error is:
#### $$n = \left(\displaystyle\frac{z^* \sigma}{m}\right)^2$$
Rounded up to the nearest whole number

