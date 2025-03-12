Recall [[Linear Regression]]
- Multivariable linear regression 
	- If a pair of independent variables is mutually correlated, do not include it as a predictor of a dependent variable 
	- WHY?
- That said, what about “information content”
- How can we include or engineer the relationships between such variables


For linearly non-separable spaces, engineer an additional dimension. Express mutual correlation as a differentiation for linear separability
#### $$\hat{y}=\text{sgn}\sum^{n}_{i=1}w_iy_ik(x_i,x^`)$$
#### $$k: X \times X \implies \text{R (all real numbers);} x,x^`\in X$$
### - Ex - datapoints separated by a sphere, $x^2_1+x^2_2<1$  
![[Pasted image 20250211152239.png]]

### Cosine, Quadratic, Linear, Polynomial, Sigmoid, Gaussian

![[Pasted image 20250211152745.png]]

#### [[Support Vector Machines]] uses kernel matrix (Gram matrix)
