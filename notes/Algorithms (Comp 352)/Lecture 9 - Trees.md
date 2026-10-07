# Terminology

- Root: node without parent (A) Internal node: node with at least one child (A, B, C, F)
- External node (leaf ): node without children (E, I, J, K, G, H, D)
- Ancestors of a node: parent, grandparent, grand-grandparent, etc.
- Depth of a node: number of ancestors
- Height of a tree: maximum depth of any node (3, in the shown tree
- Descendant of a node: child, grandchild, grand-grandchild, etc
- siblings: Two nodes that are children of the same parent
- edge: an edge of a tree is a pair of nodes (u, v), where u is the parent and v is the child, or vise versa. In other words, an edge is a connection between a parent and aE child in the tree(does not need to be on the outside f and j are edges)
- Path: a sequence of nodes such that any two consecutive nodes in the sequence form an edge (for instance: A, B, F, J).

![[Pasted image 20261007103311.png]]

# Methods

>***We can use positions to abstract nodes. Positions of a tree are its nodes. The terms “position” and “node” is hence used interchangeably. A position object support the following method:***

```
element(): Return the object stored in the position
```

**Generic methods:**

```
integer size(): Return the number of nodes in the tree.

boolean isEmpty(): Tests whether or not the tree has nodes.

Iterator iterator(): Return an iterator of all the elements stored at
nodes of the tree.

Iterable positions(): Return an iterable collection of all the nodes
of the tree.
```

**Accessor methods:**

```
position root(): Return the “root” of tree; error if tree is empty.

position parent(p): Return the parent of p; error if p is the root.

Iterable children(p): Return an iterable collection containing all
the children of node p.
```

Note:
 >If the tree is ordered, then the iterable collection returned by children(p) stores the children of p in order.
   if p is a leaf, then the returned collection is empty 

**Query methods:**

```
boolean isInternal(p): Tests whether node p is internal .

boolean isExternal(p ): Tests whether node p is external.

boolean isRoot(p): Tests whether node p is the root.
```

**Update method:**

```
element replace (p, e): Replace the element at node p with e and
return the original (old) element.
```

## Performance of methods

![[Pasted image 20261007105304.png]]


# Traversal

## Preorder Traversal

![[Pasted image 20261007105435.png]]
***---> to traverse go from 1 to 9***                         ![[Pasted image 20261007110512.png]]

## Postorder Traversal

**In a postorder traversal, a node is visited after its descendants** 
**Application: compute space used by files in a directory and its subdirectories**

![[Pasted image 20261007110632.png]]
![[Pasted image 20261007110642.png]]

# Binary Trees
![[Pasted image 20261007110948.png]]

> Each internal node has at most two children (exactly two for proper binary trees; otherwise the tree is improper )

## Arithmetic Expression Tree

![[Pasted image 20261007111058.png]]

> Binary tree associated with an arithmetic expression is a proper binary tree where:
    - internal nodes: operators
	- external nodes: operands

## Properties of Proper Binary Trees

#### Notation

**n =  number of nodes**
**e = number of external nodes**
**i = number of internal nodes**
**h = height**

#### Properties
![[Pasted image 20261007111324.png]] ![[Pasted image 20261007111409.png]]


# BinaryTree ADT

>***The BinaryTree ADT extends the Tree ADT, i.e., it inherits all the methods of the Tree ADT***

**Additional methods:**
```
position left(p): Return the left child of p; error if p has no left child

position right(p): Return the right child of p; error if p has no right child

boolean hasLeft(p): Test whether p has a left child

boolean hasRight(p): Test whether p has a right child
```


