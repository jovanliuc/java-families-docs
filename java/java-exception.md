[Back to Home](../README.md)
# The Overview of Java Exception
In Java, an exception is an event 
that occurs during the execution of a program 
that disrupts the normal flow of instructions.
When an exception occurs, the normal flow
of the program is interrupted, and the control
is transferred to the appropriate exception handler.
This helps in detecting and handling errors 
or exceptional conditions in the program.

In Java, all exceptions are objects that belong to
a class derived from the `java.lang.Exception` class 
or the `java.lang.RuntimeException` class. 
There are three categories of exceptions in Java: 
checked exceptions, unchecked exceptions, and errors.

Checked exceptions are the exceptions 
that are checked at compile-time, 
and the programmer must handle them 
or declare them to be thrown in the method 
signature using the `throws` keyword.

Unchecked exceptions are the exceptions 
that are not checked at compile-time, 
and the programmer is not required to
handle them or declare them to be thrown
in the method signature.

Errors are the exceptional conditions 
that are not recoverable by the application,
and the programmer is not expected to handle them.

Java provides several built-in exception classes, 
such as `ArithmeticException`, `NullPointerException`,
`ArrayIndexOutOfBoundsException`, `ClassCastException`, 
`FileNotFoundException`, `IOException`, `SQLException`, etc., 
that can be used to handle specific types of exceptions.
Additionally, programmers can also define their 
own exception classes by extending the `Exception` 
or `RuntimeException` classes.

# Java Exception FAQ
## 1. What is an exception in Java?
An exception is an event that occurs during 
the execution of a program that disrupts the
normal flow of instructions.

## 2. What is the purpose of the try-catch block?
The try-catch block is used to handle exceptions in Java. 
The code that may throw an exception is placed 
in the try block, and the code that handles 
the exception is placed in the catch block.

## 3. What is the difference between checked and unchecked exceptions?
Checked exceptions are those that are checked 
at compile-time, while unchecked exceptions 
are not checked at compile-time. Checked exceptions 
must be either caught or declared in the method signature, 
while unchecked exceptions can be caught or left uncaught.

## 4. What is the difference between a runtime exception and an error in Java?
Runtime exceptions are exceptions that occur at runtime 
and are not checked at compile-time. Errors, on the other hand, 
are more serious problems that can occur during 
the execution of a program and cannot be handled 
by the program itself.

## 5. What is the difference between `throw` and `throws` in Java?
`Throw` is used to manually throw an exception, 
while `throws` is used to declare that a method 
may throw one or more exceptions.

## 6. What is the difference between `final`, `finally`, and `finalize` in Java?
`Final` is a keyword used to declare a variable 
or method that cannot be modified. `Finally`
is a block of code that is always executed 
after a try-catch block, regardless of whether
an exception is thrown or not. `Finalize` 
is a method called by the garbage collector 
to clean up resources before an object is destroyed.

## 7. What is a `NullPointerException` in Java?
A `NullPointerException` is an unchecked exception
that occurs when an attempt is made to use 
a null reference where an object is required.

## 8. What is an `OutOfMemoryError` in Java?
An `OutOfMemoryError` is a type of error that
occurs when the Java Virtual Machine (JVM) 
cannot allocate enough memory for an object.

## 9. What is the difference between the `printStackTrace()` and `getMessage()` methods of the `Throwable` class in Java?
The `printStackTrace()` method prints the stack
trace of the exception to the standard error stream, 
while the `getMessage()` method returns the error 
message associated with the exception.

## 10. How can you create a custom exception in Java?
To create a custom exception in Java, 
you can extend the `Exception` or `RuntimeException` class 
and define your own exception class with the desired
properties and methods.