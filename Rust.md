#### Primary Function: Fixes memory issues that pop up in C
- Still tries to be low-level like C, but safe

### [[Memory (CS)]]


ex - can't compare floats directly
- Annoying, but philosophy is "everything is safe"

How to make a variable:
`let [mut] name [: type] = value;`O
ex.
`let y : i32 = 4`
`let mut a : i32 = 4`
- Don't have to declare type, but recommended
- Can't assign to variable unless it's mutable
	- Reason: no race conditions when running on threads
### Types:
Ints: i8, i16, i32, i64 - all ints
usize:  unsigned int used for length of arrays
Floats: f8, f16, f32, f64
Bool
Char
\[T; N]: array of type T of length N
Vec\<T>: vector of type T
String: a string, NOT a CHAR*
HashSet\<T>: a set of type T
Box\<T>: a pointer to type T
\[T]: a slice of type T
&str: string slice
### Data Types
Structs: similar to C structs
`pub struct StructName {`
	`var : type,`
	`.... `
`}`

Enums: like a bunch of tiny structs
`pub enum Name {`
	`Constructor(Type, Type,...Type),`
	`Constructor(Type, Type,...Type),`
	`Constructor(Type, Type,...Type),`
`}`
ex.
`pub enum GameAction {`
	`MovePiece(i32, i32),`
	`Capture(Piece),`
	`GiveUp`
`}`
- Basically Java inheritance without constant "instanceof" checks
#### Option
Represents data that might be there
`pub enum Option<T> {`
	`None,`
	`Some(T)`
`}`
#### Result
Represents a value that might have an error
`pub enum Result<T, Error> {`
	`Ok(T)`
	`Err(Error)`
`}`
### Flow of Control
goto LABEL
- Only thing your computer can do at assembly level is to go to a label
#### Structured Programming Theorem
Any program that can be written with goto, can be translated to an equivalent program using if statements and while loops
- "More features" is usually a detriment
##### Categories:
1. Sequence
2. Selection (if, switch)
3. iteration (while, for)
4. invocation (function/method)
5. error handling(try/catch: not in Rust)
#### Rust expressions:
- if then else
`let x = if 2 > 4`
	`then { "Not-this" }`
	`else { "this" };`
- match: inspects an expression, pick one of the cases
![[Pasted image 20250117141434.png]]

##### Enum use case:
`enum FileTree {`
	`File(String, usize),`
	`Dir(String, Vec<FileTree>)`
`}`
- Recursive structure

Rust forces you to deal with error cases

#### Orthogonality
Can nest arbitrary expressions inside each other
- In Rust, every statement returns a value
- The ; discards the value so we can put two statements together
If we can test two types of expressions inside each other, then we say the expressions are orthogonal

Only thing that's not an expression is let
#### Loops
- Loop: runs forever
- While: works while condition is fulfilled (must be boolean)
`while <condition> {`
	`<body>`
`}`
- For: similar to for:each loops in java
`for item in <collection> {`
	`<body>`
`}`
`for i in 1..11 {`
	`println!("{i}");'
`}`
#### Functions
`fn <name>(<arguments>) -> <return_type> {`
	`<body>`
`}`

### Iterators
#### How does a for-each loop work?
Basically:
`for thingy in collection`
`{`
	`do stuff with thingy`
`}`

Basically iterates through a linked list doing:
`List<Integer> list = ...;`
`while(list !- null)`
`{`
	`T x = list._head;`
	`list = list._next;`
`}`

#### 3 things going on:
- Get a value from list
- check if we're at the end
- move to the next node
Java abstracts these into an *Iterator* object,` interface Iterator<T>`
Also has an interface Iterable, which allows you to iterate to any class - `interface Iterable<T>`


What classes in java have an iterator?
- ArrayDeque
- ArrayList
- ConcurrentHashMap
- ConcurrentLinkedQueue
- ConcurrentSkipList
- DelayQueue
- HashSet
- LinkedHashSet
- ...
Basically every data structure in Java

Remember for loops are **syntactic sugar** for while loops - done for convenience, not super important

#### Are iterators only for for-each loops? No.
You can write a single method that will work with many, many methods
#### Iterator in rust:
`pub trait Iterator {`
	`type T;`
	`fn next(&mut self) -> Option<T>`
`}`

struct CountIterator {
    count : usize,
    stop : usize
}

impl Iterator for CountIter {
    type Item = usize;

    fn next(&mut self) -> Option<usize> {
        if self.curr == self.stop {
            None
        } else {
            self.curr += 1;
            Some(self.curr - 1)
        }
    }
}

struct Primes {p : usize}

fn is_prime(n : usize) -> bool {
    for x in 2..n {
        if n % x == 0 {
            return false;
        }
    }
    return true
}
  
impl Iterator for Primes {
    type Item = usize;
    
    fn next(&mut self) -> Option<usize> {
        self.p += 1;
        while !is_prime(self.p) {
            self.p += 1;
        }
        Some(self.p)
    }
}


Iterators are so useful, many Rust programmers don't write loops
`fn square(x) {x * x}
...
`let x = primes().take(100).map(square).sum()`
this is the sum of the first 100 prime numbers, square them, and add them all together

This style is powerful and useful, used in a lot of web programming


### [[Recursion]]


### HW2

make 1 change: instead of returning characters, return all the words on the board
- a word must be at least 2 characters
- we only read the board left to right. You'll need to read the board top to bottom.
- You need to move to the end of a word when you encounter one.

When iterating:
- When find char, start collecting
- collect until you find an empty square
- word MUST be 2+ chars

Make iterator collect top to bottom, not return "None" once it's finished


### RULES FOR TEST ON IMPERATIVE PROGRAMMING - can have a note sheet
- Will have 10 short-answer questions on the test
- Answer 8



### HW 3


Basically - looking over JSON data using recursion

Problem 1:
Write a function to create the "car" JSON object

Problem 2:
Write a function to find a  value in the JSON object matching the given key
If no object exists, return None

Problem 3:
