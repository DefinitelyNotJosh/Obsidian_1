#### Probability expressed by the likelihood that one of two outcomes occur
- Success -> what we are looking for, not necessarily good

Requirements:
1. Number of successes in an interval 
2. Interval type: discrete

[

discrete random variable distribution with two possible values that have fixed probabilities that add up to 1. [[Probability mass function (PMF) (Discrete)]] is: $$P(k) = C_{n,k}p^k(1-p)^{n-k}$$
where $n$ is the number of trials, $k$ is the number of successes, and $p$ is the probability of success for each trial
reminder:  $$C_{n,k}=\binom{n}{k}=\frac{n!}{k!(n-k)!}$$
Also:  $$P(X \leq k) = \sum^{n}_{x=k}\binom{n}{k}p^k(1-p)^{n-k}$$


The mean of one trial is $\mu=0(1-p)+1(p)=p$. The mean of the distribution over $n$ trials is the sum of the individual means, and is therefore $$\mu = np$$
Similarly, the variance of one trial is $$p(1-p)$$ and the variance of the distribution is $$\sigma^2=np(1-p).$$ The standard deviation of the binomial distribution is $$\sigma^2=\sqrt{np(1-p)}$$



ICA
Random  variable X has a binomial distribution with n = 10, p = 0.1. Determine the probabilities:
a) $P(K=5)$ = 0.001488
b) $P(K \leq 2)$ = 0.9298
c) $P(K>9)$ = 0.0000000001
d) $P(3 \leq K < 5)$ = 0.068555889



ICA
1. 0.0167, ~1.7%
2. 0.616, ~61.6%