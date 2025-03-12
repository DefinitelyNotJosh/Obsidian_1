scipy.stats.expon module for python

Gives probability of a [[Continuous Random Variable]] $k$ which represents the physical distance, area, volume, time, etc. occurring between successive events of a Poisson process with $\lambda > 0$. 
#### Formula for distribution: $$P(k)=\lambda e^{-\lambda k}, \text{ for } 0 \leq k < \infty$$
#### Mean or expected value of $K$: $$\mu=E(K)=\frac{1}{\lambda}$$
#### Variance of $K$: $$\sigma^2=V(K)=\frac{1}{\lambda^2}$$
### The [[Cumulative Distribution Function (CDF) (Continuous)]]: $$P(a \leq k\leq b)=\int^{b}_{a}\lambda e^{-\lambda x}dx=e^{\lambda a}-e^{-\lambda b}$$
#### DON'T FORGET - PROBABILITY OF AN EXACT VALUE IN [[Continuous Distribution]] is 0!!!!

Often used in reliability studies as the model for the time until spontaneous failure of a device. Because exponential distribution has a **lack of memory property**, the time until spontaneous failure is not describing deterioration due to hardware wearing out over time, but the occurrence of some random failure state like an electric shock that causes a malfunction.

Example of Lack of Memory property:
Probability of an event occurring in the next 2 hours is 47%. 90 minutes have passed. Probability of an event occurring in the next two hours? 47%.

Failure due to wear is better modeled with distribution that has a memory property, like [[Weibull Distribution]], but it won't be covered in EGR-361.


### [[Cumulative Probability]]

![[Pasted image 20250207121047.png]]


### ICA:
Time between arrival of email messages at your computer is exponentially distributed with a mean of 2 hours
1. probability that you do not receive a message during the first 2 hour period? $$\frac{1}{2}e^{-\frac{1}{2}*0}=1/2$$
2. 