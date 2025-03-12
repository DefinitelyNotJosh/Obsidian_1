Extension of [[Exponential Distribution]]
Because $K$ is a continuous random variable, we integrate $P(k)$ over the valid bounds $a$ and $b$ to find the probability that $k$ is between $a$ and $b$: 
#### $$P(a\leq k\leq b) = \int^{b}_{a}\lambda e^{-\lambda x}dx$$
This means that the probability that $k$ is exactly equal to some value $n$ will always be zero:
#### $$P(k=n)=P(n\leq k \leq n)=\int^{b}_{a}\lambda e^{-\lambda x}dx=0$$
#### The equation, with bounds, ends up being: $$\int^{b}_{a}\lambda e^{-\lambda x}dx=-e^{-\lambda x}|^{b}_{a}=e^{\lambda a}-e^{-\lambda b}$$
#### don't forget $e^0=1$ and $e^{- \infty}=0$ 
