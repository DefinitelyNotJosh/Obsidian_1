### Boolean logic
This is && and || and !

mathematically using math symbols - $\land, \lor, \lnot$

"If it's raining then the sky is cloudy"
if it's raining $\rightarrow$ the sky is cloudy

"If the username is not in the database or the passwor doesn't match the username then I can't log in"

$\lnot$ username in database $\land$
...
### [[Declarative Programming]]

We give the computer logical constraints, it satisfies them


All math proofs have the form $A \land B \land ... \rightarrow P$
- Predicate in prolog
Flip it around in prolog

#### Horn Clauses
Any expression in the form 
$P \leftarrow A \land B \land ...$
is a predicate

#### Write facts and rules


## Facts
- Make a predicate and put a period at the end

```prolog
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

