# Counting primitive operations

By inspecting the pseudocode, we can determine the maximum number of primitive operations executed by an algorithm, as a function of the input size.

![[Pasted image 20260911102303.png]]

# Estimating running time

Algorithm compareValues executes 4n − 4 primitive operations in the worst case.
 Define:
a = Time taken by the fastest primitive operation
b = Time taken by the slowest primitive operation
Let T(n) be the running time of compareValues.
Then
a (4n − 4) <= T(n) <= b(4n − 4)
---> Hence, the running time T(n) is bounded by two linear functions
![[Pasted image 20260911102845.png]]

# BIG O Notation

- The basic idea is to determine an upper bound for the behavior of the algorithm/function.

- In other words, to determine how bad the performance of the algorithm can get!

- If some function g(n) is an upper bound of function f(n), then we say that f(n) is Big-O of g(n).
- Specifically, Big-O is defined as follows: Given functions f(n) and g(n), we say that f(n) is O(g(n)) if there are positive constants c and n0 such that
- ![[Pasted image 20260911103738.png]]
- The idea is that if f(n) is O(g(n)) then it is bounded above (cannot get bigger than) some constant times g(n).
**!!!EXAMPLE DONE IN NOTEBOOK!!!**
![[Pasted image 20260911105805.png]]

# Big O Hierarchy

![[Pasted image 20260911105616.png]]

# Estimates 
![[Pasted image 20260911110731.png]]

![[Pasted image 20260911110753.png]]

![[Pasted image 20260911110917.png]]

![[Pasted image 20260911111003.png]]

![[Pasted image 20260911111023.png]]

![[Pasted image 20260911111049.png]]

# Asymptotic Algorithm Analysis

To perform the asymptotic analysis

- We find the worst-case number of primitive operations executed as a function of the input size
-  We then express this function with big-O notation

# BIG OMEGA

**While Big-O provides an upper bound of a function, Big-Omega provides a lower bound.**
**In other words, while Big-O indicates that an algorithm behavior “cannot be any worse than”, Big- Omega indicates that it “cannot be any better than”.**

Big-Omega is defined as follows: Given functions f(n) and g(n), we say that f(n) is OMega(g(n)) if there are positive constants c and n0 such that

![[Pasted image 20260911111533.png]]

**!!!EXAMPLE DONE IN NOTEBOOK>!!!**

# Big THETA

Big-Theta is defined as follows: Given functions f(n) and g(n), we say that f(n) is theta(g(n)) if there are positive constants c1, c2 and n0 such that
![[Pasted image 20260911112148.png]]


# Plain English

![[Pasted image 20260911112318.png]]


![[Pasted image 20260911112608.png]]