#### Advantages
- Reduce ML algo speed
- Reduce memory and storage requirements
- Aging feature set
- Visualization
- Smaller training sets
#### Disadvantages
- What if dropped dimensions contained critical info?
- Easily overfitting of the ML model

Python module for importing PCA is `from sklearn.decomposition import PCA`  which can be used as ` pca = PCA(n_components=0.95)`, where `n_components` specifies the number of components to keep. - The result is a new dataset with reduced dimensionality.
- Example code for applying PCA to a sample dataset:
```python
from sklearn.datasets import load_iris
iris = load_iris()
pca = PCA(n_components=0.95)
pca_iris = pca.fit_transform(iris.data)
```
Tips for selecting `n_components` - Use the `explained_variance_ratio_` attribute to determine the number of components that capture a certain percentage of variance.
- Set a threshold (e.g., 0.95) for cumulative explained variance.
- Plot the explained variance ratio to visually select the number of components. - Use a scree plot to determine the elbow point for optimal component selection. - Consider using cross-validation to evaluate the performance of PCA with different `n_components` values. 


