## Main page for EGR-361

### [[Quantitative]]
### [[Categorical]]


## Variables


| Population (parameters) |            | Sample (statistics) |
| :---------------------: | :--------: | :-----------------: |
|          $\mu$          |    mean    |   $\overline{x}$    |
|       $\sigma^2$        |  variance  |        $s^2$        |
|        $\sigma$         |  std dev   |         $s$         |
|           $N$           |    size    |         $n$         |
|           $p$           | proportion |      $\hat{p}$      |



### Ways to Interpret Data:
### Descriptive
describes data in given timeframe, often in hopes to achieve insight - eg, correlation

### Predictive
makes predictions with data - eg, stock market

### Prescriptive
make decisions with data - eg, ordering supplies


#### Remember: $\bar{x}$ for sample mean, $\mu$ for population mean
#### Parameters for population, statistics for sample

#### Descriptive Statistics
Analysis/display of data
#### Inferential Statistics
 Making predictions based on data/principles  of probability


### Data Collection Methods
1. Retrospective Study - studying past events
2. Observational Study - observing events, not interfering
3. Designed Experiment - controlled environment to find relationships with more certainty
 
#### Variability
Difference between values in the dataset and the center of the dataset
#### Variance
Average of the square difference from the mean
- eg - if average speed is 55mph and variance 9mph, the stddev is 3mph
#### Standard Deviation
square root of variation
![[Pasted image 20250115102646.png]]

#### Population variance: $$\sigma^2=\frac{\sum^{n}_{i=1}(a_i-\mu)^2}{n}$$ Population standard deviation: $$\sigma=\sqrt{\frac{\sum^{n}_{i=1}(a_i-\mu)^2}{n}}$$ Sample variance: $$s^2=\frac{\sum^{n}_{i=1}(a_i-\bar{x})^2}{n-1}$$ Sample standard deviation: $$s=\sqrt{\frac{\sum^{n}_{i=1}(a_i-\bar{x})^2}{n-1}}$$

#### Mean Absolute Deviation (MAD)
Mean of absolute difference between each value and the mean of the values
$$
MAD =\frac{\sum_{i=1}^{n}{|a_i-\bar{x}|}}{n}
$$

#### Percentile
data value that $n$ percent of data falls at/below. Calculated using for dataset of length N using:
$$
(N-1)\times[percent]+1
$$
where $n$ is a number between 0 and 1.

If result has decimals, interpolate

### Five-number summary
1. Min
2. Max
3. Q1: $(N-1)\times[0.25]+1$
4. Median
5. Q3: $(N-1)\times[0.75]+1$

#### Recap - measures of center:
1. Mean
2. Median
3. Mode
#### Skew
difference between mean and median
- If skewed, mean/median not in same place
- right-skewed if data skews to the right, left-skewed if data skews to the left

#### Interquartile range (IQR)
difference between Q3 and Q1
### Value considered an outlier if: 
1. greater than $Q3+1.5(IQR)$ or less than $Q1-1.5(IQR)$ 
2. Using the Z-score: $Z=\frac{X-\bar{X}}{s}$, Outliers have $|Z|\geq3$ or $|Z|\leq-3$. Think of Z as "how many stddev is this sample from the  mean?" 
	1. 3 stddev outside of sample mean
#### Frequency distribution
table that displays how often an outcome occurs in a sample
#### Class
value of a categorical variable OR interval of continuous variable

#### Histogram
Rule of thumb: start with bin size so that number of bins is about equal to square root of number of values

ex. Officer gives 15 tickets that are up to 28mph over speed limit
$sqrt{15}=3.9\approx4$ , $28\div4=7$ mph bins. Bin size should be around 7mph, but play with it. Point is to show trends in data
#### - [[Distribution]]

#### - Unit area histogram
	rectangle heights equal to the bin frequency / bin size
	
![[Pasted image 20250115113100.png]]


## Reading 3

#### Experiment
Procedure that results in one out of a number of outcomes
#### Sample space
Set of all possible outcomes
### Events
Subset of sample space
##### Compound
subset of sample space consisting of more than one outcome
- ex. rolling an even number on a dice has |{2,4,6}| =3 outcomes
##### Simple
subset with a single outcome
- ex. rolling 5 on a dice has {5} as an outcome
#### Probability
Measure of how likely an event will occur, event A denoted as P(A) (not to be confused with permutation). Calculate by outcomes / # of outcomes. May also be worded as:
$P(X)=$ # of possibilities that meet X / total # of possibilities
- Relative frequency of desired outcome when an experiment is repeated an infinite number of times

