#### Satisfiability
A boolean formula is satisfiable if all of its variables can be given values such that the entire formula becomes true

Example: $\lnot(a \land b) \land a$ is satisfiable because $a = T$ and $b = F$ makes the formula true
$\lnot(A \lor b) \land a$ is unsatisfiable


#### How to represent boolean formula in prolog:
You can make up operators in prolog

```
:-op(200, fx, [~]).
:-op(300, xfx, [/\]).
:-op(400,...
...
```
Now can write expressions like `~A \/ B /\ A`
will be parsed as `\/(~(A), /\(B, A))`

Can write rules for satisfiability:
```
sat(t).
sat(A /\ B :- sat(A), sat(B).
sat(A \/ _) :- sat(A).
sat(_ \/ b) :- sat(B).
sat(A -> _) :- not(sat(A)).
sat(A -> B) :- sat(A), sat(B).
sat(~A) :- not(sat(A)).
```
using `t` and `f` because `true` and `false` having meaning


we have one more thing: force every variable to be true or false
```
set(t).
set(f).
```

Almost nothing, and we get satisfiability in Prolog

#### Equality of Expressions
Can actually check if two expressions are equal in prolog
```
?- (~A \/ X) = (Y \/ b /\ a).
X = b/\a,
Y = ~a.
```
not super impressive, but gets to how prolog works

A logic variable is a pointer that can be set to some other thing

A substitution $\sigma$ is a function from free variables to expressions.
$\sigma (X) = b \land a$
$\sigma(Y) = \lnot a$

gives us back the value we can sub in

##### Unify
Two expressions e1 and e2 unify if there exists some substitution $\sigma$ such that $\sigma(e1)$ = $\sigma(e2)$. We call $\sigma$ the unifier of e1 and e2

#### Unification algorithm
Not too complicated


What are the unifiers of:
```
append([1,2,3], [4,5], X) and append([H|T], Y, [H|Z])
	Y = [4,5], H = 1, T = [2,3], X = [1|Z]

end up with: 
append([1,2,3], [4,5], [1|Z])


perm([1,2|X],  [3,2|Y]) and perm([H|T], P)? % practice this
	H = 1, T = [2|X], P = [3,2|Y]


sat(~A \/ B /\ A) and sat(X \/ Y)
	X = ~A, Y = B /\ A
```


### Backtracking
Whenever there's a choice, I'm going to make a choice and assume it's the right choice
- if I succeed, great
- if not, undo the choice and try again
Prolog tries both

When you write a query, Prolog searches for a way to make it true
- every prolog program implicitly defines a tree
	- Root of tree is initial query (called the goal)
	- Children of a node are all the branches the node unifies with

The tree is implicit -never actually construct the tree, just to help us understand what's happening
- In prolog, we use a stack

### SLD resolution
Standard Linear Definite resolution
This is how prolog runs programs

We keep track of a stack of goals to check
- Check the first goal, find rule that matches
- Add all goals to the right hand side
- If right hand side fails, pop off the stack and try something else

Try to unify things, pick one of them, if it fail things, try again
- not a super complicated algorithm


Important to know: How unification works (give a unifier), do an SLD resolution with no variables given
- CHECK SLIDES