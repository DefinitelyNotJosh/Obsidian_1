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