Composed of nodes or units connected by directed links
A link from unit $i$ to unit $j$ serves to propagate the activation $a_i$ from $i$ to $j$. Each link also has a weight $w_{i,j}$ associated with it which determines the strength and sign of the connection.

Each unit $j$ first computes a weighted sum of inputs $$in_j=\sum_{i=0}^{n}w_{i,j}a_i$$ then it applies an activation function $g$ to this sum to derive the output: $$a_j=g(in_j)=g (\sum_{i=0}^{n}w_{i,j}a_i)$$
If the activation is a hard threshold (most of the time it is), the unit is called a perceptron, or logistic function, or sometimes a **sigmoid perceptron**. 

### Feed-forward network
has connections only in one direction, directed acyclic graph

Usually arranged in **layers**
- single-layer - every unit directly connects from network inputs to outputs
- multilayer - have one or more layers of **hidden units** that aren't connected to the outputs of the network
### Recurrent network
feeds outputs back into its own inputs - outputs depend on both inputs and current state.
Effectively has short-term memory 

### [[Sigmoid Activation]]

#### Review: Step functions
- output dependent on if input is greater than 0 or not

#### Activation functions
- Multiclass classification problems
- Non-linear separable spaces
- Networks, deep networks, convolution deep neural networks

$$f(x)=\frac{1}{1+e^{-x}}$$
$$\frac{d}{dx}f(x)=\frac{e^x}{(1+e^x)^2}=f(x)(1-f(x))$$

### ANN Learning

#### Bad architecture for a neural network - shrinking hidden layers, expecting lets say 5 perceptrons to have 20 outputs

#### Good architecture is growing hidden layers and then shrinking them to get an output

#### Softmax
normalized output of $y_i$ wit respect to all other outputs $$y_{softmax}(y_i)=e^{y_i}/\sum_{j=1\text{ to }m}(e^{y_i})$$
#### ANN Learning Rule,  where $\mu$ is learning rate $$w_k=w_k+\mu(y_{\text{expected}}-y_{\text{actual}})$$ $$w_k=w_k+\mu \times \triangle w$$ 
![[Pasted image 20250204151448.png]]

#### $$\frac{\sigma E_{total}}{\sigma\text{out}}=(y_{o 1\text{ exp}} - \text{out}_{o 1})$$
#### $$\frac{\sigma \text{out}}{\sigma\text{in}}=\text{out}_{o1}\times(1-\text{out}_{o1})$$
#### $$\frac{\sigma \text{in}}{\sigma\text{w}}=\text{out}_{h1}$$
### Learning Algo in Practice: $$\sigma=\text{out}(1-\text{out})*\sum w* \sigma_0$$




![[Pasted image 20250204153457.png]]

![[Pasted image 20250204153510.png]]

### [[Kernel Methods]]
### [[Gabor Filter]]
