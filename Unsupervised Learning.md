### No labels!
#### Measuring distance between instances is a key
#### Grouping of unlabeled instances into clusters 



## Clustering


![[Pasted image 20250311145307.png]]
#### Not intuitive
#### Not stable (different clusters each time you run algo)
#### Not perfect information


Not obvious on how to:
- Measure distance 
	- Recall structural kernels for drug design
- How many clusters
- Where are the centers
- Online learning - initial clusters, new cluster discovery
- Soft vs hard clustering
	- Cluster membership based on a weight


#### k-means $$\sum^{k}_{i=1}\sum_{j\in C_i}||x_j-c_i||^2$$ $$\text{where }c_i=\frac{1}{|C_i|}\sum_{j \in C_i}x_j$$

### k-means clustering
1. Select k random instances as centroids
do:
	2. assign instance to closes centroid: $$min_d\forall k : d(x-c_k)$$
	3. Calculate new centroids in clusters $c_k^`$
	4. Update old centroids to new one $$c_k=c^`_k$$
while many changes to $c_k$


#### k-means disadvantages
Outlayers
Concave instance grouping
Initial centroid selection
Density defined cluster noisy data
#### Other issues:
- Mean is undefined, can't calculate
- Distance measure undefined - can't calculate
- Unequal cluster sizes/densities
- Empty clusters
- Non-spherical shapes
#### Fixes:
Label data (Categorical)
- FIX: choose most common value

Empty clusters:
- FIX: re-sample centroids at random or split cluster w highest variance

Right selection of k - hard to fix
- FIX: k-fold cross-validation parameter tuning
- FIX: choose elbow (if a clear choice)

Non-termination by cycling centroids
- FIX: force stop by attenuation

Alternative distance measure:
Cosine similarity (what LLMs do to find difference between similar vectors)

Minimize centroid coherence AND maximize cluster separation