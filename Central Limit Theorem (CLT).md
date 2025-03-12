Most situations don't involve parameters that are normally distributed.
The CLT means the distribution of sample means can be assumed to be approximately normal
CLT is the basis for assuming averages and totals follow the [[Normal or Gaussian Distribution]].

Example - when rolling one die, the distribution is uniform. When adding more dice, the result takes a normal distribution (eg, 7 is the center with 2 dice, as there are more ways to get 7 with 2 dice as there are ways to get 2)
#### CLT states that as the sample size drawn from the population with distribution $X$ becomes larger, the sampling distribution of the means $\overline{X}$ approaches that of a normal distribution $N\left(\mu,   \frac{\sigma}{\sqrt{n}}\right)$. Thus, the [[Z-Score]] is $$z = \displaystyle\frac{\bar{x} - \mu}{\frac{\sigma}{\sqrt{n}}}$$
#### Sample size at least 30, know population mean, know population std dev 
- Randomness assumption - samples must be randomly selected.
- Independence condition - sample values must be independent from each other.
- Sample size assumption - sample size must be large enough. A rule of thumb is that sample sizes should be at least 30.
- 10% condition - sample size must be at most 10% of the population size.


The Central Limit Theorem for proportions states that if $X∼B⁡(n,p)$ where n is the number of trials and p is the probability of success, then the sampling distribution for proportions p^ follows a normal distribution $N\left(p, \sqrt{\frac{p(1-p)}{n}}\right)$. Thus, the $z$-score is $$z = \displaystyle\frac{\hat{p} - p}{\sqrt{\frac{p(1-p)}{n}}}$$

Assumptions 4.10.2: Central Limit Theorem for proportions: Conditions.

- $np \geq 5$
- $n(1-p) \geq 5$ 