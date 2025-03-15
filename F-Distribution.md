#### In a sample w multiple groups taken from independent populations, variability can be partitioned into between-group variability and within-group variability. The F-statistic is the ratio of between-group variance to within-group variance

#### A right-skewed 

#### Quantities involved:
#### Sum of squares between groups (SSB): $$SSB =  \displaystyle\sum_{j = 1}^k n_j (\overline{X_j} - \overline{X})^2$$
where $n_j$ is the number of observations in the $j$th group, $k$ is the number of groups, $\overline{X}_j$ is the sample mean for the $j$th group, and $\overline{X}$ is the overall mean
#### Mean squares between groups (MSB): $$ MSB = \frac{\displaystyle\sum_{j = 1}^k n_j (\overline{X_j} - \overline{X})^2}{(k-1)}$$
where $k-1$ is the degrees of freedom $df_B$
#### Sum of squares within groups (SSW): $$SSW =  \displaystyle\sum_{ij} (X_{ij} - \overline{X_j}) ^2$$
where $X_ij$ is the $i$th observation in the $j$th group, and $\overline{X_j}$ is the sample mean for the $j$th group.
#### Mean squares within groups (MSW): $$MSW =  \displaystyle\frac{\displaystyle\sum_{ij} (X_{ij} - \overline{X_j}) ^2}{n-k}$$
where $n$ is the overall sample size and $n-k$ is the degrees of freedom $df_W$
### F-statistic: $$F = \frac{MSB}{MSW}$$
