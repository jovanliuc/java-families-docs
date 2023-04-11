[Back to Home](../README.md)
# Java Collection Overview
Java Collection Framework is a set of classes 
and interfaces in Java that provide an architecture 
to store and manipulate groups of objects. 
The Java Collection Framework contains interfaces 
and classes that represent different types
of collections like List, Set, Queue, Map, etc. 
These collections can be used to store 
and manipulate different types of data in Java.

Here are some of the key interfaces and classes 
in the Java Collection Framework:

> - Collection: This is the root interface 
> of the collection hierarchy. 
> It represents a group of objects known as elements. 
> It defines the basic operations like add, remove, 
> and contains that all collections should support.
> - List: This is an ordered collection 
> that allows duplicate elements.
> It provides operations like add, remove, get, 
> and set.
> - Set: This is an unordered collection 
> that does not allow duplicate elements.
> It provides operations like add, remove,
> and contains.
> - Map: This is a collection of key-value pairs, 
> where each key must be unique. 
> It provides operations like put, get, remove,
> and containsKey.
> - Queue: This is a collection used 
> to hold elements prior to processing. 
> It supports operations like add, remove, 
> and element.

There are other specialized collections
like SortedSet, SortedMap, Deque, etc. 
that provide additional functionality.

Java Collection Framework provides a rich set of APIs
to manipulate collections. 
It provides various algorithms like sorting, 
searching, shuffling, etc. that can be applied
to collections. It also provides utility classes 
like Collections and Arrays that provide various methods
to work with collections and arrays.

Overall, Java Collection Framework provides a powerful 
and flexible way to work with collections 
of data in Java.

# HashMap
The internal structure of a HashMap in Java 
is a hash table, 
which is implemented as an array of linked lists. 
Each element of the array is a "bucket" 
that contains a linked list of key-value pairs 
that hash to the same index. 
The following is a simplified representation
of the internal structure of a HashMap:

```rust
[ Bucket 0 ] -> (key1, value1) -> (key2, value2) -> ...
[ Bucket 1 ] -> (key3, value3) -> ...
[ Bucket 2 ] -> ...
...
[ Bucket n ] -> ...
```

Here, the Bucket arrays represent the array 
of linked lists used to store the key-value pairs 
in the map. Each linked list contains key-value pairs 
that hash to the same index in the table.

When a new key-value pair is added to the HashMap,
its key is hashed to a numeric index using 
the hash function, and the pair is stored 
in the linked list at the corresponding index
in the bucket array. If the key already exists 
in the map, its corresponding value is updated
with the new value.

When a key is looked up in the HashMap, 
its key is hashed to find the appropriate index,
and the corresponding linked list is searched 
to find the matching key-value pair. 
If the key is not found, null is returned.

The size of the HashMap is determined 
by the number of key-value pairs stored in the map.
As more pairs are added to the map, 
the internal array of linked lists may need 
to be resized to maintain a reasonable load factor.

In Java 8 and later versions, the implementation 
of HashMap has been optimized to use a combination
of a hash table and a Red-Black Tree to improve 
the worst-case performance of certain operations,
as I explained in my previous response.

Overall, the internal structure of a HashMap
in Java allows for efficient storage and retrieval 
of key-value pairs using a hash table 
with linked lists to handle collisions. 
By using an appropriate hash function 
and managing the load factor, 
HashMap can provide constant-time performance 
for adding, removing, and looking up elements
in the map.

# Hashtable
In Java, a Hashtable is implemented as an array 
of linked lists. Each element of the array is a bucket,
and each bucket can contain zero or more entries 
(key-value pairs). When a key-value pair is added 
to the Hashtable, the key is hashed to determine
which bucket it should be placed in. 
If there are no entries in that bucket, 
a new entry is added to the bucket. 
If there are already entries in the bucket, 
the new entry is added to the end of the linked list 
in the bucket.

The hash function used by the Hashtable class 
maps keys to bucket indices in a way that is intended
to minimize collisions (when two keys hash to 
the same index). This is achieved 
by using a combination of the key's hash code 
and a prime number. The resulting hash value 
is then modulo-ed with the size of the array 
to get the index of the bucket.

When retrieving a value from a Hashtable, 
the key is hashed to determine which bucket 
it should be in, and then the linked list in
that bucket is searched for an entry 
with a matching key. If a matching entry is found, 
its value is returned. If no matching entry is found,
null is returned.

To ensure thread-safety, access to the Hashtable array 
of buckets is synchronized. This means 
that only one thread can modify the Hashtable 
at a time, which can slow down performance 
in multithreaded environments. 
However, this also ensures that the Hashtable 
is safe to use in concurrent applications.

Sure, here's an example of how to use a Hashtable 
in Java:

