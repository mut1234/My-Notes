# Data Structure 

## Introductions

**Data Structure** : is a date organization, management and storage format that enables efficient access and modification.

Access, Insertion, Deletion, Search

 1-Array is suitable for Access but it not suitable for Insertion & Deletion (Access is take back information).

 2-Link List is suitable for Insertion & Deletion because Link List unbounded.

# Data Structure is divided to two type:

1- **Primitive Data Structures** is a fundamental type of data structure that stores the data of only one type.

integer, float , character , pointers

2- **Non-primitive Data Structures** is a type of data structure which is a user-defined that stores the data of different types in a single entity.

 	A- Linear Data Structures(Linear Lists)          

​		Arrays, Linked List, Stack, Queue.

​	B-Non-Linear Data Structures(Non-Linear Lists)

​	    Trees,Graphs.

# Stack Data Structure 

**Stack** :is a linear data structure which follows a particular order in which the operations are performed. 

last in first out (LIFO).

First index of stack index 0 (top).

When we use Add(x) or delete() it will delete last index add in the stack.

Array-Based Implementation of the ADT Stack :

push(x), pop() ,getTop() ,isEmpty()

<img src="https://cdn.discordapp.com/attachments/755756972053233737/889182433172414464/RriebxksfzIC9SgulZmVStKixfnExlW8KhmknIhM66BReQsVBw0aNGjQoEGDBg0aNGjQoEGDBv2qh9iI6cJFRLuQAAAABJRU5Erk.png" alt="img" style="zoom:200%;" />

```java
/* Java program to implement basic stack
operations */
class Stack {
	static final int MAX = 1000;
	int top;
	int a[] = new int[MAX]; // Maximum size of Stack

	boolean isEmpty()
	{
		return (top < 0);
	}
	Stack()
	{
		top = -1;
	}

	boolean push(int x)
	{
		if (top >= (MAX - 1)) {
			System.out.println("Stack Overflow");
			return false;
		}
		else {
			a[++top] = x;
			System.out.println(x + " pushed into stack");
			return true;
		}
	}

	int pop()
	{
		if (top < 0) {
			System.out.println("Stack Underflow");
			return 0;
		}
		else {
			int x = a[top--];
			return x;
		}
	}

	int peek()
	{
		if (top < 0) {
			System.out.println("Stack Underflow");
			return 0;
		}
		else {
			int x = a[top];
			return x;
		}
	}
	
	void print(){
	for(int i = top;i>-1;i--){
	System.out.print(" "+ a[i]);
	}
}
}

// Driver code
class Main {
	public static void main(String args[])
	{
		Stack s = new Stack();
		s.push(10);
		s.push(20);
		s.push(30);
		System.out.println(s.pop() + " Popped from stack");
		System.out.println("Top element is :" + s.peek());
		System.out.print("Elements present in stack :");
		s.print();
	}
}

```

# linked List

