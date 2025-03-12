### What is a variable?
A variable is a name that represents some value

#### Name
A *name* is a symbol in a program that refers to something else

A variable has a name
functions have names
memory locations have names

#### Binding
a binding is an association of a name with a value
also called an environment, or a symbol table

Can bind names with lots of things while compiling/interpreting
- var name w/ type
- var name  w/ value
- var name w/ memory address
- memory address w/ value

Grouped by:
- compile time binding: variable with type
- link time binding: variable with memory address
	- link-time error - linker cannot combine all object files into executable program
- run time binding: memory address with value

### Scope
names and bindings are usually straightforward, until the name refers to two different things

The scope of a variable is the set of statements where the variable can be referred to
ex:
```
for i in 0..11 
{
	println!("{}", i);
}
println!("{}", i);
```
This is incorrect, as the scope of 'i' ends at the end of a loop

ex:
```
let mut n : i32 = 4;
{
	println!("{}", n);
	let mut n : i32 = 5;
	println!("{}", n);
	n = 7;
}
println!("{}", n);
```
- The scope of the first `n` is the first and third `print` statements
- Here are 2 declarations of `n` we can pick  from. We say that the `n = 5` declaration **shadows** the `n = 4` one

#### There is no correct way to do scope - it's all up to the creator of the language

Can get some problems with function scope
- Header guards protect functions from being declared twice

Do not define functions in the header file in C/C++. Only declare them, or you will get link-time errors

### Implementing Scoping
#### Environment
An environment E : Name -> Value is a function that takes a name and returns it's value

A list of pairs
Ex:
```
int i = 5;
int j = 7;
while(i < j) {
	int k = 7;
	print(n);
}
```
At first iteration, our environment is \[(i, 5), (j, 7), (k,7)]
- this program will then crash as n is not defined

##### Adding scope is easy
We have a stack of environments
Whenever a new scope is encountered, a new environment is pushed to the stack
When we leave the scope, we pop the environment off

##### When we want a variable, we search through each of the environments until we find it

### Breaking things
Lots of languages allow nested functions, breaks entire model of scoping

#### Static scoping
The scope of a variable is defined by where it is

#### Dynamic scoping:
The scope of a variable is defined by when it is executed

Almost every language uses static scoping
- very hard to do


### Lifetime
The lifetime of an object is the amount of time where an object is accessible
- Scope is about a name, lifetime about an object
- Scope is about compile time, lifetime is runtime
- Lifetime might end because a variable went out of scope

We talked about automatic memory management, this is lifetime management

Goal of lifetime management is that any object should be free'd at the end of it's lifetime

### Scope based lifetime management
In C++, when an object is free'd, it calls a destructor, which is responsible for freeing all of the memory that object was holding

Resource Acquisition is Initialization (RAII
Process of declaring objects on the stack, and having those objects manage our resources is common

Rust has the same idea, but each variable has a lifetime
When rust can prove no one else can reach that variable, it will free the object

Good because it works with things on the heap
less good because it gives an error if it can't prove lifetime consistently


When you borrow a variable, it's only within the lifetime

If you return an object in a function in Rust, you don't free it's memory, you move ownership to the caller


When you want a reference to live in a data structure, you need to give it a lifetime
This is a variable that tells rust that the reference will live long enough

```
pub struct BoardIter <’a> 
{ 
	dir : Dir , 
	row : usize , 
	col : usize , 
	board : 
	&’a Board 
}
```

#### WHAT TO KNOW:
What is the scope of a variable
what is the lifetime