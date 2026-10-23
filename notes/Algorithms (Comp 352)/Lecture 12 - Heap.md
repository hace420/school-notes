
- Both insertion-sort and selection-sort of P.Q. achieved running time of O(n2)

- Fundamentally, the heap achieves such improvement by abandoning the idea of storing entries in a list; instead it stores the entries in a binary tree

## Properties to be heap

1. Heap-Order: for every internal  node v other than the root , **key(v) >= key(parent(v))**
	- Additionally, the minimum key (which is the most important  one) is hence always stored at the root (or the “top of the heap”, hence the name “heap” of this data structure).
	
2. Complete Binary Tree: let h be the height of the heap
	-  for i = 0, … , h − 1, there are 2^i nodes of depth i
	- at depth h − 1, the internal nodes are to the left of the external nodes
	- there is at most one node with one child (only one node can have a single child) and this child must be a left child
	- Another important node is the last node. This is the right-most, deepest external node in the tree 
![[Pasted image 20261023102842.png]]

> If we want to add to this tree we need to know last node because the next "branch" of tree will have to be under (20,b)


#### Height of heap Theorem

- **Theorem: A heap storing n keys has height O(logn)**

## Insertion

- Method insert(k, x) of the priority queue ADT corresponds to the insertion of a key k to the heap

3 Steps:
1. Find the insertion node z (the new last node)
2. Store k at z
3. Restore the heap-order property

## Upheap

- Algorithm upheap restores the heap-order property by swapping k along an upward path from the insertion node
- Upheap terminates when the key k reaches the root or a node whose parent has a key smaller than or equal to k.
- ***Since a heap has height O(log n), upheap runs in O(log n)***
![[Pasted image 20261023103507.png]]


## Removing elements of heap

4 Steps:
1. Return root entry
2. replace root key(Entry in fact) with the key of the last node w
3. remove w
4. restore the heap-order property
![[Pasted image 20261023104114.png]]


## Downheap (after removal)

- Downheap terminates when key k reaches a leaf or a node whose children have keys greater than or equal to k
- Since a heap has height O(log n), downheap runs in O(logn)
![[Pasted image 20261023104444.png]]


## Updating last node

- The insertion node can be found by traversing a path of O(log n) nodes

- For instance, if the current last node is a left child then:
	- Go up to the father and down right to the new last node

- If the current last node is a right child then:
	- Go up until a left child or the root is reached
	- If a left child is reached, go to the right child
	- Go down left until a leaf is reached
![[Pasted image 20261023104656.png]]

## Performance
#Complexity 
![[Pasted image 20261023104716.png]]


## Heap-Sort

#Complexity 
- Consequently, the entire algorithm consumes O(n logn) time to have n insertions in phase I (first loop), and O(n log n) time to have n removals in phase II (second loop) which leads to a final complexity of O(n log n )
![[Pasted image 20261023105450.png]]

## Array-Based Implementation

![[Pasted image 20261023105526.png]]

## Merging heaps

- We are given two heaps and a key k
- We create a new heap with the root node storing k and with the two heaps as subtrees
- We perform downheap to restore the heap- order property
![[Pasted image 20261023105628.png]]

## Bottom-up Heap Construction

- It is possible to construct a heap in o(n log n) time.

- Simply, perform n successive insertions.
	-  Since worst case for any of these insertions is log n, the total time consumption is O(n log n).

-  However, if all the entries (that is all the key-value pairs) are known and given in advance, we can have an alternative approach that results only on a complexity of O(n)

#### Example: 

Keys: 16, 15, 4, 12, 6, 9, 23, 20, 25, 5, 11, 27, 7, 8, 10
n = 15
h = 3 
![[Pasted image 20261023110023.png]]

> 1. Divide keys in half then place those half in bottom
> 2. Then take 1/4 and add to second row

![[Pasted image 20261023110124.png]]

> 3. Then take 2 out of 3 left add to next row
> 4. last number is root for now

![[Pasted image 20261023110208.png]]

> 5. Downheap to make tree follow properties required


> Called bottom up since step one we start at bottom
> Using this method construction runs in O(n)
> Bottom-up heap construction (while does not change the general complexity of heap-sort), it speeds up the first phase of the algorithm








