- First OOP language: simula 67 - first real OO language, has classes, objects, methods, but no class vars
- Smalltalk: widely consided a 'pure' OO language, everything is an object
- [[C++]]: combines procedural elements of C with the OOP elements of smalltalk
- [[Java]]/[[C++#]]: C++ had the right idea, but it ran way too fast.  made up for slowness by being usable
- ruby/python/javascript: "multi-paradigm" languages, OOP languages w/ commitment issues

Basic concept in OOP is a class
#### class prototype - see [[C++]]:

One of the main concepts in OOP is:
#### encapsulation
Scope sections of classes
- Public - everyone
- Protected - Only class itself or any subclass
- Private - Only class itself

General goal - all member variables are private/protected. If in doubt, make private

### [[OOP Implementation]]

### Types of Inheritance
Two reasons we may use inheritance

1. Inheritance of interface - used to create related classes that can be used interchangeably
2. Inheritance of implementation - used to reuse existing implementations of data structures and methods - generally done out of laziness, considered bad practice - ex, stack class in Java inherits from Vector, allows bypassing of stack implementation and changing values

#### [[C++]] supports inheritance of implementation with private subclasses
ex:
```
class A;
class B : private A;
```
B has all of A's fields and methods, but you can't use B as an A

### [[Type Theory]]

### [[Control Flow]]

