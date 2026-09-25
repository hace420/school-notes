
# Grow-able Array-based Stack

cont of [[Lecture 5 - Staks]]

## Comparison of the Strategies

We compare the incremental strategy and the doubling strategy by analyzing the total time T(n) needed to perform a series of n push() operations.

We assume that we start with an empty stack represented by an array of size 1.

We refer to the average time taken by a push() operations over the series of operations, i.e., T(n)/n, the amortized time of a push() operation.

### Incremental Strategy Analysis

We need to find the amortized time to perform one push() operation.
	- That is the total time to perform n push() operations / n.

In general, we need to replace the array k = n/c times for all n push() to take place.
	For instance if n = 100, and c = 4, we need to go through 25 (100/4) replacements for all push() operations to take place.
	
	Notice also that each replacement is larger than the previous one by c.


![[Pasted image 20260925102747.png]]

Since c is a constant, T(n) is O(n + k2), i.e., O(n2). That is
	 T(n) is the complexity to perform n push() operations. Hence, the amortized time of one single push() operation is O(n).

### Doubling Strategy Analysis

We replace the array k = log2 n times.
- For instance, to perform 1000 push() operations, we need to expand the
array 10 times (1 -> 2 -> 4 -> 8 -> 16 -> 32 -> 64 -> 128 -> 256 -> 512 -> 1024).

![[Pasted image 20260925103149.png]]

- Consequently, T(n) (which is needed to perform n push() operations) is O(n)
- Hence, the amortized time of a single push() operation is O(1)

end of cont [[Lecture 5 - Staks]]

# The Queue ADT

Insertions and deletions follow the first-in first-out (FIFO) scheme.

Insertions are at the rear of the queue and removals are at the front of the queue.

Main queue operations:
- enqueue(object): inserts an element at the end of the queue
- object dequeue(): removes and returns the element at the front of the queue

- object front(): returns the element at the front withoutremoving it.
- integer size(): returns the number of elements stored.
- boolean isEmpty(): indicates whether no elements are stored.
![[Pasted image 20260925104052.png]]


## Array-based Queue

- Use an array of size N in a circular fashion. 
- We can let Q[0] be the front of the queue, however this is inefficient since each dequeue() operation would result in moving all remaining elements forward.
- That is, each dequeue() operation would have a complexity of O(n)

**Instead, two variables keep track of the front and rear:**

![[Pasted image 20260925104703.png]]

Initially, we assign f = r = 0, which indicates that the queue is empty (generally f = r indicates empty queue).
Index r is kept empty. Insertion is made into Q[r] then r is incremented.

This configuration would allow enqueue(), dequeue() and front() to be performed in constant time, that is O(1)

**However, this configuration has a serious problem.**

![[Pasted image 20260925105038.png]]

### Circular array
Instead of having this normal configuration, we can let the indices f and r wrap around the end of the array.

That is view the array as a “circular array” that goes from Q[0] to Q[N - 1] then back to Q[0].

Notice that Index r is kept empty, which means that the queue can hold a maximum of N-1 elements.

![[Pasted image 20260925105147.png]]

## Queue Operations

![[Pasted image 20260925105627.png]]
![[Pasted image 20260925105645.png]]
![[Pasted image 20260925105720.png]]

## Growable Array-based Queue

Similar to what have been explained for growable array-based stack, the enqueue() operation has amortized running time of:
- **O(n) with the incremental strategy**
- **O(1) with the doubling strategy**

## Double-Ended Queues

A double-ended queue (dequeue, or D.Q.) ADT is richer than the stack ADT and the queue ADT.

It supports insertion and deletion at both ends.

Elements can only be added to or removed from the front (head) or the back (tail).

The fundamentals operations allowed by such queue are:

![[Pasted image 20260925110526.png]]
![[Pasted image 20260925110534.png]]

![[Pasted image 20260925110550.png]]