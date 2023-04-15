[Back to Home](../README.md)
# The Overview of Java Classloader
In Java, a class loader is a subsystem 
of the Java Virtual Machine (JVM) that
is responsible for loading Java classes
at runtime.

Java uses a hierarchical class loading system, 
which means that each class loader has 
a parent class loader. When a class is requested,
the class loader first checks its own cache 
of loaded classes. If the class is not found,
it delegates the request to its parent class loader.
This process continues until the class is found 
or until the root class loader is reached.

There are three types of class loaders in Java:

1. `Bootstrap Class Loader`: It is the parent 
of all class loaders and is responsible for 
loading the core Java libraries from the 
`rt.jar` file.

2. `Extension Class Loader`: It is the child
of the `Bootstrap Class Loader` and is 
responsible for loading the classes from 
the `extensions` directory.

3. `System Class Loader`: It is the child 
of the `Extension Class Loader` and is 
responsible for loading classes from the 
classpath and any other custom class loaders.

In addition to these built-in class loaders,
Java also provides a mechanism to create 
custom class loaders. This can be useful 
in scenarios where you want to load classes 
from non-standard locations or protect the 
application from loading classes that are not trusted.

Overall, understanding class loaders is an 
important aspect of Java programming, 
as it enables developers to control how classes
are loaded and provides a way to customize 
the application's behavior.

# Java Classloader FAQ
## 1. What is a classloader in Java?
A classloader is a part of the Java 
Runtime Environment (JRE) that dynamically
loads Java classes into memory as they 
are needed during runtime.

## 2. What are the types of classloaders in Java?
There are three types of classloaders 
in Java: the bootstrap classloader, 
the extension classloader, and 
the system classloader.

## 3. What is the bootstrap classloader?
The bootstrap classloader is responsible 
for loading the core Java libraries, 
such as `java.lang.*` and `java.util.*`, 
that are required for the JVM to start up.

## 4. What is the extension classloader?
A: The extension classloader is responsible
for loading classes from the extension directories, 
which are specified by the java.ext.dirs system property.

## 5. What is the system classloader?
A: The system classloader is responsible 
for loading classes from the classpath,
which is specified by the `java.class.path`
system property.

## 6. What is the delegation model of classloaders?
A: The delegation model of classloaders is 
a mechanism by which classloaders delegate 
the task of loading a class to their parent
classloader before attempting to load the 
class themselves. This ensures that classes
are loaded only once, and that the same class
is used across multiple classloaders.

## 7. What is class loading?
Class loading is the process by which 
a classloader loads a class into memory.

## 8. What is the classpath in Java?
The classpath is a system environment 
variable that specifies the directories
or JAR files containing the Java class 
files that the JVM needs to execute a program.

## 9. How does the classloader resolve class conflicts?
The classloader resolves class conflicts 
by using the delegation model. 
When a class is requested, 
the classloader first delegates the task of 
loading the class to its parent classloader.
If the parent classloader is unable to find 
the class, the classloader attempts to load 
the class itself.

## 10. Can you create your own classloader in Java?
Yes, you can create your own classloader 
in Java by extending the `java.lang.ClassLoader` class 
and overriding its loadClass() method.