cont of [[Lecture 10b - Linked data Structures]]
# Pitfalls
**need to double check if inner class is public private or protected**

![[Pasted image 20260409181150.png]]

# THE PRIVATE METHOD COPYOF

The private helping method copyOf takes an argument that is a reference to a head node of a linked list, and returns a reference to the head node of a copy of that list

	➤ It goes down the argument list one node at a time and makes a copy of each node
	➤ The new nodes are added to the end of the linked list being built
	
This produces a new linked list with all new nodes, but the new
list is not truly independent because the data object is not
cloned.

Object must implement the Cloneable interface to use clone()
**The object class has a clone method that checks to see if the implements Cloneable, if it doesn’t it throws the “CloneNotSupportedException”**

➤ Every time you use clone you need to check for exceptions.
➤ Note: clone() is a protected method.

![[Pasted image 20260409182948.png]]
**THIS IS SHALLOW COPY**


![[Pasted image 20260409183602.png]]

# Iterator

A collection of objects, such as the nodes of a linked list, must often be traversed in order to perform some action on each object
➤ An iterator is any object that enables a collection to be traversed
➤ An iterator allows you to loop through a collection in a standard way (even though the structure of the specific collection is very different)

**Given a linked list named list, an iterator can be initialized:**
**LinkedList2.List2Iterator i = list.iterator();**

➤ The basic methods used by an iterator are as follows:
➤ restart: Resets the iterator to the beginning of the list
➤ hasNext: Determines if there is another data item on the list
➤ next: Produces the next data item on the list


![[Pasted image 20260409191146.png]]

NOTE NEED TO USE next BE>FORE U CAN READ 15

