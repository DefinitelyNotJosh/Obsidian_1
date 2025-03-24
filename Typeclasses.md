#### Functional OOP

### Operators
+, -, *, /, \==, <=,  >=, <, >

also includes composition and bind operators ., >>=

Haskell supports operator overloading, and lets us make up our own operators

ex - put parentheses around it to define it as an oprator
```
(><) :: [Int] -> [Int] -> [[Int]]
xs >< ys = map (\x -> map (x*) ys) xs
```
#### Defining equality

How do we defined the '\==' operator?
```
equal :: a -> a -> Bool
equal a b = ...
```
For booleans, it's simplle
```
equal :: Bool -> Bool -> Bool
equal True True   = True
equal False False = True
equal _     _     = False
```

