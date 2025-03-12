#### Input instances with many dimensions
- 10k, 100k, 10^6 dimensions
- Text data
#### Represent data with fewer dimensions
- Faster learning
- Faster generalization
- True dimensionality of data - intrinsic dimension
- Visualize

### [[Principle Component Analysis (PCA)]] (PCA)
- Minimization of the reconstruction error
- Find the best coordinate system
	- Dot product defines the least lossy lower dimension
	- Orthonormal basis
#### Advantages
- Reduce ML algo speed
- Reduce memory and storage requirements
- Aging feature set
- Visualization
- Smaller training sets
#### Disadvantages
- What if dropped dimensions contained critical info?
- Easily overfitting of the ML model

#### ICA
Independent Component Analysis

Separating a multivariate signal into additive subcomponents
Subcomponents are statistically independent
- Minimization of mutual info (entropy)
- Maximum of non-Gaussianity (max likelihood estimation)

### LDA
Linear Discriminant Analysis
A linear combination of features that characterizes or separates two or more classes of objects or events
![[Pasted image 20250220145250.png]]

#### t-SNE
t-distributed Stochastic Neighbor Embedding