[Back to Home](../../README.md)
# The Overview of Stack
A stack is a linear data structure that stores
a collection of elements, where the order in
which elements are added or removed is based 
on the "last-in, first-out" (LIFO) principle.

A stack has two primary operations:
- Push: This operation adds an element to 
the top of the stack.
- Pop: This operation removes and returns 
the element at the top of the stack.

Other common operations include:
- Peek: This operation returns the element at the 
top of the stack without removing it.
- isEmpty: This operation checks whether 
the stack is empty or not.

Stacks can be implemented using arrays or linked lists. 
The advantage of using an array is that it provides 
constant-time access to any element, but the
disadvantage is that it has a fixed size. A linked 
list-based implementation does not have a fixed size 
but requires more memory and has slower access times.

Some common applications of stacks include expression
evaluation, recursive function calls, 
and backtracking algorithms.

# Examples
Sure, here are some examples of implementing
a stack data structure in Java:

Using Array:
```java
public class Stack {

   private int top;
   private int[] arr;
   private int capacity;

   // Constructor to initialize the stack
   public Stack(int size) {
      arr = new int[size];
      capacity = size;
      top = -1;
   }

   // Method to push an element to the stack
   public void push(int element) {
      if (isFull()) {
         System.out.println("Stack Overflow");
      } else {
         top++;
         arr[top] = element;
      }
   }

   // Method to pop an element from the stack
   public int pop() {
      if (isEmpty()) {
         System.out.println("Stack Underflow");
         return -1;
      } else {
         int element = arr[top];
         top--;
         return element;
      }
   }

   // Method to check if the stack is empty
   public boolean isEmpty() {
      return (top == -1);
   }

   // Method to check if the stack is full
   public boolean isFull() {
      return (top == capacity - 1);
   }

   // Method to return the top element of the stack without removing it
   public int peek() {
      if (isEmpty()) {
         System.out.println("Stack Underflow");
         return -1;
      } else {
         return arr[top];
      }
   }

   // Method to return the size of the stack
   public int size() {
      return top + 1;
   }
}
```

Using LinkedList:
```java
public class Stack {

   private Node top;

   // Constructor to initialize the stack
   public Stack() {
      top = null;
   }

   // Method to push an element to the stack
   public void push(int element) {
      Node newNode = new Node(element);
      if (top == null) {
         top = newNode;
      } else {
         newNode.next = top;
         top = newNode;
      }
   }

   // Method to pop an element from the stack
   public int pop() {
      if (isEmpty()) {
         System.out.println("Stack Underflow");
         return -1;
      } else {
         int element = top.data;
         top = top.next;
         return element;
      }
   }

   // Method to check if the stack is empty
   public boolean isEmpty() {
      return (top == null);
   }

   // Method to return the top element of the stack without removing it
   public int peek() {
      if (isEmpty()) {
         System.out.println("Stack Underflow");
         return -1;
      } else {
         return top.data;
      }
   }

   // Method to return the size of the stack
   public int size() {
      int count = 0;
      Node current = top;
      while (current != null) {
         count++;
         current = current.next;
      }
      return count;
   }

   // Node class to represent the elements of the stack
   private static class Node {
      int data;
      Node next;

      public Node(int data) {
         this.data = data;
         next = null;
      }
   }
}
```

These are just two examples of implementing a stack 
data structure in Java, there are many other ways 
to do it as well.
