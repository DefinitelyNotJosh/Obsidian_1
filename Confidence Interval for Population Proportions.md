#### Suppose sample proportion $\hat{p}$ and the number of samples $n$ are known from the sampling population. The margin of error $m$ is then given by: $$m = z^* \sqrt{\frac{\hat{p}(1 - \hat{p})}{n}}$$ Where $z^*$ is the critical value corresponding to the desired confidence level $c$. The confidence interval for the population proportion $p$ is given by: $$[ \hat{p} - m, \hat{p} + m ]$$
Reminder:

### z-score: $$z=\frac{\hat{p}-p}{\sqrt{\frac{p(1-p)}{n}}}$$ where $p$ is the historical proportion, $\hat{p}$ is the sample proportion, $n$ is the sample size. Ok to use the Z-score if $np \geq 5$ and $n(1-p) \geq 5$ (tells us if sample is big enough to assume normal distribution)


#### Ways to identify:
Ratio, part of whole, Fraction, %

Can go back to the [[Z-Table]]


| Confidence level | Critical value | margin or error $(\frac{1-c}{2})$ |
| :--------------: | :------------: | :-------------------------------: |
|      c=0.90      |  $z^*$=1.645   |               0.05                |
|      c=0.95      |  $z^*$=1.960   |               0.025               |
|      c=0.99      |  $z^*$=2.576   |               0.005               |

norm.interval() is used to find the confidence interval for population proportion

#### Margin of error and sample size proportions
### The sample size needed to guarantee a confidence interval within a specified margin of error is: $$n = \left(\frac{z^*}{m} \right)^2 p(1- p)$$ where $z^*$ is the critical value at a specified confidence level, $p$ is the proportion, and $m$ is the margin of error (in the table, e.g. 0.05, 0.005). Round up to nearest whole number



#### However, $p$ depends on $n$. Two options:
- Use population $p$ or preliminary $p$ from a previous study/sample
- Worst case scenario with $p=0.50$ can be used, so largest sample size needed will be used to satisfy the required margin of error at a specified confidence level



### Example problem

-1.94665

[[Z-Table]]

0.02558

2.56% that we'll continue to have probabilities less than 2% exceeding the limit


#### Example 2
Have 1000 samples of resistors
In sample, 2% were defective
Independent/random samples

1) Find 90% confidence interval
m = 0.0073
\[0.02- 0.0073, 0.02 + 0.0073]
\[1.27%, 2.73%]
2) Find sample size needed for a 95% normal confidence level
$n$ equation, $z^*=1.96$ and $m=0.025$
1537 samples needed for a 95% normal confidence level at p = 0.5
121 samples needed for a 95% normal confidence level at p = 0.02