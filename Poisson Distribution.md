Used for Continuous data - eg, number of pavement flaws in a length of roadway, number of traffic accidents during peak rush hour, number of hurricanes in a year
Gives the probability of $k$ independent, randomly occurring events happening over a period or area where $\lambda$ events happen on average. The constant $e=2.718...$ is Euler's constant. Formula for the distribution is: $$P(k)=e^{-\lambda}\frac{\lambda^k}{k!}$$ Usually used in situations where average count is low
- Differs from [[Binomial Distribution]] and hyper[[Geometric Distribution]] in that the right side of the distribution extends to infinity
	- Ex - when flipping a coin 20 times, probability of getting tails more than 20 times us exactly 0. However, when counting the number of raindrops falling in a bucket over a period of time, no theoretical upper limit exists. The probabilities for higher numbers become very small, but never exactly 0

#### Skewed to the right

#### Average: $$\mu = \lambda$$ Variance: $$\text{variance}=\sigma^2=\lambda$$ Standard deviation: $$\sigma=\sqrt{\lambda}$$ 
Poisson distribution can be used to test whether a set of events is random (hypothesis testing) or to generate random numbers


#### ICA
Number of earthquake tremors in a 12-month period appears to be distributed as a Poisson random variable with a mean of 6 tremors per 12 month period. Assume events are independent.
1. Probability of 10 tremors in a year? - 0.0413, 4.13%
2. Probability of 18 tremors in 2 years? - 0.02555, 2.555%
3. Probability of 0 tremors in a month - 0.60653, 60.653%
4. Probability of more than 5 tremors in a 6 month period? - 0.08392, 8.392%
5. Determine the mean and variance - mean = 6, variance = 6
6. Plot the [[Probability Density Function (PDF) (Continuous)]]
7. Plot the [[Cumulative Distribution Function (CDF) (Continuous)]]

