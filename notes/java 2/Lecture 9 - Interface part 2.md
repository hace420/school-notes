# Notes from midterm [[Lecture 2 - Inheritance]] to [[Lecture 5b - Exception Handling]]

**Remember when overriding parent method child cannot make method less visible it can go from private to public but not the other way around. [[Lecture 4 - Polymorphism]].**


cannot implement 2 methods that share name but not return types

hidding = 2 static methods with same name so if child method is called parent method is hidden.

private = accessibility modifier
static = state level access
# Cont. Interface [[Lecture 8 - Interfaces]]

## Static Methods
--> Every object shares the static methods of its class.
--> Java lets you define static methods in interfaces

Consider a Drawable interface with a draw() method whose int argument contains the drawing
color. It's convenient to express this color as red, green, and blue components, so you add an rgb()
static method that converts these components to an int.
![[Pasted image 20260319180847.png]]
![[Pasted image 20260319180943.png]]

Java 8 introduced interface-based static methods because it’s often convenient to
associate utility methods with interfaces instead of associating them with utility classes.
--> Doing this makes source code more readable and ensures that binary compatibility isn't
broken.

## Private method

![[Pasted image 20260319181633.png]]
![[Pasted image 20260319182025.png]]
cant mix private and default in the same method declaration because default is implicitely public  and then you would have public private method .

