Like C with classes
has some nice features we can use
Things get less tedious
### [[Object Oriented Programming]]

### [[OOP Implementation]]


#### www.cppreference.com
^ C++ documentation

#### Differences between C++ and C
- C++ is an OOP language, like Java
- Streams
- References
- Templates

Declare classes usually in .h files like Java:
```
# Example of a declaration
class Animal 
{
	private: // <- private block
		string _name;
		string _says;

	public: // <- public block
		Animal (); // constructor - must be same name as class
	
		string says(); 
		void describe();
}; // <- don't forget the semicolon
```

In C++, structs and classes are essentially the same, but classes are structs that are private by default instead of public

- Classes and methods declared in the .h file, implementations in the .cpp file
- Mark public and private sections of a class, don't pick for each variable
- The constructor is *just* the class name, it has no return type

Can construct an object in 2 ways:
```
Animal* pet1 = new Animal() // <- MUST BE A POINTER, lives on heap
Animal pet2(); // <- lives on stack, auto free'd when out of scope
delete pet1; // <- if you make on object on the heap, must free using delete
```

How to implement a class:
```
Animal::Animal()
{
	_name = "animal"; 
	_says = "Yes, I am animal ."; 
}
string Animal::says()
{
	return _says;
}
void Animal::describe() 
{
	cout << "The " << _name << ” says " << says() << endl ;
}
```

### C++ does stream based I/O
## Streams
Anything that be written or read from

C++ `stdout` and `stdin` are streams
have their own special objects` cout` and `cin`

`cout << var`
will print `var` to` stdout`

Many classes can be printed this way

`<<` - overload operator, sort of like toString() in Java
- Can think of it like string concatenation, it just adds the thing after it to stdout

`cout << endl;`
`endl` prints a new line and flushes the stream buffer - can also use `flush` if you don't want to print a new line


`cin` stream is an input stream, it will read from standard in and attempt to write the contents to a variable

#### `cin` with strings:
```
string test; 
cout << ”enter a string :” << endl; 
cin >> test;
```
`cin` reads until the next white space, if "Hello World" is written, test has "Hello" written to it

`cin` attempts to do lexing for us
If you write to an int, it will try to read the next int
If you write a float it will try to read the next float
If you write to a string, it will try to read the next word
- It's smart about how it does it - skips white space before and after the word

Does take control away, but is usually what we want from stdin

#### Two things to check when getting user input:
- Anything go wrong? - `cin.good()`
- End of file? - `cin.eof()`

or can check both with:
```
if(cin)
```
C++ will auto convert `cin` to a bool
- returns true if and only if `cin` has not had an error reading from stdin

Convenient idiom for reading input:
```
string input;
while(cin >> input) {
	...
}
```
Common pattern for reading a whole file
change type of input as desired, example `int`
- Doesn't work well for reading one line at a time

Can use 
`if(!cin)`
to see if `cin` is still valid

### References
If I want to return more than one piece of information from a function, I can pass in arguments as pointers, and have C++ fill  them in

The pattern is so common, C++ made it part of the syntax

Definition:
In a function, a *reference* parameter is a parameter where the address is passed instead of the value being copied

Can write the lex function as 
```
void readArray(int* array, int& numberRead);
```
`numberRead` behaves like any other integer, but if I assign to it during the function, its value will change after I return

```
void foo(int& x) {
	x = ...;
}
// is the same as
void foo(int* x) {
	*x = ...;
}
```

When you pass an object by reference, you don't need to copy the entire object

Notice we use '.' for accessing fields, not '->'
### [[Polymorphism]]


#### Constructor
```
class ChessPiece {... };

ChessPiece::
```


#### Virtual
Can inherit from method and overwrite. If not made virtual in C++, cannot overwrite - java does this automatically
```
class ChessPiece
{
	...
	virtual void move(Position newPos);
};


```
Only need to use "virtual" in parent classes, technically not necessary in leaf/child classes


#### Create object
inheritance does not work unless you make it on the stack using new
```
ChessPiece* p = new ChessPiece(Position(1,4));
p->move(Position(2,4));-----------?

```

Most C++ classes declared in a .h file

Common to name file after the class

If making a template class, it must be declared and defined in the .h file


### Inheritance
": public" is the same as "extends"
```
class Pawn : public ChessPiece {
	Pawn(Position initPos)
}
...
Pawn::Pawn(Position initPos) : ChessPiece(initPos) {}
...
ChessPiece* p1 = new Pawn(Position(1,4));
p1->move---------------?
```

#### Difference between method and function

```
class ChessPiece {
	virtual void move(Position);
}
class Pawn : public ChessPiece {
	virtual void move(Position);
}

void move(ChessPiece* p, Position pos);

void move(Pawn* p, Position pos);
```

Are these the same? No

Compiler defaults to declared type when using a function, so if there's a pawn object and a chess piece object, if the pawn was declared as a chess piece, the compiler will view it as a function. A method uses 

#### Dynamic Dispatch
is the process for deciding what method to call at run-time instead of compile time
Only happens if P is a pointer

Sometimes we *only* want dynamic dispatch
For example, if you have an Expr class
- don't want to actually make an Expr
- Want an Add or Lit

In java, abstract
In C++, pure virtual method in a class
```
class Expr {
public:
	virtual Type* typecheck(...) = 0;
	virtual Expr* eval(...) = 0;
};
```

#### With inheritance and Dynamic Dispatch, we have a new way to do [[Polymorphism]]

Suppose:
```
ChessPiece* p = ...;
p->move(...);
```
p can be any class that inherits from ChessPiece
It will call the appropriate method every time

How does the compiler know which method to call?

Each object has a method table - an array of pointers to code where the method is
compiler says, "p, jump to method move()"




Example:
```
class A {
	virtual void print(int x) {
		cout << "A" << endl;
	}
};
class B : public A {
	virtual void print(bool x) {
		cout << "B" << endl;
	}
};
int main() {
	A* b = new B();
	b->print(false);
}
```
Function prints "A"