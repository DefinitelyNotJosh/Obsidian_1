sum type - enum in [[Rust]]

#### Primitive types
Int
Float 
Char
-  a char is a different than int, can't treat a char as int ASCII value

```haskell
chr :: Int -> Char
ord :: Char -> Int
```
#### Types in Haskell
Can make a type synonym with type keword
```
type Name = String
type Length = Int
```
just like C++

```
typeEnv a = Name -> a
type Matrix a = [[a]]
```
Env is a function from names to some other type
Env Type ___ = Name -> Type
Env Exp ___ = ...

#### Tuples
```
x :: (Int, Char)
x = (4, 'c')
```
Can make tuples of up to length 16, if you need more than 16 should rethink how you're writing your program

```haskell
fst :: (a,b) -> a -- first element
snd :: (a,b) -> b -- second element
add :: (Int, Int) -> Int -- add elements
```

## Algebraic Data Types
Haskell has system - Algebraic Data Types
```
data Student String [Int]
data Employee = Employee String Int
```
student = name and list of grades, employee = name and salary

#### Pattern matching
```
grade :: Student -> Int
grade (Student name grades) = sum grades

get_name :: Employee -> String
get_name = (Employee name salary) = name
```


### Alternates
```
data TrafficLight = Green | Yellow | Red

next :: TrafficLight -> TrafficLight
next Green  = Yellow
next Yellow =  Red
next Red = Green
```
Example
```
data Employee = CEO Name
			  | Mgt Name Department
			  | ....
```

All of the functions are defined with pattern matching
```
not :: Bool -> Bool
not True = False
not False = True


```

#### Can make Polymorphic
In haskell, polymorphism is the default
```
data Wrapper a = Wrapper a

notUnwrap :: Wrapper Bool -> Bool
notUnwrap (Wrapper True) = False
notUnwrap (Wrapper False) = True
```

several useful poly types
```
data Maybe a = Just a | Nothing
data Either a b = Left a | Right b -- left is error, right is OK
```
Maybe - option in rust
Either - result in rust
example
```
divide :: Int -> Int -> Maybe Int
divide x y
 | y /+ 0 && mod x y == 0 = Just (div x y)
 | otherwise              = Nothing
```

Either usually used for gathering errors
```
parse :: String -> Either ErrorString Value
```

Now we don't have to worry about return codes

Pattern with them

Bind operator
```
(>>=) :: Either error value ->
		 (value -> Either error value) ->
		 Either error value

(Left e) >>= _ = Left e
(Right x) >>= f = f x
```
If the thing on the left returns an error, we give up
Function composition that stops the first time we get an error

```
type Err String
lex   ::            String   -> Either Err [Token]
parse ::            [Token]  -> Either Err Stmt
check :: Int     -> Stmt     -> Either Err Stmt
exec  :: Env Exp -> Stmt     -> Either Err (String, Env Exp)
```

To put all this together in single function using bind operator is easy

```
runStep :: Int -> Env Exp -> String -> Either Err (String, Env Exp)
runStep n env line = lex line
				   >>= parse
				   >>= check n
				   >>= exec env
```
Don't have to check at each step if we have an error

#### Recursive types

```
data List a = Nil | Cons a (List a)
```
most of our data types end up being recursive

List contains every feature of data types
- Cons is a record
- It has 2 alternates
- It's polymorphic in the type of elements
- It's recursive

Pattern matching works on recursive types
```
length' :: List a -> Int
length' Nil              = 0
length' (cons head tail) = 1 + length tail
```
In haskell, base case is usually a pattern, have to handle base case
- compiler keeps you from writing inf. recursion

Lists in haskell really defined as:
```haskell
data [a] = [] | a : [a]
-- but it's really the same thing
length []     = 0
length (x:xs) = 1 + length xs
```
Write x and xs for head and tail

```
data Tree a = Leaf a | Node a (Tree a) (Tree a)


flip :: Tree a -> Tree a
flip (Leaf x) = Leaf x
flip (Node x...
```

noDups 
```
noDups t = noDups' t []
	where
		noDups' (Leaf x)     seen = not (elem x seen)
		noDups' (Node x | r) seen = not (elem x seen) &&
									noDups' (x:see)
```