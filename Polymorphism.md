A polymorphic function is when one function can be applied to multiple types of data

3 Types of polymorphism:
- ad-hoc: give a different implementation for each type
- subtype: subclasses have different implementations for methods
- parametric: a single implementation for every type

#### Ad-hoc
```
int average(int x, int y) {
	return (x+y) / 2;
}
```

can also make a version that works with floats
```
float average(float x, float y) {
	return (x+y) / 2.0;
}
```

in C++, these are different functions

#### Subtype
 Base class defines an interface.
Subclasses provide specific implementations.
Allows for code reuse.
Example:
```
class Shape {
public:
  virtual double area() { return 0; }
};
```
	```

can even change the implementation

#### Parametric
Suppose a function that doesn't care what type it is
```
int id(int x) {
	return x;
}
```
Technically, the fact that x is an int doesn't really matter

C++, like almost every other language, lets us write one function for all types
```
template<typename T>
T id(T x) {
	return x;
}
```

Polymorphic data type implementation: 

