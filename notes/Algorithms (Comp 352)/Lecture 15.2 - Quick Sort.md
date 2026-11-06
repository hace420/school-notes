→ Quick-sort is a randomized sorting algorithm based
on the divide-and-conquer paradigm:

1. Divide: pick a random element x (called pivot) and partition S into
	→ L elements less than x
	→ E elements equal x
	→ G elements greater than x
	
2. Recur: sort L and G
3. Conquer: join L, E and

![[Pasted image 20261106104046.png]]

## Partition

#Complexity 
→ We partition an input sequence as follows:
- We remove, in turn, each element y from S and
- We insert y into L, E or G, depending on the result of the comparison with the pivot x 
- Each insertion and removal is at the beginning or at the end of a sequence, and hence takes O(1) time 
- Thus, the partition step of quick-sort takes O(n) time

#PseudoCode 
![[Pasted image 20261106104307.png]]


## Quick-Sort Tree

> **IN THIS EXAMPLE: PIVOT IS 50**


![[Pasted image 20261106104500.png]]![[Pasted image 20261106104541.png]]

## Worst-case Running Time

- The worst case for quick-sort occurs when the pivot is the unique minimum or maximum element
- One of L and G has size n − 1 and the other has size 0 
- The amount or work done at any depth proportional to the number of nodes at that depth. Hence, the running time in that case is proportional to the sum
- 
                  ![[Pasted image 20261106104800.png]]
#Complexity 
> **Thus, the worst-case running time of quick-sort is O(n2)**


## Expected Running Time

> Consider a recursive call of quick-sort on a sequence of size s

→ *Good call:* the sizes of L and G are each less than 3s/4
→ *Bad call:* one of L and G has size greater than 3s/4

![[Pasted image 20261106105020.png]]

![[Pasted image 20261106105046.png]]

#Complexity 
**→ Thus, the expected running time of quick-sort is O(n logn)**


## In-Place Partitioning

![[Pasted image 20261106105240.png]]

- Repeat until j and k cross:
- Scan j to the right until finding an element > x.
- Scan k to the left until finding an element < x.
- Swap elements at indices j and k


![[Pasted image 20261106105319.png]]

# Summary

#Complexity 
![[Pasted image 20261106105339.png]]


