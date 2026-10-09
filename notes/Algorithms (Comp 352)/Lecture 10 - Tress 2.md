

# [[Lecture 9 - Trees#BinaryTree ADT|Part 2 of binary tress adt]]

## Inorder Traversal of Binary Trees

 ***In an inorder traversal a node is visited after its left subtree and before its right subtree***

![[Pasted image 20261009102556.png]]

> **Example for inorder traversal is printing arithmetic expressions: 
> ((2 x (a − 1)) + (3 x b))
---

![[Pasted image 20261009102937.png]]     ![[Pasted image 20261009102947.png]]

# Euler Tour Traversal

- All previously discussed traversal algorithms are forms of iterators where each traversal is guaranteed to visit each node in a certain order, and exactly once.
- Euler Tour traversal relaxes that requirement of the single visit to each node.
- The advantage of such algorithms is to allow for more general kinds of algorithms to be expressed easily

***Euler Tour traversals walks around the tree and visit each node three times

```
on the left (preorder – root → left → right)
from below (inorder – left → root → right)
on the right (postorder – left → right → root)
```

- If the node is external, all three visits actually happen at the same time.

Example of traversal below showing external is visited 3 times in a row.

![[Pasted image 20261009104429.png]] 
### Complexity

- ***Since we spend a constant time at each node, the overall running time is O(n)***

# Linked Structure for General Trees (tree implementation)

- A node is represented by an object storing
	- Element
	- Parent node
	- Sequence of children nodes
Node objects implement the Position ADT

![[Pasted image 20261009104710.png]]
![[Pasted image 20261009104724.png]]

# Linked Structure for Binary Trees

- A node is represented by an object storing
	- Element
	- Parent node
	- left child node 
	- right child node
![[Pasted image 20261009104921.png]]
![[Pasted image 20261009104932.png]]


## Performance of List Implementation of Binary Trees

#Complexity
![[Pasted image 20261009105001.png]]

# Array-Based Representation of Binary Trees

- Node v is stored at A[rank(v)]
- rank(root) = 0
- if node is the left child of parent(node), rank(node) = 2rank(parent(node))+1
- if node is the right child of parent(node),rank(node) = 2rank(parent(node)) + 2

![[Pasted image 20261009105242.png]]![[Pasted image 20261009105304.png]]

```
So, in general; for any parent/root at rank i

	the left child is at rank 2i + 1
	the right child is at rank 2i + 2
	links between nodes are not explicitly stored
```


> ***NOTE 7 8 are going to be null in this example because 5 and 6 have no child and 4 has 2 child and 2(4) + 1 = 9 and 2(4) + 2  = 10

## Performance of Array-based Implementation of Binary Tree

#Complexity 
![[Pasted image 20261009105639.png]]


# Template Method Pattern

![[Pasted image 20261009105825.png]]

- A TourResult object with fields left, right and out keeps track of  the output of the recursive calls to eulerTour

### Specializations

![[Pasted image 20261009110023.png]]

***ASSUMPTIONS***

>--> Nodes store ExpressionTerm objects with method getValue
>--> ExpressionVariable objects at external nodes
>--> ExpressionOperator objects at internal nodes with method setOperands(Integer, Interger)






