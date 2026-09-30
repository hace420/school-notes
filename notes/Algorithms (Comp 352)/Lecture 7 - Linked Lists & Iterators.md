# Singly Linked List
covered in [[Lecture 10b - Linked data Structures]]

![[Pasted image 20260930102806.png]]


## Insert at head

1. Allocate a new node
2. Insert new element
3. Have new node point to old head
4. Update head to point to new node

## Removing at the Head

1. Update head to point to next node in the list
2. Allow garbage collector to reclaim the former first node

## Inserting at the Tail

1. Allocate a new node
2. Insert new element
3. Have new node point to null
4. Have old last node point to new node
5. Update tail to point to new node

## Removing at the Tail

- Removing at the tail of a singly linked list is not efficient!
- There is no constant-time way to update the tail to point to the previous node

---
# Stack as a Linked List

- We can implement a stack with a singly linked list
- The top element is stored at the first node of the list
- The space used is O(n) and each operation of the Stack ADT takes O(1) time
![[Pasted image 20260930104245.png]] 
# Queue as a Linked List

- We can implement a queue with a singly linked list
	- The front element is stored at the first node
	-  The rear element is stored at the last node
- The space used is O(n) and each operation of the Queue ADT takes O(1) time **(assuming that both head and rear are pointed to!)**


![[Pasted image 20260930104939.png]]

---

# Doubly Linked List

![[Pasted image 20260930105105.png]]

- Nodes implement Position and store
	- element
	- link to previous node
	- link to next node
- Special sentinel/dummy trailer and header nodes (simplify implementation)

![[Pasted image 20260930105224.png]]


## Insertion

```
Algorithm addAfter(p,e):
Create a new node v
v.setElement(e)
v.setPrev(p) {link v to its predecessor}
v.setNext(p.getNext()) {link v to its successor}
(p.getNext()).setPrev(v) {link p’s old successor to v}
p.setNext(v) {link p to its new successor, v}
return v {the position for the element e}
```

![[Pasted image 20260930105724.png]]

# Delete

```
Algorithm remove(p):
t = p.element {a temporary variable to hold the return value}
(p.getPrev()).setNext(p.getNext()) {linking out p}
(p.getNext()).setPrev(p.getPrev())
p.setPrev(null) {invalidating the position p}
p.setNext(null)
return t
```

![[Pasted image 20260930105827.png]]

---

# Iterators

[[Lecture 12 - Node as Inner class#Iterator|Covered in java 2]]

- An iterator abstracts the process of scanning through a collection of elements
- It maintains a cursor that sits between elements in the list, or before the first or after the last element
![[Pasted image 20260930111429.png]]

## Performance

In the implementation of the List ADT by means of a doubly linked list

```
The space used by a list with n elements is O(n)

The space used by each position of the list is Operations of the 

List ADT run in O(1) timeO(1)

Operation element() of the Position ADT also runs in O(1) time
```


We can augment the different ADTs (i.e. Stack,Queue, List, etc. ) with method:
	```
	Iterator<E> iterator(): returns an iterator over the elements
	In Java, classes with this method extend Iterable<E>
	```

#### Two notions of iterator

- snapshot: freezes the contents of the data structure at a given time
- dynamic: follows changes to the data structure

#### The For-Each Loop

![[Pasted image 20260930111822.png]]

## List Iterators in Java

- Java uses a the ListIterator ADT for node-based lists.

![[Pasted image 20260930111910.png]]

