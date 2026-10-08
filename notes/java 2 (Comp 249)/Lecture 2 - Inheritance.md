
# Enumerated types
--> used when user can only enter inputs from a specified list 
for example asking which day a user want to schedule meeting

to define 
`` enum WorkDay {MONDAY,TUESDAY,....} 
`` Workday meetingDay; 
`` meetingDay = WorkDay.TUESDAY; 

**if using comparing operator index will be compared not string.**

--> can use `` WorkDay.MONDAY.ordinal `` to get index value.

--> null can be used if you want to send variable to garbage.

**use of valueOf can be used for switches**


# Methods

method overloading is used when number of attributes can change or unknown.

methods can also have varied number of parameters
``int result3 = max(4, 5, 7);
``int result2 = max(4, 5);

`public static int max(int... arg){
`if (arg.length == 0) {
`System.out.println("Fatal Error: maximum of zero values.");
`System.exit(0);
`} 
``// checks for largest number
`int largest = arg[0];
`for (int i = 1; i < arg.length; i++)
`if (arg[i] > largest)
`largest = arg[i];
`return largest;

**limitations** :
-->  if more then one attribute needs to be passed for example a variable int and a non variable int the variable int will consume all inputs and the second int wont be assigned. **(VARIABLE ATTRIBUTE SHOULD BE WRITTEN ALWAYS LAST)**

# Inheritance 

**REPRESENTS IS-A RELATION**

--> multiple inheritance not allowed through classes.

**ONLY VARIABLES THAT ARE PART OF INSTANTIATED CLASS ARE LOCALIZED**

--> always write default constructor and always manually initialize all variables.

--> When a class C acquires the properties of another class P, then class C is said to have
inherited class P

class P is called base, parent or super class
class C is called a child or sub class.

--> A subclass inherits the members defined by the super class and adds its own, unique elements.

**The keyword extends is used to inherit a class.**
Ex: 
``public class Car extends Vehicles{...};  Vehicles is parent while car is child.``









