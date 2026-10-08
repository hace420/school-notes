# Polymorphism is the ability to associate many meanings to one method name

# It does this through a special mechanism known as late binding or dynamic binding




# Upcasting and Downcasting

Can you do this?    Hierarchy = pig --> animal
```
Animal a; 
Pig p = new Pig();
a = p;   
---> **this is ok no compiler or runtime issue**
 ---> it’s called upcasting
```

```
Animal a = new Animal();
Pig p;
p = a;
---> **this will fail as you cant assign a to p as there is a chance a animal cannot be a pig.**
---> it’s called downcasting
```


```
public class Up {

static void show_animal_cost(Creature myCreature){
System.out.println("I'm " + myCreature.getName() + " and my cost is " + myCreature.getCost());
}

public static void main(String[] args) {
Creature myCreature1 = new Creature(4,60,"Jellybean");
show_animal_cost(myCreature1);
// This works because of upcasting
Creature myCreature2 = new Platypus(44,17,"Natasha"); 
//(**for complier it will be creture but at run time it will be platipus which //is ok as platipus is child of animal**)
show_animal_cost(myCreature2)

```

```
// This will not even compile because of downcasting
Platypus myCreature3 = new Creature(44,17,"Wally");
show_animal_cost(myCreature3)

Platypus myCreature3 = new Creature1;
// this will also produce comp error 


Platypus myCreature3 = (Platypus) Creature1;
// this will work because of casting because 
//compiller sees: Platypus myCreature3 = (Platypus) 
// and at runtime sees: (Platypus) Creature1;


```

```
// A very peculiar example that shows that downcasts are possible
Platypus myPlatypus1 = new Platypus(4,60,"Peeps");
Creature myCreature5 = myPlatypus1;
Platypus myPlatypus2 = (Platypus) myCreature5;
myPlatypus2.print_foo();
show_animal_cost(myPlatypus2)
}
```

# Binding 

## **Binding = The process of associating a method definition with a specific method call**

There are 2 basic forms:
---> static binding - also called early binding
---> method definition is associated with its invocation when the code is compiled

---> dynamic binding - also called late binding
---> method definition is associated with its invocation when the method is invoked (at run time)
---> because it is not done at runtime there is a performance penalty
---> the reason this is used because it is because performance is not speed or effiency.

# Polymorphism 

Suppose we create following reference variable:

Animal a;
this reference can point to an Animal object, or to any object of any compatible type

This compatibility can be done:
- using inheritance 
- using interfaces

**Output for slide 17** hwmk
```
public static void main (String[] args) {
Farmpoly myFarm = new Farmpoly();
for (int i = 0; i < FARMSIZE; i++){
System.out.print(myFarm.aList[i]); // ???
}
}
}

output = 
```


We place an object of animal type in each of these references
---> an animal type includes any sub-class of animal

Java delays the binding of talk() until run time.
In the main loop, the right version (the most specific one) of talk() will be called

```
public class PrivateOverride{
private void f(){
System.out.println("private f()");}
public static void main(String[] args){
PrivateOverride po = new Derived();
po.f(); }}
public class Derived extends PrivateOverride{
public void f() { //this method is never run.
System.out.println("public f()"); }}

//output is private f() because early binding 
```

changed private to protected and commented out public method --->
```
public class PrivateOverride{
protected void f(){
System.out.println("private f()");}
public static void main(String[] args){
PrivateOverride po = new Derived();
po.f(); }}
public class Derived extends PrivateOverride{
//public void f() { //this method is never run.
//System.out.println("public f()"); }}

```

Java always use dynamic binding
 Java always uses dynamic binding for methods except:
---> for private, final and static methods