![Linked list in C | Programming Simplified](https://www.programmingsimplified.com/images/c/linked-list.png)

**A linked list **is a linear data structure, in which the elements are not stored at contiguous memory locations. The elements in a linked list are linked using pointers.

**add()** − Appends the specified element to the end of this list.

**remove()** − Removes the first occurrence of the specified element from this list

**indexOf()** − Returns the index of the first occurrence of the specified element in this list.

**peek()**  − Retrieves, but does not remove, the head (first element) of this list.

**poll()** −  Retrieves and removes the head (first element) of this list.

**push()** − Pushes an element onto the stack represented by this list. In other words, inserts the element at the front of this list.

**pop()** −Pops an element from the stack represented by this list. In other words, removes and returns the first element of this list.

```java
import java.util.*;

public class Test {

	public static void main(String args[])
	{
		// Creating object of the
		// class linked list
		LinkedList<String> ll
			= new LinkedList<String>();

		// Adding elements to the linked list
		ll.add("A");
		ll.add("B");
		ll.addLast("C");
		ll.addFirst("D");
		ll.add(2, "E");

		System.out.println(ll);

		ll.remove("B");
		ll.remove(3);
		ll.removeFirst();
		ll.removeLast();

		System.out.println(ll);
	}
}

```



# linked stacks Data Structure

**A linked stack** is a linear list of elements commonly. implemented as a singly linked list whose start pointer. performs the role of the top pointer of a stack.

```java
// Java program to Implement a stack
// using singly linked list
// import package
import static java.lang.System.exit;

// Create Stack Using Linked list
class StackUsingLinkedlist {

	// A linked list node
	private class Node {

		int data; // integer data
		Node link; // reference variable Node type
	}
	// create global top reference variable global
	Node top;
	// Constructor
	StackUsingLinkedlist()
	{
		this.top = null;
	}

	// Utility function to add an element x in the stack
	public void push(int x) // insert at the beginning
	{
		// create new node temp and allocate memory
		Node temp = new Node();

		// check if stack (heap) is full. Then inserting an
		// element would lead to stack overflow
		if (temp == null) {
			System.out.print("\nHeap Overflow");
			return;
		}

		// initialize data into temp data field
		temp.data = x;

		// put top reference into temp link
		temp.link = top;

		// update top reference
		top = temp;
	}

	// Utility function to check if the stack is empty or not
	public boolean isEmpty()
	{
		return top == null;
	}

	// Utility function to return top element in a stack
	public int peek()
	{
		// check for empty stack
		if (!isEmpty()) {
			return top.data;
		}
		else {
			System.out.println("Stack is empty");
			return -1;
		}
	}

	// Utility function to pop top element from the stack
	public void pop() // remove at the beginning
	{
		// check for stack underflow
		if (top == null) {
			System.out.print("\nStack Underflow");
			return;
		}

		// update the top pointer to point to the next node
		top = (top).link;
	}

	public void display()
	{
		// check for stack underflow
		if (top == null) {
			System.out.printf("\nStack Underflow");
			exit(1);
		}
		else {
			Node temp = top;
			while (temp != null) {

				// print node data
				System.out.printf("%d->", temp.data);

				// assign temp link to temp
				temp = temp.link;
			}
		}
	}
}
// main class
public class GFG {
	public static void main(String[] args)
	{
		// create Object of Implementing class
		StackUsingLinkedlist obj = new StackUsingLinkedlist();
		// insert Stack value
		obj.push(11);
		obj.push(22);
		obj.push(33);
		obj.push(44);

		// print Stack elements
		obj.display();

		// print Top element of Stack
		System.out.printf("\nTop element is %d\n", obj.peek());

		// Delete top element of Stack
		obj.pop();
		obj.pop();

		// print Stack elements
		obj.display();

		// print Top element of Stack
		System.out.printf("\nTop element is %d\n", obj.peek());
	}
}

```



#  Queue Data Structure

**Queue** is an abstract data structure, somewhat similar to Stacks. Unlike stacks, a queue is open at both its ends. One end is always used to insert data (enqueue) and the other is used to remove data (dequeue). Queue follows First-In-First-Out methodology, i.e., the data item stored first will be accessed first. (FIFO).

**enqueue()** − add item to the queue.

**dequeue()** − remove item to the queue.

**peek()**  − Gets the element at the front of the queue without removing it.

**isfull()** − Checks if the queue is full.

**isempty()** − Checks if the queue is empty.

```JAVA
// Java program to demonstrate a Queue

import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {

	public static void main(String[] args)
	{
		Queue<Integer> q
			= new LinkedList<>();

		// Adds elements {0, 1, 2, 3, 4} to
		// the queue
		for (int i = 0; i < 5; i++)
			q.add(i);

		// Display contents of the queue.
		System.out.println("Elements of queue "
						+ q);

		// To remove the head of queue.
		int removedele = q.remove();
		System.out.println("removed element-"
						+ removedele);

		System.out.println(q);

		// To view the head of queue
		int head = q.peek();
		System.out.println("head of queue-"
						+ head);

		// Rest all methods of collection
		// interface like size and contains
		// can be used with this
		// implementation.
		int size = q.size();
		System.out.println("Size of queue-"
						+ size);
	}
}

```

