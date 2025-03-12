if B inherits from A, then B is an A

```
class B : public A
```

In type theory, we say that B <: A (B is a subtype of A)

#### To model this, we give an **inference rule** $$\frac{\text{e~:~S~~~~~~S~<:~T}}{e~:~T}\text{T-Sub}$$
"if e is an expression of type S, and S inherits from T, then e is an expression of type T"

#### Refl rule - every object inherits from itself $$\frac{}{S~<:~S}\text{Refl}$$
#### Trans rule $$\frac{S<:T~~~~~T<:U}{S<:U}\text{Trans}$$

if A \\= B and A<:B, then B \\<:A.
We don't have anything that states this, but would lead to infinitely large objects

We have 3 rules: 
A <: A
if A <: B and B <: A then A = B
if A <: B and B <: C then A <: C

What this means - all inheritance is a Directed Acyclic Graph
- If we restrict ourselves to single inheritance, can make inheritance tree


#### Java problem
Java array subtyping rule
if A <: B, then A\[] <: B\[]

Every array of type B can be converted to an array of type A, allowing objects that aren't of type B but inherit from A to be put into the same array. It will compile, but it will have a runtime error