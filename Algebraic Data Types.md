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
lex   :: 
parse ::
parse ::            [Token] 
check :: Int     -> Stmt
exec  :: Env Exp -> Stmt
```