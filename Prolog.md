### [[Logical  Programming]]

#### Horn Clauses

Any expression in the form 
$P \leftarrow A \land B \land ...$
is a predicate

#### Write facts and rules


## Facts
- Make a predicate and put a period at the end

```
male(harry),
male(james),
female(lily),
parent(james, harry),
parents(lily, harry)
```
Has a database of facts, harry is a male, lily is a female

Two parts to facts
#### Atom
just text

ex - harry, james, lily
#### Predicate
text with parenthesis
we write predicates as name/arity (# of arguments)
examples: male/1, female/1, parents/2

##### All atoms and predicates must start lowercase


Can ask prologs questions about the facts

#### free variable
start with a capital letter
Prolog will find every solution for the variable

parent(X,harry).
finds all possible variables
`.` automatically stops, `;` keeps on going


### Prolog code
Find all of harry's ancestors
- Define what an ancestor is
- Your parents are ancestors
- any ancestor of your parents are your ancestors
```prolog
ancestor(X,Y) :- parent(X,Y).
ancestor(X,Y) :- parent(Z,Y), ancestor(X,Z).
```

Sibling - share a same parent(s), are distinct
Grandparent(X,Y) - X is the parent of Z, Z is the parent of Y
cousin - parents are siblings
second cousin - parents are cousins

Generational difference
```prolog
ancestor(X,X,0).
ancestor(X,Y,N+1) :- parent(Z,Y,...
```

```prolog
2=1+1
false.
```

prolog doesn't automatically evaluate

```prolog
2 is 1 + 1
```
using `is` evaluates it

### LISTS
Everything in prolog is a linked list (cons list)
We write the as \[head|tail]
head is first element
tail is rest of list

```
ancestors(C,C,[]).
acestors(A,C,[P|AS]) :- parent(P,C), ancestors(A,P,AS)
```

Two people are related if they have a common ancestor
```prolog
related(X,Y) :- ancestor(A,X), ancestor(A,Y).
```
#### If you use a variable twice, it is the same variable (don't have to check if they're equal)


#### Append
append/3 concatenates two lists

```prolog
append([1,2,3],[4,5,6],X).
X = [1, 2 3, 4, 5, 6].

append(X,[3,4,5],[1,2,3,4,5]).
X=[1, 2];
false.

append(X,Y,[1,2,3,4,5]).
finds all possible ways to make X and Y true
```

append is NOT a function. It is a predicate.

```
append([[1,2,3],[4,5,6],[7,8,9]], Z).
Z = [1,2,3,4,5,6,7,8,9].

append(X,[1,2,3,4]).
```

#### Member
`next member/2` checks if something is an element of a list
First recursively
- If element is the head of the list, then it's there
- If not, check the tail
```
member(X, [X|T]).
member(X, H|T) :- member(X,T).
```
Way two:
```
member(X, L) :- append(A, [X|B], L).
```
if there's a way to make a list with free variable A and X with free variable B that is equal to L, then X is indeed a member of the list L

#### Insert
```
insert(X,T,XT) :- append(A,  B,    T),
			      append(A, [X|B], XT).

permute([],[]).
permute([H|T],P):- permute(T,PT),
				   insert(H,PT,P).

sorted([]).
sorted([X]).
sorted([X,Y|Z]) :- X =< Y, sorted([Y|Z]).
```
^ permSort
