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
