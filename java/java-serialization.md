[Back to Home](../README.md)
# The Overview Java Serialization
Java Serialization is a mechanism provided 
by the Java programming language to enable 
the conversion of an object into a stream 
of bytes and vice versa. This allows objects 
to be easily stored, transmitted, and reconstructed 
later on.

To serialize an object, it must implement the 
`java.io.Serializable` interface, 
which is a marker interface that indicates 
that the object can be serialized.
Once an object is serialized, it can be stored 
in a file or sent over a network to another machine.

To deserialize an object, the opposite process 
is followed. The stream of bytes representing 
the object is read, and the object is reconstructed 
back into its original form. Deserialization is done 
using the `ObjectInputStream` class.

One of the advantages of Java Serialization is 
that it is a language-level feature, 
which means that it works across platforms 
and programming languages. However, 
it is not always the most efficient way 
to transmit data, especially for large amounts of
data or for data that needs to be transferred 
over a network with limited bandwidth.

Additionally, Java Serialization has some security
risks associated with it. Malicious users 
can manipulate the stream of bytes to execute 
arbitrary code, which is known as a deserialization 
vulnerability. To mitigate this risk, 
it is important to validate the input stream 
of bytes and to use a secure classloading mechanism.

# FAQ
## What is Java Serialization?
Java Serialization is the process of converting 
an object into a stream of bytes, 
which can be sent over a network or saved into a file.
The reverse process of restoring the object 
from the stream of bytes is known as deserialization.

## How is Serialization achieved in Java?
In Java, Serialization is achieved
by implementing the Serializable interface. 
The Serializable interface is a marker interface, 
which means it does not have any methods that
need to be implemented. The JVM automatically 
handles the serialization and deserialization 
of the object when the class implements the
Serializable interface.

## What is the use of serialVersionUID in Java Serialization?
serialVersionUID is a unique identifier 
for the serialized version of a class. 
It is used to ensure that the serialized 
and deserialized objects are compatible. 
If the serialVersionUID of the serialized object 
is different from the serialVersionUID of the 
class during deserialization, 
then an `InvalidClassException` is thrown.

## What are the advantages of Java Serialization?
Java Serialization has the following advantages:

- It provides an easy way to save and restore 
the state of an object.
- It allows objects to be sent over a network,
which is useful in client-server applications.
- It can be used to implement deep cloning of objects.

## What are the disadvantages of Java Serialization?
Java Serialization has the following disadvantages:

- It can be slow and inefficient compared 
to other serialization mechanisms.
- It can cause security issues if untrusted data 
is deserialized.
- It can be difficult to debug issues related 
to serialization and deserialization.

## What is the difference between Serializable and Externalize interfaces?
Serializable is a marker interface, 
which means it does not have any methods 
that need to be implemented.
The JVM automatically handles the serialization
and deserialization of the object when the class
implements the Serializable interface. 
Externalize is an interface that provides
methods to customize the serialization 
and deserialization process.
The Externalize interface has two methods 
that need to be implemented: `readExternal()`
and `writeExternal()`.

## What is the purpose of `readResolve()` method in Java Serialization?
The `readResolve()` method is used to replace 
the object read from the stream during deserialization.
This method is called after the object is deserialized,
but before it is returned to the caller.
The `readResolve()` method is useful 
when you want to ensure that only one instance of 
a class exists in the JVM.

## What happens when a non-serializable object is serialized?
If a non-serializable object is serialized,
a `NotSerializableException` is thrown at runtime.
To make an object serializable, 
it must implement the Serializable interface.

## How can you prevent certain fields from being serialized?
Certain fields can be prevented from being serialized
by marking them as transient. 
The transient keyword instructs the serialization
mechanism to skip the serialization of the marked field.

## How can you implement custom serialization and deserialization in Java?
Custom serialization and deserialization
can be implemented by implementing 
the Externalize interface and providing custom 
`readExternal()` and `writeExternal()` methods.
These methods provide full control over the
serialization and deserialization process,
allowing you to customize the behavior to your needs.
