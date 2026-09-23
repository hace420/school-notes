# Abstract Data Types

An abstract data type is defined indirectly, only by the operations that may be performed on it. An ADT specifies:
-  Data stored
- Operations on the data
- Error conditions associated with operations

# Stack ADT

![[Pasted image 20260923102521.png]]

## Array-based Stack

A simple way of implementing the Stack ADT uses an array.
- We add elements from left to right.
-  A variable keeps track of the index of the top element
![[Pasted image 20260923104156.png]]
![[Pasted image 20260923104215.png]]

**The array storing the stack elements may become full**
A push operation will then throw a FullStackException

### EXAMPLE
![[Pasted image 20260923104607.png]]
![[Pasted image 20260923104646.png]]
![[Pasted image 20260923104708.png]]
## Performance and Limitations

- Performance
	- Let n be the number of elements in the stack
	- The space used is O(n)
	- Each operation runs in time O(1)
- Limitations
	- The maximum size of the stack must be defined a priori and cannot be changed
	- Trying to push a new element into a full stack causes an implementation-specific exception

### Computing Spans

![[Pasted image 20260923111209.png]]

![[Pasted image 20260923111312.png]]

![[Pasted image 20260923111543.png]]



