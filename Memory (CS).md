A place to store data - RAM, cache, Internet(kinda), hard disk(kinda)
- If a variable is being store on someone else's computer, problems will probably pop up

Everything in CS is organization
- Languages are about organizing our thoughts/algorithms
- Operating systems are about organizing our running programs
- Data structures are about organizing data

Memory is no different
Computer only sees a giant array of bytes to look up

For CS-352, everything lives in main memory (RAM)

If memory is an array, in order to read/write memory we need an index into the array - an address

a pointer is a variable that holds a memory address


In most languages it would be obnoxious to refer to memory addresses for everything
- local variables only exist within a specific region of code
- references are pointers that behave like local variables
- static variables exit throughout the duration of the program

Some memory will always be used in the program (static memory)
- global vars
- code
- libraries
Some memory changes based on where we are in the code (stack)
- local variables
- return addresses from functions
Some memory changes dynamically but persists between functions (heap)
- data structures
- file objects

Because of this, we split memory into 3 areas:

Although these categories are common, all artificial - nothing stops you from getting a pointer to your code and changing it
#### Static memory
Calculated at compile time, does not change
Holds everything we know at compile time
- eg, constant values, global variables

since code is in the memory, we should be able to get a pointer to it - a *function pointer*

you can alter your functions while your program is running, as you're able to access the function location in memory

#### The Stack
Holds local variables
- each function is in charge of managing it's section of the stack

This is more interesting, really only exists to support function calls

Every time we cann a function, it needs space to store local vars/parameters

It's also a stack

each function has a *stack frame*/*activation record*
includes: 
- parameters
- return address
- local variables
- possible pointer to previous stack frame

Order matters on stack: parameters, return address,  and then local variables

#### The Heap
Everything else that's not stack or static
- Anyone can use memory on the heap
What most people mean when they say something "lives in memory"

Usually pretty unorganized
- Can use whatever memory in the heap we want
- Can refer to heap memory anywhere

We can solve the first problem by limiting what heap memory we use

Usually we ask our language to mark out a chunk of memory for us to use

in C this is malloc and calloc
in Java it's new
In Rust this is the Box data type
- ex- `let x : Box<i32> = Box::new(4);`
- Allocates enough memory to hold an i32
- if we don't use Box then it's allocated on the stack, just like any local variable


To keep the data organized, most languages offer some way of creating new data types
- Structs in C
- Classes in Java
- Rust has structs/enums

Rust structs
`struct List {
	`item : i32,
	`next : List
`}`
#### ^^^^^DO NOT DO THIS
because no pointer is used, a List struct will need  infinite memory to be allocated at compile time


#### Memory management
Memory leak - when memory isn't free'd, the memory is inaccessible
#### 4 solutions
- Don't worry about it (C)
- Track it through smart pointers (C++)
- Garbage Collection (Java)
- Limit copying pointers (Rust)

#### Smart pointer
pointer that tracks when the memory it's pointing to can be free'd
idea is simple:
- objects keep track of how many things point to them
- when a pointer is copied, the count is updated
- when a pointer goes out of scope, the count is updated
- when the count is 0, we delete the object

The good
- easy to implement
- very fast
- easy to use

the bad
- easy to fool - circularly linked list will never be deleted

#### Garbage collection
part of the language that cleans up memory
- occasionally pauses the program
- traces all pointers in scope
- any memory that doesn't have a pointer to it is unreachable and can be free'd

The good
- Not fooled by cycles
- Invisible to use
- potentially as fast as malloc/free

The bad
- hard to implement
- inconsistent timing
	- bad for embedded programming

#### Limiting pointers
When a local variable goes out of scope, then it can be deleted

Rust extends this to the heap
- heap objects are "owned" by exactly one local variable
- when the owner goes out of scope the heap object is free'd

in Rust only ONE variable can own anything on the heap

In practice, you can never use a pointer variable twice

How to get around that?
we can borrow a reference to a heap object

The good
- very efficient
- completely deterministic
- guaranteed no memory leaks or corruption

the bad
- cryptic error messages
- hard to get used to