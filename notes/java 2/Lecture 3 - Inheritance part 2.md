part 2 of [[Lecture 2 - Inheritance]]
 **private standing final cannot be overwritten**

# The super keyword

- super.member ----> always uses superclass’s member
- ex: super.aMethod()
- ex: super.anAttribute
- super()  calls constructor of its immediate superclass

from child can you access grandparents and if so can we use super.super.aMethod()? ----> **HMWK**

slide 28 output is ----> 1000 1010 1010

# This Constructor

Often, a no-argument constructor uses this to invoke an explicit-value constructor

``public HourlyEmployee() {
``this("No name", new Date(), 0, 0);
``}
``public HourlyEmployee(String theName,
``Date theDate,
``double theWageRate,
``double theHours){

# Inheritance and Constructors

---> construcotrs are not inherited .If you don't call parent's constructor yourself:

---> Java will automatically call super() (parent's constructor) as 1st line of every constructor

So if you provide your own constructors with arguments
----> You must explicitly call the parent's constructor (super(argument list)) since no default constructor will be provided

**WHENEVER A PARAMETERIZED CONSTRUCTOR IS DEFINED CANNOT USE DEFAULT WITHOUT WRITING IT**

**STUDY STACK RACE CALL!!!!!**

# Member Visibility

- Visibility modifiers determine which class members get inherited and which do not

- Members declared with public visibility are inherited

- Members declared with private visibility are not inherited

types of modifiers in order of privilege ---> 
- private 
- default (package private)
- protected
- public
**good practice slide 44**


# Method Overriding

A derived class can change the visibility of a superclass’s methods, but only if it provides more access.

So, it must:
---> have the same name as a superclass method
---> have the same parameter list as a superclass
method
---> have the same return type as a superclass
method 

access modifier for an overriding method can not be more restrictive than that of its corresponding superclass method

---> if a superclass method is public, then its corresponding overriding method must be public
---> if a superclass method is protected, then its corresponding  overriding method may be protected or public
---> if a superclass method is package, then its corresponding overriding method may be package, protected, or public

**Array can store different childs of same parents class**













