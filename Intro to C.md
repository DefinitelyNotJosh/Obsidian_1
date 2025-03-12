
#### Java and C have a lot of similarity
- Java based on C++
- C++ based on C

## Main Difference:
- In C, performance is more important that portability and safety
- In Java, portability and safety are more important than performance

Ex: Out of bounds array access
- In java: exception thrown
- In C: It will corrupt memory, cause bizzare behavior

Ex: Order of evaluation, z = f(x) + g(x)
- Java - f(x) first
- C - f(x) may be evaluated before or after, depends on compiler

Ex: Range of values for the type int
- Java\
- C- 



Doing something in C that is illegal spits "undefined behavior"
Could be:
- Segmentation fault: an attempted memory access does not exist, or program does not have permission to access
- Bus error: an attempt to access a word of memory on a non-exact word boundary
- illegal instruction: attempt to execute a bit pattern that is not a legal encoding\
- Infinite loop - program hangs

Warning about debugging - the error of the same program and same code can change depending on the compiler