### Discrete Overview:
Sets are now events
###### Union of events A and B is $A\cup B$, includes outcomes in A, B, or both
###### Intersection of events A and B is $A\cap B$, includes outcomes that are in both A and B
###### Complement of event A is $\overline{A}$, includes outcomes that aren't in A
###### Empty set = event with no outcomes
###### Events are **mutually exclusive** if $A\cup B=A + B$ and $A \cap B=\emptyset$, no outcomes in common
###### Events are **independent**  if probability of one event doesn't effect the probability of another - $A|B = A$ or $B|A = B$


#### Axioms of Probability
The probability of an event must be between 0 and 1, inclusive
- Smallest probability (event never occurs) is 0, maximum (when event always occurs) is 1
#### Complement rule
Relates probability of an event to probability of complement of event
For any event $A$, if the probability of of $A$ is $P(A)$, the probability of $\overline{A}$ is $P(\overline{A})$.
#### Addition/Additive rule
Generalizes the complement rule to events which aren't mutually exclusive
For any events $A$ and $B$, $P(A \cup B)=P(A)+P(B)-P(A \cap B)$.

#### Multiplication rule
Gives probability of 2 independent events happening together
Let $A$ and $B$ be independent events. The probability that both $A$ and $B$ occur is $$P(A \text{ and } B)=P(A)P(B)$$
Can be generalized to $$P(A_1\text{ and }A_2\text{ and }A_3...A_n)=P(A_1)P(A_2)...P(A_n)$$

[[EGR-361 probability extra credit]]


## Reading 4
#### Conditional probability
measure of probability of one event given that another event occurred
Conditional probability of event $A$ given event $B$ has occurred is denoted as $P(A|B)$ and is equal to: $$P(A|B) = \frac{P(A \cap B)}{P(B)}$$
- At times, no experiments are even necessary to draw probabilities - mathematical proofs can be useful
#### Law of total probability
If the sample space is partitioned into 2+ subevents, the probability of event $B$ can be expressed by conditional probabilities given each of the subevents
Let a sample space $S$ be partitioned into $k$ subregions $S_1,S_2,S_3,...S_k$. let $B$ be an event in $S$. Then $$P(B)=P(B|S_1)P(S_1)+P(B|S_2)P(S_2)+P(B|S_3)P(S_3)+...+P(B|S_k)P(S_k)$$

#### Bayes' Theorem
Relates the probability of an event $A$ given a condition $B$ to the probability of condition $B$ given that the event $A$ occurred. In a nutshell, allows $P(B|A)$ to be calculated from $P(A|B)$.
Let $A$ and $B$ be the events in the same sample space such that $P(A)=0$ and $P(B)\neq0$. Then, $$P(A|B)=\frac{P(B|A)P(A)}{P(B)}=\frac{P(B|A)P(A)}{P(B|A)P(A)+P(B|\overline{A})P(\overline{A})}$$
## Reading 5

### [[Counting Rules]]
#### Multiplication/Multiplicative rule of counting (pt 2)
If one event can occur in $A$ ways and another event in $B$ ways, the number of possible ways both events can occur is $A \times B$.
#### Permutations
possible ordering of set objects. Order **does** matter. 

With replacement - eg, number of password combos (sample size being depleted): $$P_{n,k}=n^k$$
Without replacement - # of positions < # of objects: $$P_{n,k}=\frac{n!}{(n-k)!}$$
#### Combinations
Places selected objects in order. The number of ways to "choose" a set of $k$ objects/positions/choices from a group of $n$ objects. Order **doesn't** matter. 
Without replacement: $$C_{n,k}=\binom{n}{k}=\frac{n!}{k!(n-k)!}$$
With replacement: $$\binom{n+k-1}{k-1}=\frac{(n+k-1)!}{(k-1)!((n+k-1)-(k-1))!}$$
#### Partitions

#### Probability using combinatorics


## Reading 6

