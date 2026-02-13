part 2 of [[Lecture 4 - Polymorphism]]
# Abstract keyword
--> Abstract method should be defined as high as possible in the inheritance tree.

--> cannot be defined as static final or private as it will make it unreachable 
--> cannot be used for constructor 

--> abstract class still has constructors as it will be needed for usage of super() in child class.

```
abstract class A {
short m2() { return (short) 420; }
}
abstract class B extends A {
abstract short m2();
}

this works as the child is making the parent function not visible and defining its own version forsing its children to have to define it also
```

# Clone method

**ALWAYS INHERITED FROM OBJECT CLASS**

- clone has no parameters
- it should return deep copy of the calling object
- each class is expected to override it with a more appropriate version

**LIMITATIONS (CLONE VS COPY)**

```
public Object clone() {
return new Animal(this);
}
So, the result had to be casted
Animal copy = (Animal)original.clone();
```

given a method in the class Animal that copies an array of animals
If the array contains objects of type Dog
-  If we use the copy constructor:
-  then the copy will be a plain Animal, not a true copy
```
b[i] = new Animal(a[i]);
//plain Animal object
```

---> if we use the clone method, a true copy is made
`b[i] = (a[i].clone()); //Dog object

 - because the method clone has same name in all classes, and polymorphism works with method names
-  The copy constructors named Animal and Dog have different names, and polymorphism doesn't work with methods of different names


