
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

Higher order function implementation: - Utilize lambda expressions
- Leverage function composition
- Implement map, filter, and reduce operations
- Create closures to encapsulate data and behavior
- Use currying to transform functions with multiple arguments

``` 
def higher_order_function(func, arg):
    return func(arg)
```

- Apply recursion to solve problems with nested function calls 
- Define function decorators to extend or modify existing functions 
- Explore the use of callbacks and asynchronous programming techniques 
- Study the concept of monads - Examine the role of immutability in functional programming
- Learn about lazy evaluation and its benefits
- Explore type systems and their impact on functional programming
- Investigate the use of pattern matching for concise code
- Discover how to apply functional programming principles to real-world problems
- 
``` 
def immutable_data_structure(example_data):
    return example_data[:]
```