```java
import java.util.Hashtable;

public class ExampleHashtable {
public static void main(String[] args) {

        // Creating a Hashtable with String keys and Integer values
        Hashtable<String, Integer> grades = new Hashtable<>();
        
        // Adding key-value pairs to the Hashtable
        grades.put("John", 90);
        grades.put("Mary", 85);
        grades.put("Bob", 95);
        
        // Retrieving a value from the Hashtable using its key
        int johnGrade = grades.get("John");
        System.out.println("John's grade is " + johnGrade);
        
        // Checking if a key exists in the Hashtable
        boolean bobExists = grades.containsKey("Bob");
        if (bobExists) {
            System.out.println("Bob's grade is " + grades.get("Bob"));
        } else {
            System.out.println("Bob is not in the Hashtable.");
        }
        
        // Removing a key-value pair from the Hashtable
        grades.remove("Mary");
        System.out.println("Hashtable after removing Mary: " + grades);
    }
}
```

In this example, we create a Hashtable object 
called grades that maps String keys (student names) 
to Integer values (test grades). 
We add three key-value pairs to the Hashtable
using the put() method.

We then use the get() method to retrieve John's grade
by passing his name as the key. 
We also use the containsKey() method 
to check if Bob's key exists in the Hashtable. 
If it does, we retrieve and print out his grade. 
If it doesn't, we print out a message saying 
that Bob is not in the Hashtable.

Finally, we remove Mary's key-value pair 
from the Hashtable using the remove() method, 
and print out the Hashtable to show 
that her key-value pair has been removed.

# Array
In Java, an array is an object that holds a fixed number 
of values of the same data type. 
The elements of an array can be accessed 
by their index, which starts at 0.

To create an array in Java,
you need to specify the data type of the elements 
and the number of elements the array can hold. 
Here's an example of creating an array
of integers with 5 elements:

```java
int[] numbers = new int[5];
```

This creates an array named numbers 
that can hold 5 integers. 
The elements in the array are initialized
to their default value, which for integers is 0.

You can also initialize the elements 
of an array when you create it, like this:

```java
int[] numbers = {1, 2, 3, 4, 5};
```

This creates an array named numbers 
with 5 elements that are initialized 
to the values 1, 2, 3, 4, and 5.

To access an element in an array, 
you use the index of the element in square brackets
after the array name. For example:

```java
int firstNumber = numbers[0]; // gets the first element in the array
numbers[2] = 10; // sets the third element in the array to 10
```

You can also loop through an array using a for loop,
like this:

```java
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```
This will print out each element in the numbers array 
on a separate line.

Arrays can be used in many ways in Java,
such as storing and manipulating data, sorting 
and searching algorithms,
and implementing data structures like stacks 
and queues.

# List
In Java, a List is an interface that defines 
an ordered collection of elements,
where duplicate elements are allowed.
Some key features of a List in Java are:

- Lists maintain the insertion order of the elements, 
which means the elements are added to the list 
in a specific order and that order 
is maintained throughout the life of the list.
- Lists allow duplicate elements, 
which means the list can have multiple occurrences 
of the same element.
- Lists allow null elements (unless otherwise specified).
- Lists can be accessed and modified by their index positions.
- Lists can be iterated over using various methods 
provided by the List interface.
- There are several classes in Java 
that implement the List interface, 
including ArrayList, LinkedList, Vector, and Stack.
Each of these classes has its own characteristics 
and performance characteristics,
so choosing the right one for your use case 
is important.

To use a List in Java, you first need to import
the List interface and the appropriate class 
that implements it. For example, 
to use an ArrayList, you would import both 
the List interface and the ArrayList class as follows:

```java
import java.util.List;
import java.util.ArrayList;
```

Then, you can create a new ArrayList 
and add elements to it like this:

```java
List<String> myList = new ArrayList<>();
myList.add("apple");
myList.add("banana");
myList.add("orange");
```

You can also access and modify elements 
in the list by their index positions, like this:

```java
String secondElement = myList.get(1); // "banana"
myList.set(2, "grapefruit");
```

And you can iterate over the list using a for loop 
or a for-each loop, like this:

```java
for (int i = 0; i < myList.size(); i++) {
    String element = myList.get(i);
    System.out.println(element);
}

for (String element : myList) {
    System.out.println(element);
}
```

# Set
In Java, a Set is an interface in the Java Collections 
Framework that represents a collection 
of unique elements. It is similar to a List, 
but unlike a List, a Set does not allow 
duplicate elements.

Java provides several implementations 
of the Set interface, including:

HashSet: This is the most commonly used 
implementation of the Set interface. 
It uses a hash table to store elements 
and offers constant-time performance 
for the basic operations (add, remove, and contains).

TreeSet: This implementation uses a tree structure 
to store elements, which allows for efficient traversal 
of the elements in sorted order. 
However, the basic operations 
(add, remove, and contains) have a time complexity 
of O(log n).

LinkedHashSet: This implementation is similar 
to HashSet, but it maintains a linked list
of the elements in insertion order. 
This means that iterating over the elements 
in a LinkedHashSet will return them in the order
in which they were added.

All Set implementations in Java provide 
the basic operations of adding, removing, 
and checking if an element is present in the Set. 
They also support operations for iterating over 
the elements in the Set, checking the size 
of the Set, and checking if the Set is empty.

Here's an example of how to create a HashSet 
and add elements to it:

