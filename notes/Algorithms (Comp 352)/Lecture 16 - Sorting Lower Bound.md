[[Lecture 15.1 - Merge Sort]] and [[Lecture 15.2 - Quick Sort]] algorithms where O(n logn) however it can be faster.

# Bucket-Sort

- Let S be a sequence of n entries where the keys are always restricted in the range [0, N − 1], for some N >1

- *Bucket-sort does not use comparisons; instead it uses the keys as indices into an auxiliary array B of sequences (buckets).*
- The array B has cells that are indexed from 0 to  N – 1

→ An entry with key k is placed in the bucket pointed by B[k].
	- Notice that the bucket pointed by B[k] is hence a sequence of entries that have similar key k

**Phase 1:** Empty sequence S by moving each entry (k, v) into its bucket B[k].

**Phase 2:** For i = 0, …, N − 1, move the entries of bucket B[i] back to the end of sequence S.

#Complexity 
**→ Bucket-sort can sort in O(n) time;**

#PseudoCode 
![[Pasted image 20261111102858.png]]

#### Example:
![[Pasted image 20261111103103.png]]

### Extensions

- Integer keys can be in the range [a - b], which is equal in size to [0 – N-1], but not restricted to [0 – N-1]
- Simply put entry (k, v) into bucket B[k − a]
- Example: Keys are 30 to 39. Key 37 is placed in B[37 – 30]; that is B[7]

> Note: String keys can also be possible. For instance if the length of the string is the mean of sorting, and the entries have keys with lengths that are always between a minimum and maximum lengths (e.g. names of the 50 U.S. states), then strings can be used as the keys


## Stable Sorting

*→ A sorting algorithm is classified as “stable” if it preserves the original order (in the unsorted sequence) of entries with the
same keys when it forms the sorted sequence.*

> For instance, if three entries (k2, v3), (k2, v9), and (k2, v5) exist in that order in the unsorted sequences, then the final sorted sequence must also have them in that same order (k2, v3), (k2, v9), then (k2,v5)


## Lexicographic Order

*→ A d-tuple is a sequence of d keys (k1, k2, …, kd), where
key ki is said to be the i-th dimension of the tuple*

![[Pasted image 20261111104225.png]]

### Lexicographic-Sort Analysis

#Complexity 
- Lexicographic-sort sorts a sequence.
- of d-tuples in lexicographic order by executing d times algorithm stableSort, one per dimension
- Lexicographic-sort runs in O(dT(n)) time, where T(n) is the running time of stableSort
#PseudoCode 
![[Pasted image 20261111105448.png]]

#### Example:
![[Pasted image 20261111105516.png]]

## Radix-Sort

*→ Radix-sort algorithm sorts a sequence S of entries with keys
that are pairs (or generally d-tuple)*

**→ uses lexicogrpahic order**

> Radix-sort performs that simply by applying a stable bucket-sort on the sequence twice (when the keys are pairs. The application is done d times in the general d-tuple case)


#### Example:
![[Pasted image 20261111104806.png]]
![[Pasted image 20261111104955.png]]

**IMPORTANT!**
> Note: Therefore by first stably sorting by the second component and then by the first component, we guarantee that if two entries have an equal first component key (when applying the second phase of sorting), then their relative order from the first phase is preserved.


### Radix-Sort Analysis

#Complexity 
**O(d(n + N)) → this will give O(n) since d is constant **

#PseudoCode 
![[Pasted image 20261111105702.png]]


### Radix-Sort for Binary Numbers

- We represent each element as a b-tuple of integers in
the range [0, 1] and apply radix-sort with N =2

#Complexity 
*→ This application of the radix-sort algorithm runs in O(bn) time (is the same as O(n) since d is constant* 

#PseudoCode 
![[Pasted image 20261111105825.png]]


#### Example:
![[Pasted image 20261111110001.png]]


#exam 
→ question about sort on tree pick a sort method and what will be output or path


