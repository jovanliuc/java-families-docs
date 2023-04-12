[Back to Home](../README.md)
# The Overview of Java Generics
Java generics is a feature in Java programming 
language that allows you to write more generic
and reusable code. Generics provide a way to 
parameterize types, so that a class or method 
can operate on objects of various types without 
the need for explicit casting. This helps to
improve type safety and makes the code more
readable and maintainable.

The syntax for defining a generic type is to 
specify the type parameter in angle brackets 
following the class or method name. For example,
the following code defines a generic class named Box
that can hold any type of object:

```java
public class Box<T> {
    private T item;

    public T getItem() {
        return item;
    }

    public void setItem(T item) {
        this.item = item;
    }
}
```

The Box class has a single type parameter T, 
which can be any type. The `setItem` method 
takes an argument of type T, and the `getItem` method
returns an object of type T. When you create an 
instance of the Box class, you specify the actual 
type to use for T.

Wildcard is another feature of Java generics, 
which allows you to represent an unknown type. 
Wildcards are denoted by the ? symbol, and they 
can be used in place of a type parameter when 
the exact type is unknown or unimportant.

For example, the following code defines a method 
that accepts a List of objects of an unknown type:

```java
public void printList(List<?> list) {
    for (Object elem : list) {
        System.out.print(elem + " ");
    }
    System.out.println();
}
```

The `printList` method takes a List of objects of 
an unknown type using the wildcard ?. 
This means that the method can accept a List of 
any type. The method then iterates over the elements
in the list and prints each one to the console.

Wildcards can also be bounded by specifying upper 
or lower bounds using the extends and super keywords.
For example, the following code defines a method 
that takes a List of objects that extend the Number class:

```java
public void printNumbers(List<? extends Number> list) {
    for (Number num : list) {
        System.out.print(num + " ");
    }
    System.out.println();
}
```

In this example, the ? wildcard is bounded by 
extends Number, which means that the method 
can accept a List of objects that extend the
Number class, such as Integer, Double, or BigDecimal.
This allows you to write more generic code 
that works with a wider range of types.

# Type Erasure
Java type erasure refers to the process by which
the Java compiler removes type information 
from generic code at compile time. 
This is done to maintain compatibility 
with legacy code that was written 
before the introduction of generics in Java 5.

When you write generic code in Java,
you use type parameters to define 
the type of the objects that will 
be stored in a collection or used
as a method parameter. For example, 
you might write a method that takes 
a `List` of Strings as a parameter:

```java
public void printList(List<String> list) {
    for (String s : list) {
        System.out.println(s);
    }
}
```

At compile time, the Java compiler replaces 
the type parameter `List<String>` with the raw type List. 
This means that the type information is erased, 
and the method signature becomes:

```java
public void printList(List list) {
    for (Object o : list) {
        String s = (String) o;
        System.out.println(s);
    }
}
```

As you can see, the type information has been removed, 
and the code now uses the raw type `List` instead of `List<String>`. 
This can cause problems if you try to access 
the generic type information at runtime, 
because it is no longer available.

To work around this, Java uses a process 
called type bounds to ensure that the generic code
is type-safe at runtime. 
Type bounds specify the upper and lower limits
of the type that can be used with 
a generic class or method. 
For example, the type bound `extends Number` specifies 
that the generic type must be a subclass 
of the `Number` class.

In summary, Java erasure is the process 
by which the Java compiler removes type information 
from generic code at compile time, 
and type bounds are used 
to ensure type safety at runtime.

# FAQ
## What is a generic in Java?
Generics allow you to define classes, interfaces, 
and methods that can work with any type. 
A generic type is a class or interface that 
is parameterized over types.
The parameterized types are referred to 
as type parameters.

## What is a wildcard in Java generics?
A wildcard in Java generics is a special type argument
that can be used to match any type. 
The wildcard character "?" 
is used to represent an unknown type.

## What is the difference between \<? extends T\> and \<? super T\>?
\<? extends T\> is a bounded wildcard 
that allows any type that is a subtype of T or T itself. 
It is useful when you want to read from a collection, 
but not write to it. 
\<? super T\> is also a bounded wildcard 
that allows any type that is a supertype of T or T itself. 
It is useful when you want to write to a collection, 
but not read from it.

## Can you give an example of how to use a wildcard in Java generics?
Yes, for example, suppose we have a method that takes 
a list of numbers and returns the sum. We can use
a wildcard to make the method more flexible, as follows:

```java
public static double sum(List<? extends Number> numbers) {
    double sum = 0.0;
    for (Number number : numbers) {
        sum += number.doubleValue();
    }
    return sum;
}
```
This method can now accept a List of any type 
that is a subtype of Number, 
such as Integer, Double, or Float.

## What is type erasure in Java generics?
Type erasure is the process of removing 
all generic type information from a program
when it is compiled. This is done to ensure compatibility
with pre-existing code 
that was not designed to work with generics.

## How can you create a generic class in Java?
To create a generic class in Java, 
you can use the following syntax:

```java
public class MyClass<T> {
    // class definition
}
```

The "T" in angle brackets is the type parameter,
which can be replaced by any class or interface.

## Can you create a generic method in a non-generic class?
Yes, you can create a generic method in a non-generic class. 
To do so, you need to declare the type parameter
before the return type, as follows:

```java
public class MyClass {
    public <T> void myGenericMethod(T t) {
        // method body
    }
}
```

## What is a raw type in Java generics?
A raw type in Java generics is a class or interface 
that is used without any type parameter. 
Raw types are allowed for compatibility 
with pre-existing code 
that was not designed to work with generics.

## What is type inference in Java generics?
Type inference in Java generics is the process 
by which the Java compiler infers the type arguments 
for a generic method invocation, based on the context
in which the method is called.

## What is the difference between a generic and a parameterized type?
A generic is a type that is parameterized over types. 
A parameterized type is a specific instance of a generic,
with actual type arguments supplied for the type parameters.

## Can you use a wildcard in a method return type?
Yes, you can use a wildcard in a method return type. 
For example, you can declare a method 
that returns a List of any type 
that is a subtype of Number, as follows:

```java
public List<? extends Number> getNumbers() {
    // method body
}
```

This method can return a List of any type 
that is a subtype of Number.
