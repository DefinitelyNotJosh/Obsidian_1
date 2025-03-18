### [[Naive Bayes Classifier]]
### [[Gaussian Bayes Classifier]]

### [[Bayes' Theorem]] recap:
 
 Bayes' Rule: Space of hypothesis h has many models. Input: Training set of data D $$P(h|D)=\frac{P(D|h)P(h)}{P(D)}$$
You are a physician and you see 2000 patients, out of these you see 110 of them aren't sick. You work on a clinical study and 500 of your patients participate in the clinical study and of the patients only 80 are not sick

probability patient is not sick in regular practice?
0.055
probability next patient in clinical study is not sick
0.16
Probability next patient coming participates in clinical study?
0.25
For a known patient in clinical study, probability is not sick?
0.2
For patient who is not sick, probability patient is in the clinical study
0.72


### Maximum Posteriori Learning (MAP)
Goal: Find a maximum posterior hypothesis $h_{map}$
#### $h_{map}$ is maximum likelihood hypothesis

### $$argmaxP(h|D)=\frac{P(D|h)P(h)}{P(D)}$$