### Random variables
A rule that assigns a number to every outcome in the sample space of an experiment
- ex - coin toss may assign 1 to heads and 0 to tails
- Random variables typically defined using capital letter, ex $X=1$ is heads and $X=0$ tails
### [[Discrete Random variable]] 
Can take on a countable number of distinct values like the integers between 0 and 100
- Typically counted
#### Probability mass function of a discrete probability distribution
###### **[[Probability mass function (PMF) (Discrete)]]** assigns the probability that a discrete random variable is exactly equal to some value
- Notation $p(X=x)$ or $p(x)$ is typically used for the PMF of $X$
- Probabilities assigned in a PMF are between 0 and 1, and he total probability must sum to 1
- If in a histogram, it's the "mass" of each outcome relative to the total probability
###### **[[Cumulative distribution function (CDF) (Discrete)]]** of a discrete random variable is the probability that for any number $x$, the observed value of the random variable will be at most $x$ or $p(X \geq x)$. 
- ex. - when a fair die is rolled and the value facing up is recorded, CDF describes the probability of getting less than or equal to any value $x$, such that the probability $X$ is less than or equal to 3
	- $F(3)=p(X \geq 3)=\frac{1}{2}$ is read as: "the probability $X$ is greater than or equal to 3 is one half"
	- $p(X  \geq 6) = 1$, as the probability of the number being greater than or equal to 6 is 100%
	- Notation $F(x)$ is typically used for the CDF of X
	- CDF always starts at 0 and ends at 1, never decreases as the value of X increases

###### The **mean** or **expected value $\mu$** of a discrete random variable $X$ is the sum of the possible values of X multiplied by the probability of the value. $$\mu = E(X) = \sum{(x*p(x))}$$
Keep in mind, computing the mean does not always make sense for a discrete random variable
###### The **variance** of a discrete random variable $X$ is a measure of the spread of a distribution.$$\text{variance} = \sigma^2=V(X)=\sum{((x-\mu)^2*p(x))}$$
 ###### The **standard deviation** is:$$\sigma=\sqrt{\sigma^2}=\sqrt{\text{variance}}$$
#### In class activity:
1. Is this a valid PMF? - yes, all the values add up to 1.0
2. What is the CDF? - graph of values
3. What is the probability you knock down more than 5 pins on your first shot? - 0.11
4. How many pins should you expect to knock down on your next first shot? - 2 (rounded down from 2.34)
5. What's the STDEV of your bowls? - $\sigma^2=4.6484$ , $\sigma = 2.15$
#### [[Continuous Random Variable]]
Can take on any value within a range of values, like the real numbers between 0 and 1
- Typically measured
- find more info in Reading 9



## Reading 7
### [[Distribution]]

#### [[Binomial Distribution]]
#### [[Bernoulli Distribution]]
#### [[Geometric Distribution]]


## Reading 8
#### [[Poisson Distribution]]

#### Cumulative probability
Sum of the probabilities being considered. found by summing the probabilities for fewer events and subtracting that from the total probability.

## Reading 9

### Properties of continuous probability distributions
#### [[Probability Density Function (PDF) (Continuous)]]

#### [[Cumulative Distribution Function (CDF) (Continuous)]]

#### [[Continuous Random Variable]]


## Reading 10
### [[Exponential Distribution]]
### [[Cumulative Probability]]


## Reading 11
### [[Normal or Gaussian Distribution]]
### [[Unimodal Distribution]]
### [[Empirical Rule]]
### [[Z-Score]]
### [[Sample Distribution]]
### [[Standard Error]]
### [[Central Limit Theorem (CLT)]]

### [[Binary Categorical Variable]]


## Reading 12
### [[T-Distribution - T-Test]]


## Reading 13

#### Point estimate
A single value estimate for an unknown POPULATION parameter
- ex - a sample of 15 employees have a mean of 38.4 hours worked weekly which is a point estimate for the population mean hours worked weekly for all employees at the company
#### Interval estimate
A range of possible values for the population parameter being estimated
- ex - Based on the sample of 15 employees, a 95% confidence interval for the population mean hours worked weekly is (35.2, 41.6)
#### Accuracy
Measured in terms of bias, how close on average the estimate is to the population parameter being estimated.
- Numerically, the distance between the mean of the sampling distribution and the population parameter being estimated
#### Precision
How close variable estimates are to one another if the estimation process is repeated
- Measured in terms of the standard error of the sampling distribution
#### An interval estimate is considered accurate if the interval contains the true population parameter, and an interval estimate's precision refers to the width of the interval

### [[Confidence Intervals]]

## Reading 14

### [[Z-Confidence Intervals]]
### [[T-Confidence Intervals - T-Test]]

## Reading 15
### [[Confidence Interval for Population Proportions]]

## Reading 17

### [[Hypothesis Testing]]

## Reading 18
more in [[Hypothesis Testing]]
### [[Z-Test]]
### [[T-Test]]

## Reading 20
#### [[Hypothesis Testing for Population Proportion]]

## Reading 21
### [[F-Distribution]]

### [[ANOVA]]
### [[One-Way ANOVA]]

## Reading 22
### [[Linear Regression]]
- [[Simple Linear Regression]]
### [[Correlation and Coefficient of Determination]]
### [[T-Test for Population Correlation Coefficient]]
