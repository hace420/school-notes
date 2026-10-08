# Example usage
extension of [[Lecture 9b - Abstraction - Generics]]
![[Pasted image 20260326180111.png]]


this will take any kind of object array and print it as it takes generic E element

**if you want to make generic to represent trio you would need to put bounds on F or S. This can be achieved with interfaces or abstract classes.** 
![[Pasted image 20260326180451.png]]

**IMPORTANT**
![[Pasted image 20260326180813.png]]

# Pitfalls
1. Although class name in a parameterized class definition has a type parameter attached; the type parameter is not used in the heading of the constructor definition.(Reason at compile time class has been defined already.job of constructor is to create instance it does not matter what t is it will always be created in the same way.)
	![[Pasted image 20260326181235.png]]
2.  A constructor can use the type parameter as the type for a parameter of the constructor, but in this case, the angular brackets are not used
	![[Pasted image 20260326181342.png]]
3. However, when a generic class is instantiated, the angular brackets are used.(At this point compiler will instanciate object)
	![[Pasted image 20260326181418.png]]
	
4. Within the definition of a parameterized class, there are places where an ordinary class name would be allowed, but a type parameter is not allowed.
5. In particular, the type parameter cannot be used in simple expressions using new to create a new object
	-  For instance, the type parameter cannot be used as a constructor name or like a constructor:
	- ![[Pasted image 20260326181802.png]]
6. It is not permitted to create a generic class with Exception, Error, Throwable, or any descendent class of Throwable (Reason: at runtime there is no difference between checked and unchecked error and generics are objects with are higher in the hierarchy tree.)
	- A generic class cannot be created whose objects are throwable:
	- ![[Pasted image 20260326182015.png]]
	- The above example will generate a compiler error message
7. Cannot have an array of a generic class.
	- ![[Pasted image 20260326182500.png]]
8. The type plugged in for a type parameter must be a reference type 
	- cannot be a primitive type (int, double, char,…)
	-  can be an array
	- ![[Pasted image 20260326182557.png]]
# Bound for "T"
![[Pasted image 20260326182712.png]]
**NOTE HERE EXTENDS = IMPLEMENTS WILL BE FINAL QUESTION**


![[Pasted image 20260326183030.png]]
- **if you want multiple extends use & not ","** & not ",

# Generic methods

- Generic method: method with a type variable 
-  Can be defined inside ordinary and generic classes
-  In a generic class, the type parameter can be used in its methods.
-  A generic method can define a type parameter that is not the type parameter of the class.
-  The type parameter of a generic method is local to that method, not to the class.

```
public static <T> T genMethod(T[] a) { … }

public static <E> void printArray(E[] inputArray)
{
for (E element : inputArray)
System.out.print(element + " ");
System.out.println();
}
```

```
ClassName.<RealType>genMethod(arg)
or simply
ClassName.genMethod(arg);
```

```
Rectangle[] rectangles = …;
// not necessary
ClassName.<Rectangle>printArray(rectangles);
ClassName.printArray(rectangles);
Character[] a3 = {'a', 'b', 'c'};
ClassName.printArray(a3);
// You can also define generic methods that are
// not static.
```

![[Pasted image 20260326183659.png]]

**A generic class can be a derived class of an ordinary class or of another generic class**
```
class Animal {
void sound() {
System.out.println("Animal makes a sound");
}
}
public class Dog<T> extends Animal {
T breed;
void sound() {
System.out.println("Dog barks");
}
}
Dog<String> dog = new Dog<>();
Animal animal = dog; //dog can be treated as an Animal
```

# Inheritance
**RULE**
if B is a subtype of A and G is some generic type declaration then
**This is probably the most counter intuitive rule of generics.**
![[Pasted image 20260326184545.png]]


**IMPORTANT THESE ARE NOT THE SAME**
```
public class Dog<T> extends Animal // dog is child of animal (t is not child of animal)
public static <E extends Comparable> // E is implementing comparible 
```



![[Pasted image 20260326184738.png]]

- The generic type is locked to the type you pass when the class is defined (in this case, either Dog or Animal)

```
Is the following code legal?
ArrayList<String> sList = new ArrayList<String>();
ArrayList<Object> oList = sList;

// answer: not legal arraylist object and arraylist string are not the same type nd type is lcoked at compilation so this cannot work
```
```
What about this?
sList.add(new Object());
String string = sList.get(0);

// answer: yes slist will alwasy contain strings


```

# Wildcards
![[Pasted image 20260326185447.png]]

**EXAMPLES**
```
public void m(ArrayList<? extends E> other) {…}
public static <E extends Comparable> E min(E[] a) {…}
public static <E extends Comparable<E>> E min(E[] a) {…}
static void reverse(ArrayList<?> list) {…}
static <T> void reverse(ArrayList<T> list) {…}

```

Generic methods and wildcards can also be used together.
```
public <T> void copy(
ArrayList<T> destination,
ArrayList<? extends T> source) {…}
```
![[Pasted image 20260326190345.png]]

output is compiler error.

