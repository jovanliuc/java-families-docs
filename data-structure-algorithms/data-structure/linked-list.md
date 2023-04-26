[Back to Home](../../README.md#data-structure--algorithm)
# The Overview of Linked List
A linked list is a linear data structure in which
elements are stored in nodes. Each node contains 
a data field and a pointer or reference to the 
next node in the sequence. Linked lists are used
to implement dynamic data structures such as stacks,
queues, and associative arrays.

There are two main types of linked lists: 
singly linked lists and doubly linked lists. 
In a singly linked list, each node has a 
reference to the next node, but not the 
previous node. In a doubly linked list, 
each node has references to both the next 
and previous nodes.

Linked lists offer several advantages over
arrays. They can be dynamically resized 
without the need to copy elements to a new 
location in memory. They can also be easily
traversed in either direction, making them 
ideal for implementing data structures such 
as stacks and queues.

However, linked lists also have some disadvantages.
They do not provide constant-time access to 
individual elements like arrays do. Instead,
elements must be accessed sequentially by 
traversing the list. Additionally, linked
lists require extra memory to store the pointers 
or references to the next and previous nodes.

Despite these limitations, linked lists are still
widely used in computer programming due to their 
flexibility and ease of implementation.

# Examples
**Implementing a singly linked list with a remove method:**
```java
class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class LinkedList {
    Node head;

    public LinkedList() {
        this.head = null;
    }

    public void add(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node curr = head;
        while (curr.next != null) {
            curr = curr.next;
        }
        curr.next = newNode;
    }

    public void remove(int data) {
        if (head == null) {
            return;
        }
        if (head.data == data) {
            head = head.next;
            return;
        }
        Node curr = head;
        while (curr.next != null && curr.next.data != data) {
            curr = curr.next;
        }
        if (curr.next != null) {
            curr.next = curr.next.next;
        }
    }

    public void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }
}

public class Main {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.remove(3);
        list.printList(); // Output: 1 2 4
    }
}
```
In this example, we add a remove method to 
the LinkedList class that removes the first 
occurrence of a specified element from the list.
If the element is not found in the list,
nothing happens. We also add some additional 
elements to the list and remove an element
before printing the list.

**Implementing a doubly linked list:**
```java
class Node {
    int data;
    Node prev;
    Node next;

    public Node(int data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}

class DoublyLinkedList {
    Node head;
    Node tail;

    public DoublyLinkedList() {
        this.head = null;
        this.tail = null;
    }

    public void add(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            tail = newNode;
            return;
        }
        tail.next = newNode;
        newNode.prev = tail;
        tail = newNode;
    }

    public void printList() {
        Node curr = head;
        while (curr != null) {
            System.out.print(curr.data + " ");
            curr = curr.next;
        }
        System.out.println();
    }
}

public class Main {
    public static void main(String[] args) {
        DoublyLinkedList list = new DoublyLinkedList();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.printList(); // Output: 1 2 3 4
    }
}
```
In this example, we define a `Node` class with 
references to the previous and next nodes in the list.
We also define a `DoublyLinkedList` class with 
references to both the head and tail of the list.

The `add` method adds a new `Node` to the end of the
list by updating the `next` reference of the current 
tail node and the `prev` reference of the new node.