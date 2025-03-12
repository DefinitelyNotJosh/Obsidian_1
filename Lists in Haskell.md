Lecture 15 cs352
```
funcName :: Type
funcName param_1 param_2 ... param_n = expression
```
All functions have this form

Expressions: 
- Lots of different types of expressions - assignment expressions, if expressions, case expressions
- These are NOT statements

#### Lambda
- A lambda expression has the form - `\x -> e`
- Fundamentally everything a lambda
- Can be used as event handlers
- Haskell based on the Lambda Calculus
- Supports type inference 
- Often used with `map()`, `filter()`, and `reduce()` functions

``` 
lambda x: x * 2
```

```
square :: Int -> Int
square \x -> x * x
```


Everything that can be done with a turing machine can be done with lambda calculus and vise versa

Alonzo Church in the 1930's asked the question what is a function - answer - takes an input and gives back an output

#### New notation for functions: $$\lambda x.e$$ this is a function that takes a variable called and returns an e $$f(x)=x^2+2x+1 \text{  is equivalent to } f = \lambda x. x^2+2x+1$$ now, $f$ is just an ordinary variable, and functions are just objects we can use

What can I do with a function? Call the function
- This is function application
When we call a function, we replace the argument with the value

Can do $$(\lambda x. x^2 +2x+1) ~5=5^2+2*5+1$$
#### Example $$(\lambda x. x+x)((\lambda y. y+y)~3)$$ Order of evaluation generally doesn't matter - end up with 12

### Sometimes it does, if you run out of arguments: reduce from left to right if possible $$(\lambda f.(\lambda x. f~x))(\lambda y. 2*y)~3$$

[[Functions in Haskell]] tangent

Lists in Haskell:

Lists are really made out of cons : and nil []
The list is really

ints :: \[Int]
ints = \[1 .. 5] - actually works, does 1-5


\[1,2,3 ..] - infinite list

ints = 1 : 2 : 3 : 4 : 5 : \[]

#### All of haskell's lists are linked lists

3 fundamental functions for lists: Map, filter, foldr. Implementations: ### 3 Fundamental Functions for Lists

#### 1. `map` - Applies a function to each element of a list

```haskell
map :: (a -> b) -> [a] -> [b]
map _ [] = []
map f (x:xs) = f x : map f xs
```

#### 2. `filter` - Selects elements of a list for which a predicate is True

```haskell
filter :: (a -> Bool) -> [a] -> [a]
filter _ [] = []
filter p (x:xs) = if p x then x : filter p xs else filter p xs
```
