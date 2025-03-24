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

#### Functions can only have one type - cannot do adhoc polymorphism in Haskell
- It, however, has parametric polymorphism

#### Solution: Typeclasses 
These are Haskell Typeclasses, have nothing to do with OOP classes


Typeclass - defines functions that each type can implement
```haskell
class Equal a where
	where :: a -> a -> Bool
```
Closer to interfaces, NOT OOP CLASSES

```
instance Equal Bool where
equal True True   = True
equal False False = True
equal _     _     = False
```

can use a typeclass to put a constraint on our types
nub function - removes duplicates
```
nub :: (Equal a) => [a] -> [a] -- '=>' has to have implemented Equal
nub []     = []
nub (x:xs) = x: nub (filter (not . equal x) xs)
```

Class Eq
```
class Eq where
	(==) :: a -> a -> Bool
	(\=) :: a-> a -> Bool

	a == b = not (a \= b)
	a \= b = not (a == b)
```
^ if you implement either '\==' or '\\=', you get the other

Class Ord
```
class Ord a where
	(>=)    :: a -> a -> Bool
	(<=)    :: a -> a -> Bool
	(<)     :: a -> a -> Bool
	(>)     :: a -> a -> Bool
	min     :: a -> a -> a
	max     :: a -> a -> a
	compare :: a -> a -> Ordering 
```

Every 'ord' thing is automatically an 'Eq' thing
Not exact definition

Class Show and Class Read
```
class Show a where -- toString() method
	show :: a -> String

class Read a where -- parsing 
	read :: String -> a
```

Haskell can't print out functions, functions don't have "Show" implemented
Also can't check if each function is equal, as they don't have 'Eq' implemented
- Makes sense

#### Deriving
Implementations normally easy, compiler can do it
```
data TrafficLight = Red | Yellow | Green
	deriving(Show, Eq, Ord, Read)
```

Some typeclasses where it doesn't work
#### Num
Numbers in haskells aren't integers 
```
class Num a where 
	(+)         :: a -> a -> a
	(-)         :: a -> a -> a
	(*)         :: a -> a -> a
	negate      :: a -> a -> a
	abs         :: a -> a -> a
	signum      :: a -> a 
	fromInteger :: Integer -> a
```
^= NOT DONE

Example
```
data Complelx = Comp Float Float

norm :: Complex -> Float
norm(Comp r i) = sqrt (r*r) (i*i)

class Num Complex where
	(Comp r i) + (Com r' i') = Comp (r+r') (i+i')
	...
	
```
Num instance for matrix
```
data Mat a = Mat [[a]]

instance Num (Mat a) where
	(Mat m) + (Mat n) = mat (zipWith (zipWith (+)) m n)
	...
```

but assumes can add elements in our matrix
We need to know that in Mat a, a is a Num
```

instance (Num a) => Num (Mat a) where
	(Mat m) + (Mat n) = Mat (zipWith (zipWith (+)) m n)
	...
```

Now, can treat matrices as if they're just numbers

Cannot derive Num, have to implement manually


#### Matrix and higher order typeclasses
What if I try to make Mat polymorphic?

Why does it have to be list?
Wy can't we have a map that wokrs on trees, matrices, or Maybe?

```
map :: (a -> b) -> Tree a -> Tree b
map :: (a -> b) -> Mat a -> Mat b
map :: (a -> b) -> Maybe a -> Maybe b
```

For any type a, Tree a is a type
can use **Type Constructors**

```
class Functor f where
	fmap :: (a -> b) -> f a -> f b
```
So what is f here?
- Function that is polymorphic in the data structure

```
data Tree a = Leaf a | Branch a (Tree a) (Tree a)

instance Functor Tree where
```