# Priority Queue ADT

- A key can be used to indicate the priority of a value (p.s. value means an element here).
- Each entry in the P.Q. is hence a pair of (key, value)

***METHODS***
```
MAIN:
insert(k, x): insert an entry with key k and value x into PQ, and
return the entry storing them

removeMin(): remove and returns the entry with smallest key
(smallest key indicates first priority).


ADDITIONAL
min(): return the entry with smallest key, but do not remove it
size(),
isEmpty()
getKey(): returns key
getValue(): returns value


```

![[Pasted image 20261021103008.png]]

# Total Order Relations

![[Pasted image 20261021103832.png]]

# Comparator ADT

- It is possible to have comparable objects by implementing the java.lang.Comparable interface.java.lang.Comparable
- The problem with such approach however is that there are cases where the keys will be required to provide more information than they should/expected to, such as their comparison rules.

- Instead, we can use special comparator objects that are external to the keys to supply the comparison rules.
- A comparator encapsulates the action of comparing two objects according to a given total order relation.
![[Pasted image 20261021104042.png]]

# Priority Queue Sorting

- We can use a priority queue to sort a set of comparable elements
	1. Insert the elements one by one with a series of insert operations
	2. Remove the elements in sorted order with a series of removeMin operations
- The running time of this sorting method depends on the priority queue implementation

![[Pasted image 20261021104343.png]]


## Sequence-based Priority Queue

#### Implementation with an unsorted list
![[Pasted image 20261021104814.png]]

Performance:
- insert takes O(1) time since we can insert the item at the beginning or end of the sequence 
- removeMin and min take O(n) time since we have to traverse the entire sequence to find the smallest key
##### Sorted List

![[Pasted image 20261021105003.png]]

# Selection-Sort

- Find the minimum value in the collection (list/sequence, P.Q., etc.)
- Swap it with the value in the first position
- Repeat the steps above for the remainder of the list (starting at the second position and advancing each time)

***(First loop): Inserting the elements into the priority queue with n insert operations takes O(n) time***

***(Second loop) Removing the elements in sorted order(repeated seclection) from the priority queue with n removeMin operations takes time proportional to***
![[Pasted image 20261021105211.png]]

# Insertion-Sort

- Removes an element (possibly arbitrary) from the input data
- Insert the element into the correct position in the already-sorted list
- Repeat until no input elements remain

***(First loop): Inserting the elements into the priority queue with n insert operations takes time proportional to 1 + 2 + …+ n***

***(Second loop): Removing the elements in sorted order from the priority queue with a series of n removeMin operations takes O(n) time***

***Resulting in a total of O(n2+ n) ➔ O(n2) 
➔ Insertion-sort runs in O(n2) time***

#### Special case

![[Pasted image 20261021105521.png]]

# In-place Insertion-Sort

- Instead of using an external data structure, we can implement selection-sort and insertion-sort in-place 
- A portion of the input sequence itself serves as the priority queue

- We keep sorted the initial portion of the sequence
- We can use swaps instead of modifying the sequence

![[Pasted image 20261021105657.png]]

