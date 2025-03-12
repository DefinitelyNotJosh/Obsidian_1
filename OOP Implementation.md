### How to express objects in the memory
```
class Foo {
	int x;
	int y;
	boolean c;
	double d;
}
```
Any object type `Foo` will point to somewhere in memory, that area in memory will have space for 2 ints, a boolean, and a double

remember - memory is just a huge array of bytes, all objects live in those bytes

In C, the struct will keep values in the same order
C++ is free to rearrange the order of fields. Why?

Struct packing
\[int, short, short, double]
is more efficient than
\[int, short, double, short]

because all values in memory have to be word-aligned - all objects have to  start on a multiple of 8 bytes
- Java does this automatically
- Rust can do this
- you can do this in C++

Bottom line - use structs the way the language intended - being clever with pointers can cause problems

#### What about methods?
A function is just a label in assembly - it lives in memory, it has an address

Suppose we have the object
```
class Checker {
public:
	virtual void move(Square);
	virtual void capture(Square);
	virtual void kingMe(Square);
}:
```
We can make a table with all of these methods
```
void* CheckerTable[] = { &&move,
						 &&capture,
						 && kingMe };
```

calling a method is jumping to that method in your method table

In general write method tables as:

| Class            |
| ---------------- |
| Class::Method1() |
| Class::Method2() |
| Class::Method3() |

Great, but missing inheritance

```
class GamePiece
{
public:
	virtual int side();
	virtual int numTurns();
};

class Checker : public GamePiece
{
public:
	int numTurns();
	void move(Square);
	void capture(Square);
	void kingMe(Square);
}
```

#### Currently, the method table of Checker does not have 'side()'

#### One option: Prototype Inheritance
Each object has a pointer to it's parent class - what Java does
in practice - Checker doesn't have the method, check parent class GamePiece method table, find it, use it
- Downside - searching through method tables takes resources and is slow
	- O(N) in depth of inheritance tree - very inefficient
	- Doesn't deal with dynamic dispatch well

#### Better option - Each object has ALL of it's parents methods in it's method table
If an object overrides a method, then we overwrite it in the method table

Better in pretty much every way
- No need to search
- no need for pointer to parent
- all methods are constant time
- dynamic dispatch is free
This is the virtual method table

For any of this to wok, subclasses need to have the same methods in the same order in the table

C++ does this

Method table ends up being:

| Checker                  |
| ------------------------ |
| GamePiece::side()        |
| Checker::numTurns()      |
| Checker::move(Square)    |
| Checker::capture(Square) |
| Checker::kingMe(Square)  |
#### Important points:
Methods are in the same order - code correctly
If we override a method, we override the entry in the table

#### This method doesn't work for interfaces
We don't know how many interfaces a class will implement
- Can't look in a single place for interface methods

For ~20 years, interfaces were assumed to be inherently slow

Now we have a better strategy:
Throw them in a hashset
- unlikely two methods will conflict
- constant(ish) time lookup
- works with multiple interfaces

Aside from interfaces few other ways to implement OOP concepts
Javascript has prototype inheritance
Every object has a prototype tat holds all of the fields and methods

If B inherits from A, then B's prototype will point to A's prototype

This means to look up a field or method, you have to look through a linked list
- not ideal

Python uses a system called "duck typing," aka dynamic typing
- Python doesn't do type checking
- Every object is a hash map
- All fields and methods are entries in the hash map

If you call a method, python looks up the name in the hash map, and runs whatever's there

All inheritance in Python is inheritance of implementation, not inheritance of interface

Rust and Swift both use an idea of traits
- a lot like interfaces, but can have default methods
- Traits usually implemented with a traits object that will hold the method table

[[Haskell]] uses type classes. Again, very similar to traits and interfaces

However, can't implement anything on a type class, and are passed to the calling function statically

A type class is more like a constraint

Whatever function implements this type class will have these functions available