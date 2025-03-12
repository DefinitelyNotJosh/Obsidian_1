#### Order matters. The order of function calling will effect the output of the function

A  function $f$ is recursive if the body of $f$ calls itself

All recursive functions have at least 2 cases:
- Base case - does not contain a call to $f$
- Recursive case - contains at least 1 call to $f$

Base case usually comes first

ex:
`fn fac(n : i32) -> i32 {`
	`if n == 0 {`
		`return 1;`
	`}`
	`else {
		`return n * fac(n-1)
	`}`
`}`

Recursion occurs in lots of different forms - eg, circuits, geometry (Sierpinski triangle)

#### To solve a recursive problem:
- Solve the simplest case
- Reduce our problem to a smaller one
- make sure our smaller problem is actually smaller

There's a mental trick to getting recursive problems: once we've reduced our problem to a smaller problem, we assume our solution will work, and it usually does

ex:
`fn two_to_the(n : i32) -> i32 {
	`if n == 0 {
		`return 1;
	`}
	`else {
		`return 2 * two_to_the(n-1);
	`}
`}`

I don't know how to compute two_to_the(n-1) - and I don't care. As long as the function works, it doesn't matter.

### Recursive file tree:
`enum FileTree {
	`File(String, usize),
	`Dir(String, Vec<FileTree>`)
`}`

To find the total size of a file, I need to go find the size of every file in it

Recursion.
Case 1: A file knows its size
Case 2: The size of the directory is the size of everything in it

A Linked list is either empty *Nil* or it contains an element and another Linked List

`enum list<T> {
	`Nil,
	`Cons(T)
}`

Case 1: empty list has 0 nodes
Case 2: A Cons list has 1 node, and however many noes are in the tail

### Binary Tree
A Binary Tree is either a Leaf with a single value, or its a branch with a value, left, and right subtree

`enum Tree<t> {
	`Leaf(T),
	`Branch(T,Box<Tree<T>>, Box<Tree<T>>)
`}`

`fn count<T>(tree : Box<Tree<T>>) -> usize {
    `match *tree {
        `Leaf(x)              => {return 1;}
        `Branch(x,left,right) => {return 1 + count(left) + count(right);}
    `}
`}`

#### Look back at [[Abstract Syntax Trees (AST)]]

how do we evaluate an Exp?
- The value of a number is the number
- To get the value of an operation, we get the value of the children
