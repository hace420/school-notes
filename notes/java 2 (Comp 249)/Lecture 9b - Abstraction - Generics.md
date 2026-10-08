
# Abstraction
Imagine someone working on Physics engine wants to make a sound when a player hits the ground.
---> Should be able to do this without knowing any of the details of how the audio engine works.

# Generics

![[Pasted image 20260319184913.png]]
![[Pasted image 20260319184926.png]]
![[Pasted image 20260319185417.png]]

**Since Java 5 we have a large group of collection classes that solves this problem.**
**--> Today we’ll only talk about the “ArrayList” class (collection class that holds a dynamic array of some object).**

**LEARN COMPILE TIME SAFETY USING GENERICS**

## Array lists

ArrayList is a class in the standard Java libraries 

**--> Unlike arrays, which have a fixed length once they have been created, an ArrayList is an object that can grow and shrink while your program is running**

In general, an ArrayList serves the same purpose as an array, except that an ArrayList can change length while the program is running 

--> The tools for manipulating arrays consist only of the square brackets and the instance variable length
-->  ArrayLists, however, come with a selection of powerful methods that can do many of the things
for which code must be written to do them using the arrays (or using java.util.Arrays)

The ArrayList class is implemented using an array as a private instance variable

**-->  When this hidden array is full, a new larger hidden array is created, and the data is transferred to this new array**
--> An initial capacity can be specified when creating an ArrayList
--> The following code creates an ArrayList that stores objects of base type String with an initial capacity of 20 items
```
ArrayList<String> aList = new ArrayList<String>(20);
```

---> Specifying an initial capacity does not limit the size to which an ArrayList can eventually grow

**How to implement**
```
import java.util.ArrayList;

ArrayList<BaseType> aList = newArrayList<BaseType>();
ArrayList<BaseType> aList = newArrayList<BaseType>(int);

ArrayList<String> band = new ArrayList<String>();
ArrayList<Double> prices = new ArrayList<Double>(10);
ArrayList<Animal> zoo = new ArrayList<Animal>(300);
```

**if initial capacity is not defined it will be set to 10 by default also when array is full its size is increased automatically by 1.5x**

**size is actual amount of objects inside  while capacity is total available**

Predicate = method that return boolean value

![[Pasted image 20260319192005.png]]

![[Pasted image 20260319192126.png]]

