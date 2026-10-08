# Class members

➤ Not all combinations of instance and class variables and methods are allowed: 
➤ Instance methods can access instance variables and instance methods directly. 
➤ Instance methods can access class variables and class methods directly. 
➤ Class methods can access class variables and class methods directly. 
➤ **Class methods cannot access instance variables or instance methods directly** — they must use an object reference. Also, class methods cannot use the this keyword as there is no instance for this to refer to.

**STATIC METHODS CANNOT ACCESS NOT STATIC METHOD HOWEVER IF A OBJECT IS CREATED THEN THE OBJECT CAN ACCESS IT**

**ONLY WAY TO HAVE PRIVATE CLASS IS FOR IT TO BE INSIDE PUBLIC CLASS**
# Nested classes

This provides more information hiding and encapsulation. 
	➤ Ex: 
		➤ a Node class defined within a List class 
		➤ a Client class defined within an Account class 
		➤ a Money class defined within an Account class

**Nested classes are divided into two categories: static and non-static.** 
	-  Nested classes that are declared static are called static nested classes. 
	- Non-static nested classes are called inner classes
```
class OuterClass { 
... 
	static class StaticNestedClass { 
	... 
	} 
		class InnerClass { 
		... 
		}
	}
```
![[Pasted image 20260402182303.png]]

--> **Inner classes have access to other members of the enclosing class, even if they are declared private.** 
--> **Static nested classes do not have access to instance members of the enclosing class.**

![[Pasted image 20260402182606.png]]

**SPECIAL NOTE**: CANNOT OVERRIDE METHOD THAT HAS CLASS INSIDE

# Static Nested Classes

Since a static nested class has no connection to an instance of the outer class, within a static nested class method: 
	➤ Instance variables of the outer class cannot be referenced 
	➤ Non-static methods of the outer class cannot be invoked 
	
To call a static method or access a static variable of a static nested class from the outer class, prefix it with the name of the nested class followed by a dot.
![[Pasted image 20260402183228.png]]

**WHEN TO USE STATIC NESTED CLASSES?**
- If an object of the inner class is created within a static method of the outer class 
- If the inner class must have static members

Static nested classes are accessed using the enclosing class name 

```
OuterClass.StaticNestedClass
```

For example, to create an object for the static nested class, use this syntax

```
OuterClass.StaticNestedClass nestedObject = new OuterClass.StaticNestedClass();
// this is done if we want to access non static method inside static class because we need it to be instanciated in order to access methods
```

**ALL OF THESE ARE ACCEPTABLE**

```
staticNestedObject.nonstaticMethod(); 
staticNestedObject.staticMethod(); 
OuterClass.StaticNestedClass.staticMethod();
```

**NOTE**:
- A static nested class behaves like any other top-level class when accessing instance members of its outer class — it must do so through an object reference. In essence, it's like a top-level class that's nested within another class purely for organizational or packaging purposes.

# Inner Class

**Like instance methods and instance variables, an inner class is tied to an instance of its enclosing class and can directly access that instance's methods and fields.** 

**Also, because an inner class is associated with an instance, it cannot define any static members itself.**

An instance of InnerClass **can exist only within an instance of OuterClass** and has direct access to the methods and fields of its enclosing instance. 

To instantiate an inner class, **you must first instantiate the outer class.** Then, create the inner object within the outer object with this syntax:

```
OuterClass outerObject = new OuterClass(); 
OuterClass.InnerClass innerObject = outerObject.new InnerClass();
```

**INNER AND OUTER CLASSES HAVE ACCESS TO EACH OTHER'S PRIVATE MEMBERS**

➤ Inside an inner class method: 
- You can directly access private instance variables of the outer class. 
- You can call private methods of the outer class.

➤ Inside an outer class method : 
- You can access private instance variables of the inner class **via an object of the inner class**. 
- You can call non-static methods of the inner class, **if you use an instance of the inner class**. 
- Within the body of the inner or outer class, the **public** and **private** modifiers are equivalent — they don't restrict access between the two.

**NOTE**: IF CLASS IS PRIVATE ALL MEMBERS / VARIABLES ARE AUTOMATICALLY PRIVATE THEY CAN BE SET TO PUBLIC BUT WILL ACTS AS PRIVATE

A non-static inner class must be instantiated through an instance of the outer class
```
BankAccount account = new BankAccount(); 
BankAccount.Money amount = account.new Money(“41.99");
```

![[Pasted image 20260402191347.png]]

SIMPLE USES OF INNER CLASSES 
➤ An inner class is a member of the outer class 
	➤ Just like an instance variable is a member 
	
➤ An inner class is local to the outer class definition 
	➤ If the inner class is private, then the inner class cannot be accessed by name outside the definition of the outer class. 
	
➤ In this case, the name of an inner class may be reused for something else outside the outer class definition 

➤ 2 main advantages to use inner classes 
	➤ Can make the outer class more self-contained 
	➤ Both of their methods have access to each other's private methods and instance variables
	 
➤ Typically used when the inner class is a helping class to the outer class; make the inner class private

![[Pasted image 20260402191706.png]]
output =    9
         5

