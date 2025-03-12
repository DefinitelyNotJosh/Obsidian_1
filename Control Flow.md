#### The most fundamental form of control flow: goto
"goes to" a spot to execute code

In assembly, this is basically your only choice

Programmers invented patterns with goto's that became 'if' and 'while'

#### Structured Programming Theorem:
Any code written using gotos can be rewritten using only if and while statements

##### We came up with more control flow mechanisms:
- Branching - if, if/else, switch
- looping - while, do while, for
- functions - functions, methods, lambdas
- events: event handlers
- #### try/catch
Entirely non-local
If something goes wrong several function calls in, we might want to jump out

Can lead to some interesting patterns
```
try { 
	// big recursive function to find the best move 
	// and set a global variable called move. 
	findNextMove(board); 
	return move; 
} 
	catch(TimeoutException e) { 
	// we’re on a clock, return the move. 
	return move; 
}
```
Can be cool, but couple reasons not to do it
- Bad for readability - exceptions can jump out of several function calls, hard to tell where you came from. People also expect exceptions to be errors in OOP
- Bad for performance - have to unwind stack to find the exception handler - this is a slow process (not true in functional languages)

- #### Functions
Usually have simple control flow
- Can call a function
- Control flow jumps to that function
- when function ends, jump back

Can implement any control flow in an imperative language with functions

Callbacks underlie a lot of modern web dev frameworks

idea - user may click button in the future. Give the button a function so it knows what to do

Example:
```
QPushButton ("Click me");
connect(&button, &QPushButton:: clicked, &click_function);
...
void click_function() {
...
}
```

One use for callbacks - event handling

- write an event handling function
- register it with some object
^event handlers in Java

in reality, we put the function in some list, and there's a loop that keeps checking if an event's happened

#### Co-routines
Slightly different take on functions. Instead of one function calling another, both functions call each other
- When one function gets to a point, the control will jump back to the other function
- Used in async programming and generators in python
```
def fibs(): 
	a = 0 
	b = 1 
	while True: 
		yield b 
		(a,b) = (b,a+b) 
		
def main(): 
	for x in fibs(): 
		print(x)
```

Why are co-routines different than iterators?
- Can do them in a recursive function

```
def perms(xs,i): 
	if i == len(xs): 
		yield xs 
	for j in range(i,len(xs)):
		(xs[i],xs[j]) = (xs[j],xs[i]) 
		perms(xs,i+1) 
		(xs[i],xs[j]) = (xs[j],xs[i]) 
		
def main(): 
	for x in perms([1,2,3,4],0): 
		print(x)
```

#### Continuation

Code normally thought of like this:

code before function
f()
code after function

Idea is after we call f(), we return to the same point.

With continuations, don't return, pass the rest of the code in as a function

```

```

Never actually return, just call continuation

Almost never written by hand, but used to implement
- Exceptions
- co-routines
- compiler optimizations

#### Parameter passing

- Call by value - evaluate all args, push those values on the stack
- Call by reference - evaluate all args, push references (pointers) to those values on the stack
- Call by copy restore - call by value, but after function returns we overwrite the arguments value
- Call by name - don't evaluate args
	
note: call by reference or call by copy restore only make sense if the argument can be assigned to

```
int n = 0;
void f(int k) {
	n = n + 2;
	k = k + 3;
}
f(n);
print(n)
```

Call by value - prints 2, line 5 has no effect
Call by reference - prints 5, both k and n refer to the same thing
Call by copy restore - prints 3, line 4 executes, but n is overwritten when the function returns
Call by name - crashes, you can't assign to parameters in call by name

```
int n = 0;
voidf(int k) {
	print(k)
	n = n + 2;
	print(k)
}
f(n+1);
```

Call by value - prints 1 1, n and k have no relation
Call by name - prints 1 3, because print(k) is actually print(n+1)
