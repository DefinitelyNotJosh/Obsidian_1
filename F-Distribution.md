#### In a sample w multiple groups taken from independent populations, variability can be partitioned into between-group variability and within-group variability. The F-statistic is the ratio of between-group variance to within-group variance

#### A right-skewed distribution
he F-distribution is a right-skewed distribution, as shown in the figure below. The F-distribution has two parameters: the degrees of freedom between samples $df_B$ and the degrees of freedom within samples $df_W$.
![[Pasted image 20250315113419.png]]
#### Quantities involved:
#### Sum of squares between groups (SSB): $$SSB =  \displaystyle\sum_{j = 1}^k n_j (\overline{X_j} - \overline{X})^2$$
where $n_j$ is the number of observations in the $j$th group, $k$ is the number of groups, $\overline{X}_j$ is the sample mean for the $j$th group, and $\overline{X}$ is the overall mean
#### Mean squares between groups (MSB): $$ MSB = \frac{\displaystyle\sum_{j = 1}^k n_j (\overline{X_j} - \overline{X})^2}{(k-1)}$$
where $k-1$ is the degrees of freedom $df_B$
#### Sum of squares within groups (SSW): $$SSW =  \displaystyle\sum_{ij} (X_{ij} - \overline{X_j}) ^2$$
where $X_ij$ is the $i$th observation in the $j$th group, and $\overline{X_j}$ is the sample mean for the $j$th group.
#### Mean squares within groups (MSW): $$MSW =  \displaystyle\frac{\displaystyle\sum_{ij} (X_{ij} - \overline{X_j}) ^2}{n-k}$$
where $n$ is the overall sample size and $n-k$ is the degrees of freedom $df_W$
### [[ANOVA F-Test]] F-statistic $$F = \frac{MSB}{MSW}$$

### Python code:

```python
import scipy.stats as st

# For an F-distribution, if the degrees of freedom between samples is 2
# and the degrees of freedom within samples is 5, what is P(F < 2)?
print(st.f.cdf(2, 2, 5))

# f.sf(f, dfb, dfw) returns the probability of  being greater than a critical value f for an -distribution with  equal to dfb and  equal to dfw.
# For an F-distribution, if the degrees of freedom between samples is 2
# and the degrees of freedom within samples is 5, what is P(F > 3.5)?
print(st.f.sf(3.5, 2, 5))

# To find the probability between two critical values, the difference between the two probabilities is calculated.
# For an F-distribution, if the degrees of freedom between samples is 2
# and the degrees of freedom within samples is 5, what is P(2 < F < 3)?
print(st.f.cdf(3, 2, 5) - st.f.cdf(2, 2, 5))
```