![[Pasted image 20260402192058.png]]
output = compiler error as y cannot be accesed from c MyClass would need to be accessed from inner
![[Pasted image 20260402192715.png]]
output =   5
	    7
	    9

CALLING METHOD OF THE OUTER CLASS

If a method is invoked in an inner class: 
	➤ If the inner class has no such method then the method is searched in the outer class 
	➤ If both the inner and outer class have a method with the same name, then the method of the inner class is used to force the call the method of the outclass class: 
		
	OuterClassName.this.methodName()

**SHADOWING:**

- **if a declaration of a type in a particular scope has the same name as another declaration in the enclosing scope, then the declaration shadows**

```
public class ShadowTest { 
public int x = 0; 
class FirstLevel { 
	public int x = 1; 
	void methodInFirstLevel(int x) { 
		System.out.println("x = " + x); 
		System.out.println("this.x = " + this.x); 
		System.out.println("ShadowTest.this.x = " + ShadowTest.this.x); }
	 } 
public static void main(String... args) { 
	ShadowTest st = new ShadowTest(); 
	ShadowTest.FirstLevel fl = st.new FirstLevel();
	fl.methodInFirstLevel(23); 
} 
}
```

**Given an OuterClass that has an InnerClass**
- Any DerivedClass of OuterClass will automatically have InnerClass as an inner class
-  In this case, the DerivedClass cannot override the InnerClass

**➤ An outer class can be a derived class** 
**➤ An inner class can be a derived class also**

# Local Classes

**TWO KINDS OF INNER CLASSES** 
	➤ Local classes and Anonymous classes. 
	➤ Local classes: defined in a block (group of zero or more statements between balanced braces). Typically find local classes defined in the body of a method.

A local class has access to: 
	➤ the members of its enclosing class. 
	➤ local variables that are declared final or effectively final. (bc local has instance that cannot be changed)

➤ When a local class accesses a local variable or parameter of the enclosing block, it captures that variable or parameter. 
➤ For example, the PhoneNumber constructor can access the local variable numberLength because it is declared final; numberLength is a captured variable

**Local classes are similar to inner classes because they cannot define or declare any static variables**

**Local classes in static methods, such as the class PhoneNumber, which is defined in the static method validatePhoneNumber, can only refer to static members of the enclosing class.**
![[Pasted image 20260402195023.png]]

**You cannot declare an interface inside a block; interfaces are inherently static.**

![[Pasted image 20260402195128.png]]
![[Pasted image 20260402195141.png]]
![[Pasted image 20260402195230.png]]


# Anonymous classes
**MADE TO BE DISPOSABLE**

**➤ Anonymous classes enable you to make your code more concise.** 
**➤ They enable you to declare and instantiate a class at the same time.** 
**➤ They are like local classes except that they do not have a name. Use them if you need to use a local class only once.**

The class definition is embedded inside the expression with the new operator
```
public static void main(String[] args){ 
	NumberCarrier anObject = new NumberCarrier() { 
		private int number; 
		public void setNumber(int value) { 
		number = value; }
		public int getNumber( ) { 
		return number;} 
		} ; // semicolon after curley brace as it finishes NumberCarrier 
			anObject = new NumberCarrier() {
			// cannot make another numberCarrier only used once 
```

➤ The syntax of an anonymous class expression is like the invocation of a constructor, except that there is a class definition contained in a block
![[Pasted image 20260402200643.png]]
**SEMICOLON AFTER LAST CURLY BRACE IS VERY IMPORTANT**
![[Pasted image 20260402201008.png]]


**Like local classes, anonymous classes can capture variables; they have the same access to local variables of the enclosing scope:** 
	➤ An anonymous class has access to the members of its enclosing class. 
	➤ An anonymous class cannot access local variables in its enclosing scope that are not declared as final or effectively final. 
	➤ Like a nested class, a declaration of a type (such as a variable) in an anonymous class shadows any other declarations in the enclosing scope that have the same name

Anonymous classes also have the same restrictions as local classes with respect to their members: 
	➤ You cannot declare static initializers or member interfaces in an anonymous class. 
	➤ An anonymous class can have static members provided that they are constant variables.
![[Pasted image 20260402201504.png]]


# Uses

1. It is a way of logically grouping classes that are only used in one place: If a class is useful to only one other class, then it is logical to embed it in that class and keep the two together. Nesting such "helper classes" makes the package more streamlined
2. It increases encapsulation: Consider two top-level classes, A and B, where B needs access to members of A that would otherwise be declared private. By hiding class B within class A, A's members can be declared private and B can access them. In addition, B itself can be hidden from the outside
3. It can lead to more readable and maintainable code: Nesting small classes within top-level classes places the code closer to where it is use.

# Examples

![[Pasted image 20260402201646.png]]
1. no
2. no
3. yes
![[Pasted image 20260402201724.png]]
1.yes(only if not modified elsewhere)
2.yes

![[Pasted image 20260402201823.png]]

![[Pasted image 20260402201923.png]]

![[Pasted image 20260402202103.png]]
output = A
![[Pasted image 20260402202149.png]]
outpout = B
![[Pasted image 20260402202229.png]]
output = A
