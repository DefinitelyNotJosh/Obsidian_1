
### [[Imperative Programming]]
Limiting what we can do with programs makes us better programmers

Just because you can, doesn't mean you should
-  Takes away side effects
No changing variables
No assigning memory

Why do this? How do we even program without them?
- Not just giving up variables, shifting our focus
Arguably one of most important developments with imperative programming was the introduction of functions

In some form or another, functions are basis for everything

### [[Haskell]]


### What makes functional programming what it is?

#### Higher order functions
- Can pass functions as arguments
- Can return functions from other functions

#### Example of a higher order function in Haskell:
- `map` function: applies a given function to each element of a list
- `filter` function: takes a predicate function and a list, returning a new list with elements that satisfy the predicate
```haskell
map :: (a -> b) -> [a] -> [b]
filter :: (a -> Bool) -> [a] -> [a]
```
- Use of lambda functions as arguments to higher-order functions


