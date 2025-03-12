Multiple parameter functions in Haskell. example: 
```
avg :: Float -> Float -> Float
avg x y = (x + y) / 2
```

in Haskell, avg really is:
$avg=\lambda x.(\lambda y.(x+y)/2)$ 

#### Currying Theorem
A function that takes multiple parameters is equivalent to a function that takes a first parameter and returns another function

``` haskell
avg4 :: Float -> Float
avg4 = avg4
```
This is a partial application - average will average any number with 4

``` haskell
avg x y = (x + y) / 2
avg 2 4
```
``` haskell
map (+1) [1, 2, 3, 4]
```

