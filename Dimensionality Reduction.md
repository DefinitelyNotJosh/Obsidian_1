
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
 #### Advantages
- Separating sources of information
- Noise reduction
- Feature extraction
#### Disadvantages
- Sensitive to noise
- Requires many samples
#### Autoencoders
- Neural network architecture
- Encode data into lower dimensions
- Decode back to original dimensions
- Reconstruction error minimization
implementation:
```python
import tensorflow as tf

# Define autoencoder model
model = tf.keras.models.Sequential([
    tf.keras.layers.Dense(128, activation='relu', input_shape=(input_dim,)),
    tf.keras.layers.Dense(32, activation='relu'),
    tf.keras.layers.Dense(input_dim, activation='sigmoid')
])
```
### LDA
Linear Discriminant Analysis
A linear combination of features that characterizes or separates two or more classes of objects or events
![[Pasted image 20250220145250.png]]

#### t-SNE
t-distributed Stochastic Neighbor Embedding 
 Non-linear dimensionality reduction
- Good for visualization
- Sensitive to parameter tuning
