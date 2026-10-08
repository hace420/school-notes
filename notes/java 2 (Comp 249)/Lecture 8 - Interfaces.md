# Intro
Usually used common characteristics of otherwise unrelated objects

- ex: Integer, Double, Fraction, Polynomial… **can all be compared** using compareTo()
-  ex: Shoe, Telephone, Desk… **can all be sold in a store** using computeTax(), getInventory(),..
-  ex: Car, Lawnmower, Boat… **can all have engines** using consumeFuel(), boastEngine(), …

--> **Two types of interfaces**

- built-in: Comparable, Serializable, Cloneable …
- programmer defined
![[Pasted image 20260312182204.png]]


**MAIN CONCEPT**
---> The single responsibility principle is a computer programming principle that states that every module or class should have responsibility over a single part of the functionality provided
by the software, and that responsibility should be entirely encapsulated by the class

**note : Fields declared in an interface are implicitly public, final and static. An interface’s header only  method headers are implicitly public abstract.**

Remember that all of the methods whose headers are declared in the interface are implicitly declared public. If you forget to include public in the implemented method's declaration, the compiler will report an error informing you that you’re attempting to assign weaker access to the implemented method.
![[Pasted image 20260312192321.png]]
![[Pasted image 20260312190658.png]]

# Lists

**ArrayList** is a class that describes an array-based implementation of the List Java interface.

```
List names = new ArrayList<>()
void print(List names)
{
// ...
}
```

**Linked List** 
The client code will not interact directly with ArrayList. As a result, the client code will not break when a different implementation class, such as LinkedList, is required: 

```
List names = new LinkedList<>()
void print(List names)
{
// ...
}
```

![[Pasted image 20260312184335.png]]

# example of interface implementation

![[Pasted image 20260312185113.png]]
![[Pasted image 20260312184714.png]]
![[Pasted image 20260312184725.png]]
![[Pasted image 20260312190833.png]]


# Polymorphism via interface
similar to [[Lecture 4 - Polymorphism]] and [[Lecture 5a - Polymorphism part 2]]


# Selection Sort
![[Pasted image 20260312190923.png]]
