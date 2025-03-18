### Under the umbrella of AI, subset of it that uses data

"The field of study that gives computer the ability to learn without being explicitly programmed" - Arthur Samuel

"A computer program is said to learn from experience E with some class tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E." - Tom Mitchell

### [[Artificial Neural Networks]]

### [[Support Vector Machines]]

### [[Kernel Methods]]
### [[Dimensionality Reduction]]

### [[Unsupervised Learning]] (Clustering document)

### [[Supervised Learning]] (Clustering document)

## Week 9-10
### [[Probabilistic Machine Learning]]
### [[Bayesian Learning]]
### [[Logistic Regression]]
### [[Markov Graphical Models]]





#### Fine line between generalization and specification
if model is overtrained, it can lose the ability to generalize - eg, can't recognize a human face when overtrained on a specific group of people 

- Stochastic Gradient Descent

#### Bias-Variance Tradeoff


### Methods of Data collection
Supervised: labeled
Unsupervised: unlabeled - [[Unsupervised Learning]]
Semi-supervised

#### [[Regression]]
#### [[Gradient Descent]]


### ML Tasks
- Detection of diseases/cancers from MRIs
- Detecting Spam email
- "Game" AI - stockfish? 
- Image recognition and classification
- Natural language processing
- Recommendation systems
- Anomaly detection
- Time series forecasting
### Steps:
1.  Pre-Processing
2. Feature extraction
3. Representation
4. Learning
5. Prediction


### Generally good practice to stop training a general model when learning error intersects with classification error

### Ethical ML
- All about data
- Everyone is wrong- human, machine, AI
	- big opportunity in correcting biased ML models

#### Assumptions:
- Unbiased training set
- set large/inclusive enough
	- Inductive reasoning possible
		- Learning data → Generalized model
		- Test data → Generalized model → Predictions


### Ensemble
Multiple models training on data, models outside of ensemble trained on data points models got wrong, poorly performing models in ensemble gets replaced by new models outside of ensemble


Numerical calculation:
Python openCV, pandas, Tensorflow, numpy(CuPy is better now)


### How to know which way to adjust parameters
Take derivative of error function in respect to parameters to know which way to adjust the model

### Local Minima
Traps in the data that get error function "stuck"

#### Measuring Accuracy
how 'good' a model is
closer look at positive vs negative labels
statistical analysis

DiCE score

TN = true negative
TP = true positive
FN = false negative
FP = false positive

Accuracy (A):
AC = (TN +TP) / (TN+FP+FN+TP)

Recall(R) - proportion of correctly classified positive instances:
RC = TP / (FN+TP)

Precision(P) -proportion of the predicted positive instance that was correct:
PR = TP / (FP+TP)


### [[CS-429 HW1]]

### [[CS-429 HW2]]
### [[CS-429 HW3]]
