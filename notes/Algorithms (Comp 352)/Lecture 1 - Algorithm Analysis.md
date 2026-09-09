# Efficiency

**--> How to estimate : Ignore various restrictions; i.e:**
◼ CPU speed
◼ Memory limits; for instance allow an int variable to take any allowed integer value, and allow arrays to be arbitrarily large.

Since the method is now unrelated to specific computer environment, we refer to it as algorithm.

1. Consider the number of executed statements, in a trace of the algorithm, as a measurement of running-time requirement.
2. This measurement can be represented as function of the “size” of the problem.
3. The running time of an algorithm typically grows with the input size.
4. We focus on the worst case of running time since this is crucial to many applications such as games, finance,robotics, etc.
5. Given a method of a problem of size n, findworstTime(n) , which is the maximum number of executed statements in a trace, considering all possible parameters/input values.

**EXAMPLE**
Assume an array a [0 … n] of int, and assume the following trace:

``for (int i = 0; i < n - 1; i++)
``if (a [i] > a [i + 1])
``System.out.println (i);

What is worstTime(n)?

![[Pasted image 20260909111000.png]]

# Pseudocode
![[Pasted image 20260909112155.png]]
![[Pasted image 20260909112218.png]]

# Important functions

![[Pasted image 20260909112330.png]]