In Java, we use exception objects
-  An exception is an object that describes an unusual or erroneous situation
--> ex: take the log of a negative number, division by zero, a file cannot be opened, null reference

 A program is now separated into:
1. the normal execution flow 
2. An exception execution flow

**STACK TRACE**
shows the trace of methods that error went through

![[Pasted image 20260212185609.png]]

# TRY TROW CATCH FINALLY

--> try:  a block of code in which exceptions can be generated
--> throw: allows to generate an exception
--> catch:  a handler for a particular type of exception

![[Pasted image 20260212185950.png]]

The try block

- includes the line that throws an exception (directly/not)
-  is followed by one or more catch clauses

The catch block

- contains code to process an exception 
- has an associated exception type
- is called an exception handler
- If an Exception is thrown inside of a try block, the exception that is returned is forwarded as an argument to the catch block where the Exception can be handled

The finally block

- optional
-  The statements in the finally clause:
	are always executed
	 Run before Java moves up the call stack
-  useful to run important code that must run at the end of the try block even if an exception is thrown
	 ex: closing a file opened in a try, …
- If no exception is generated,
	the finally clause is executed after the try block completes
-  If an exception is generated,
	 the finally clause is executed after the appropriate catch block completes

![[Pasted image 20260212192308.png]]

![[Pasted image 20260212192343.png]]
