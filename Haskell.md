Instead of focusing on what we lose w variables, focus on what we gain with functions

#### [[Lists in Haskell]] - lecture 15


```
square :: Int -> Int
square x = x * x

isPalindrome :: String -> Bool
isPalindrome str = reverse str == str
```
Things to note
- Functions are defined w equations
- The type of a function is math style, $f : R->R$ 
- Function calls are juxtaposition f x
	- instead of parenthesis f(x)
- No statements - no loops
#### have to use recursion

What about flow of control? Guards and recursion
Count digits in a number - if `n` is less tan 10, then it has 1 digit
If `n` is greater than 10, it has 1 digit, plus the digits of `n/10`

```
ilog :: Int -> Int
ilog n
	| n < 10    = 1
	| otherwise = 1 + ilog (div n 10)
```

| - a guard
code above - if `n` is less than 10 it has 1 digit, otherwise it has 1 digit, plus the digits of `n/10`

Guards instead of if statements 

### What makes this [[Functional Programming]]?

#### Higher order functions
- Can pass functions as arguments
- Can return functions from other functions
##### This isn't new - a derivative is a higher order function. It takes a function and returns a function

Also function composition - 'glue' function in haskell
```
(.) :: (b -> c) -> (a -> b) -> (a -> c)
(f . g) x = f (g x)
```
Equivalent to $f(g(x))$


#### Lists in haskell - a list is a sequence of elements - everything we can do to a list we can do to a string
```
numbers :: [Int]
numbers = [1,2,3,4,5]

strings :: String
```

reverse - reverses a list
reverse implementation: 
``` 
reverse :: [a] -> [a]
reverse [] = []
reverse (x:xs) = reverse xs ++ [x]
```

group - groups lists together



intersperse - takes an element and intersperses them in a list (buts between each element)

intersperse implementation:
``` 
intersperse :: a -> [a] -> [a]
intersperse _ [] = []
intersperse _ [x] = [x]
intersperse y (x:xs) = x : y : intersperse y xs
```


concat - smashes lists together


### Why functional programming?
Solve a problem:
I have string `n` -want to add commas every 3 digits

functional approach:

```
addCommas :: String -> String
addCommas = reverse
		  . concat
		  . intersperse ","
		  . group 3
		  . reverse
```



Haskell 'group' implementation: 
```
group :: Int -> [a] -> [[a]]
group _ [] = []
group n xs = take n xs : group n (drop n xs)
```

Key points to note:
* Pattern matching for empty list
* Recursive call with dropped list
* Using take and drop functions 
* Example use case: `group 3 [1,2,3,4,5,6,7,8,9]`
* Use cases for group function:
  * Splitting lists into chunks
  * Formatting data into groups
  * Processing lists in batches 


Functional programming is useful because it promotes code reusability and simplicity. Key benefits include:
- Immutable data structures
- Easier debugging
- Improved composability 
