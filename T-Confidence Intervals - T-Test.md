
#### [[Confidence Intervals]] for a population mean using the [[T-Distribution - T-Test]] is defined as: $$\left[\bar{x} - t^* \displaystyle\frac{s}{\sqrt{n}}, \bar{x} + t^* \displaystyle\frac{s}{\sqrt{n}}\right]$$ Where $t^*$ is the critical value that depends on the degrees of freedom and significance level

Remember - t-statistic is $$t=\frac{\overline{x}-\mu}{\frac{s}{\sqrt{n}}}$$ where $\mu$ is the population mean, $\overline{x}$ is the sample mean, $s$ is the sample standard deviation, $n$ is the sample size
### Critical values $t^*$ for selected degrees of freedom $df$ and significance level $\alpha$:
Remember: degrees of freedom is the sample size - 1

#### [[T-Table]]

|         | $\alpha = 0.1$ (90%) | $\alpha = 0.05$ (95%) | $\alpha = 0.01$ (99%) |
| ------- | -------------------- | --------------------- | --------------------- |
| $df=5$  | 2.015                | 2.571                 | 4.032                 |
| $df=10$ | 1.812                | 2.228                 | 3.169                 |
| $df=15$ | 1.753                | 2.131                 | 2.947                 |
| $df=24$ | 1.711                | 2.064                 | 2.797                 |
| $df=32$ | 1.694                | 2.037                 | 2.738                 |


![](https://zytools.zybooks.com/zyAuthor/AppliedStatisticswithDataAnalytics/14/IMAGES/e60e8bc4-5422-0142-cc85-a9c6e49cbc54)  

#### Margin of error is: $$m=t^*\frac{s}{\sqrt{n}}$$ where $s$ is the standard deviation and $n$ is the sample size

t.interval() function in python to find a confidence interval with a t-distribution

#### Margin of error and sample size when $\sigma$ is unknown
For a situation with an unknown population and standard deviation, the sample standard deviation should be used. Thus: 
#### $$n = \left( \dfrac{t^*s}{m} \right)^2$$ where $t^*$ is the critical value at a specified confidence interval, $s$ is the sample standard deviation based on a preliminary study, and $m$ is the margin of error. Round up to nearest whole number sample size

#### However, $t^*$ depends on the degrees of freedom $n-1$, which is also in terms of $n$. To find $t^*$, $z^*$ ([[Z-Confidence Intervals]]) is used to find the preliminary sample size $n^*$: $$n^* = \left(\dfrac{z^* s}{m} \right)^2$$ 

Example problem
99% confidence on pop mean
 what is 

sample mean: 8.28
sample variance: 0.007
sample std dev = 0.0837

1. What is the 99% confidence interval on the pop. mean?
   $$\left[8.205,8.355\right]$$
2. How does the confidence interval change if the population variance is 0.005? ([[Z-Confidence Intervals]]) 
   $$\left[8.227,8.333\right]$$

