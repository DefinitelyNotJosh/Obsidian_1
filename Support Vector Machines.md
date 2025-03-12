- Maximum margin method 
- Assume Binary classification problem
- Supervised Learning
	- –Each training point is a vector of features: x = (x1 ,x2 ,x3 ,x4 ,x5 ,...xn )
	- –Training samples X = {(x1 ,y1 ),(x2 ,y2 ),(x3 ,y3 )... (xm ,ym )}
	- –Training set is labeled by {1,-1}
	- –For simplicity the examples will be from 2D feature space 
- Train model to separate training set to 1 and -1 
- Model optimized as a hyperplane

![[Pasted image 20250211145648.png]]

- Hard Margin – no training sets are allowed inside of the margin 
- The most fitting hyperplane will maximally separate the two labeled samples (Vapnik 1979) 
- Margin, distance of hyperplane to the nearest instance of each labeled set 
- Optimization problem 
- The hyperplane is your decision 
- Alternatively the margins defined as: w.x+b = +/- a
![[Pasted image 20250211151448.png]]