```java
Set<String> mySet = new HashSet<>();
mySet.add("apple");
mySet.add("banana");
mySet.add("orange");
```

In this example, we create a Set of Strings
using the HashSet implementation, 
and then add three elements to the Set.
Since Sets do not allow duplicates, 
if we try to add an element that is already 
in the Set, it will be ignored.

# Stack
In Java, a stack is a data structure 
that allows operations to be performed 
on a collection of elements in a last-in, 
first-out (LIFO) order. The stack has two 
main operations: push and pop.

The push operation adds an element to the top 
of the stack, while the pop operation removes 
the element at the top of the stack. 
Other common operations include peek, 
which returns the element at the top of the stack 
without removing it, and isEmpty, which checks 
if the stack is empty.

Java provides a built-in implementation 
of the stack data structure called java.util.Stack.
It is a subclass of the Vector class and provides 
all the operations mentioned above. 
However, the use of java.util.Stack is discouraged 
due to its synchronization overhead 
and poor performance compared to other implementations.

Instead, the Deque interface is preferred 
for implementing a stack in Java. 
Deque stands for double-ended queue 
and provides the same LIFO behavior as a stack. 
The LinkedList class in Java implements the Deque interface 
and can be used to create a stack. 
Here is an example of using LinkedList 
to create a stack in Java:

```java
import java.util.LinkedList;

public class StackExample {
    public static void main(String[] args) {
        LinkedList<Integer> stack = new LinkedList<Integer>();
        
        stack.push(1);
        stack.push(2);
        stack.push(3);
        
        System.out.println("Stack: " + stack);
        
        int top = stack.pop();
        System.out.println("Popped element: " + top);
        System.out.println("Stack after pop: " + stack);
        
        int peek = stack.peek();
        System.out.println("Peeked element: " + peek);
        System.out.println("Stack after peek: " + stack);
    }
}
```

This code creates a stack of integers 
using LinkedList and performs push, pop, 
and peek operations on it. The output of the program will be:

```yaml
Stack: [3, 2, 1]
Popped element: 3
Stack after pop: [2, 1]
Peeked element: 2
Stack after peek: [2, 1]
```

# Vector
Java Vector is a dynamic array-like data structure 
that can resize itself automatically. 
It is similar to an ArrayList, 
but Vector is synchronized, 
which means that all its methods are thread-safe.
This makes Vector suitable for use 
in multithreaded applications.

To use Vector in your Java program, 
you need to import the java.util.
Vector package. Here is an example 
of how to create a Vector:

```java
import java.util.Vector;

public class Main {
    public static void main(String[] args) {
        Vector<Integer> v = new Vector<Integer>();
        v.add(1);
        v.add(2);
        v.add(3);
        System.out.println(v);
    }
}
```

In this example, we create a Vector of type Integer 
and add three elements to it using the add() method.
Finally, we print the contents of the Vector 
using the println() method.

Vector has many methods that you can use 
to manipulate its contents, including add(), 
remove(), size(), get(), and set(). 
It also has methods for iterating over its elements,
such as iterator(), listIterator(), and forEach(). 
Additionally, Vector supports various methods 
for searching and sorting its elements.

Note that while Vector is thread-safe, 
its synchronization can have a performance impact.
If you do not need thread-safety, consider 
using ArrayList instead.

# Queue
In Java, a queue is a collection of elements
that follow the FIFO (first-in, first-out) principle.
The Java Queue interface is a subtype 
of the Java Collection interface and provides 
a set of methods for performing various operations 
on the elements of a queue.

Some common methods provided by the Java Queue interface are:

- add(element) - This method adds an element to the end of the queue.
- remove() - This method removes and returns the element at the front of the queue.
- peek() - This method returns the element at the front of the queue without removing it.
- isEmpty() - This method returns true if the queue is empty, false otherwise.
- size() - This method returns the number of elements in the queue.

There are several classes in Java 
that implement the Queue interface, 
including LinkedList, ArrayDeque, and PriorityQueue.
Here is an example of how to use 
the LinkedList class to create a queue:

```java
import java.util.LinkedList;
import java.util.Queue;

public class ExampleQueue {

    public static void main(String[] args) {

        Queue<String> queue = new LinkedList<>();

        // Adding elements to the queue
        queue.add("element1");
        queue.add("element2");
        queue.add("element3");

        // Displaying the elements of the queue
        System.out.println("Elements in the queue: " + queue);

        // Removing the element at the front of the queue
        String removedElement = queue.remove();
        System.out.println("Removed element: " + removedElement);

        // Displaying the elements of the queue after removal
        System.out.println("Elements in the queue: " + queue);

        // Checking if the queue is empty
        boolean isQueueEmpty = queue.isEmpty();
        System.out.println("Is the queue empty? " + isQueueEmpty);

        // Retrieving the element at the front of the queue without removing it
        String frontElement = queue.peek();
        System.out.println("Element at the front of the queue: " + frontElement);
    }
}
```

Output:

```yaml
Elements in the queue: [element1, element2, element3]
Removed element: element1
Elements in the queue: [element2, element3]
Is the queue empty? false
Element at the front of the queue: element2
```