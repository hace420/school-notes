
# The Stack

A running Java program maintains a private memory area called the stack, which is used to keep track of the methods as they are invoked.

# The Heap

The heap is another memory area that is maintained for a running program.

The heap is used for dynamic allocation of memory at runtime (i.e. when new is called to create an object).

Usually, the stack and the heap grow against each other in the memory.

Recursion has hence the potential of overflowing the stack by quickly consuming all available space.

# Linear Recursion

![[Pasted image 20260916104704.png]]

![[Pasted image 20260916104932.png]]

# Tail Recursion
**EVERY TAIL RECURSIVE FUNCtION IS LINEAR BUT NOT OTHER WAY AROUND **

Tail recursion occurs when a linearly recursive method makes its recursive call as its last step; as in the array reversal method.
Such methods can be easily converted to non- recursive methods (which saves on some resources)

![[Pasted image 20260916111104.png]]

# Binary Recursion

Binary recursion occurs whenever there are two, and exactly two, recursive calls for each non-base case.
Applicable, for instance, when attempting to solve two different halves of some problem.

![[Pasted image 20260916111251.png]]