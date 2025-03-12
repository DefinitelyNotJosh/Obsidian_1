Describes relative likelihood of all values for a continuous random variable
- Ex - time for Casey to do chores is random variable $X$, where all values between 1 and 2 hours are equally likely
- Notation $f(x)$ typically used for PDF
- For Casey's chores, $f(x)=1$ for all values of $x$ between 1 an 2 and 0 everywhere else
Can be written as a function, but often graphical representation is most descriptive, where area under curve is probabilities
- for graph: pdf must be non-negative and total area under curve must be 1


### To know - 100% of all probabilities within a PDF are under the curve:
#### $$\int^{\infty}_{-\infty}f(x)dx=1.0$$
#### $$P(a\leq X \leq b)=\int^{b}_{a}f(x)dx$$
#### $$F(x)=p(X\leq x)=\int^{x}_{-\infty}f(u)du=\text{CDF}$$ #### [[Cumulative Distribution Function (CDF) (Continuous)]]
#### ^ Where f(u) = PDF function f(x)
#### $$P(a \leq X \leq b)=F(b)-F(a)$$ $$P(X=x)=0$$
### Also important to note: Because $P(X \leq x)=P(X < x)$ and $P(X=x)=0$, $$P(X\leq x)=P(X<x)$$
![[Pasted image 20250212083734.png]]
![[Pasted image 20250212083746.png]]

