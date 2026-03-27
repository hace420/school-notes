# Static vs dynamic structures
- A static data structure has a fixed size
➤ NOTE: nothing to do with the Java static modifier

- A dynamic data structure can grow and shrink at run time
➤ Ex: ArrayList (as seen [[Lecture 9b - Abstraction - Generics]]) or a linked data structure - implemented through our good friend: the reference

A reference (or pointer) is a variable that stores the address of an object in memory
![[Pasted image 20260326193632.png]]

Object references can be used to create links between objects
![[Pasted image 20260326193751.png]]

# Linked list

A linked list consists of a single chain of nodes, each connected to the next by a link
➤ The first node is called the head node
➤ The last node serves as a kind of end marker

![[Pasted image 20260326193909.png]]

➤ In a linked list, each node is an object of a node class
➤ Each node contains data and a link to another node
➤ A piece of data is stored as an instance variable of the node
➤ Data is represented as information contained within the node "box"
➤ Links are implemented as references to a node stored in an instance variable of the node type

NODE = entity in your list.


![[Pasted image 20260326195424.png]]
output is = cantaloupe bananas apples (b/c used addtostart method)


head points to first node that will then point to next node.

**PERFORMANCE OF LINKED LISTS**

Linked Lists are fast for :
➤ Adding elements
➤ Removing elements

Linked Lists are slow for : (array list are better for these reasons)
➤ Traversing the list
ex: Checking if elements exist within the list
ex: Finding elements
➤ Retrieving elements by index (random access)

# Traversing lists
![[Pasted image 20260326195847.png]]

# Adding / removing / inserting from lists
![[Pasted image 20260326195945.png]]
![[Pasted image 20260326200033.png]]
![[Pasted image 20260326200102.png]]
