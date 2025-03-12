Order of operations:
Tedious - have to fit all new operators into PEMDAS
hard to manipulate with program

So we use Abstract Syntax Trees

$$
\begin{align}
E \implies N \newline
| E + E \newline
| E - E \newline
| E \times E \newline
| E \div E \newline
| E \land E

\end{align}
$$

- Any number is an expression
- Can add expressions together
- Nothing else is an expression

Can turn expressions into trees - an AST

Advantages:
- Don't have to remember PEMDAS
- New operator adding is easy
- Much easier for computers to work with

#### Can represent whole programs with an AST


### Rules:
#### $1+2+3$
we add $1+2$ first, and then add $+3$
![[Pasted image 20250115140127.png]]
#### we say that $+$ is *left associative*, aka goes from left->right
#### right associative is right->left

#### $1+2\times3$
we go from right to left, $2\times3$ and then add 1 
![[Pasted image 20250115140521.png]]
#### We say that $\times$ has *higher precedence* than $+$
- the "PL" term for order of operations

#### Solved via [[Recursion]]
