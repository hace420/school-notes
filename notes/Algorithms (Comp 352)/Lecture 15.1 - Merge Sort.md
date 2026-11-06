# Divide-and-Conquer

- Divide-and conquer is a general algorithmic design paradigm:

1. Divide: divide the input data S in two disjoint subsets S1 and S2
2. Recur: solve the subproblems associated with S1 and S2
3. Conquer: combine the solutions for S1 and S2 into a solution for

# Merge-Sort

-> Merge sort on an input sequence S with n elements consists of three steps:
1. Divide: partition S into two sequences S1 and S2 of about n2 elements each
2. Recur: recursively sort S1 and S2 
3. Conquer: merge S1 and S2 into a unique sorted sequence

#PseudoCode 
![[Pasted image 20261106102737.png]]

## Merge-Sort Tree

- An execution of merge-sort is depicted by a binary tree
- each node represents a recursive call of merge-sort and stores
	- unsorted sequence before the execution and its partition
	- sorted sequence at the end of the execution
- the root is the initial call
- the leaves are calls on subsequences of size 0 or 1
![[Pasted image 20261106102935.png]]
![[Pasted image 20261106102941.png]]


## Sorting 2 sorted arrays

> The algorithm to merge 2 sorted arrays (possibly of different sizes) can be as follows 
> NOTE: pseudo code blow uses arraylist

#PseudoCode 
![[Pasted image 20261106103045.png]]

#### Example: 
![[Pasted image 20261106103349.png]]

#Complexity 
> We compare the two current elements at the head of the two arrays (which are pointed by i & j) then insert the smaller one in the final array. 
> → Hence, actual cost is O(n1) + O(n2) , where A1 has n1 elements and A2 has n2 elements ➔ total cost is hence O(n)



# Merge-Sort vs. Heap-Sort

- Like heap-sort
1. It uses a comparator
2. It has O(n log n) running time.
	→  The cost to sort the elements at each level is O(n) and we
do that log n times


- Unlike heap-sort 
1. It does not use an auxiliary priority queue
2. It accesses data in a sequential manner (suitable to sort data on a disk)

## Summary of sorting algorithms

#Complexity 
![[Pasted image 20261106103814.png]]

