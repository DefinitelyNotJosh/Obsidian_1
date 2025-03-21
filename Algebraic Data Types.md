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

