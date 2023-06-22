# 

1. Linked List:
A linked list is a data structure where each element, called a node, contains a value and a reference to the next node in the sequence. Here's a basic implementation:

```python
class Node:
    def __init__(self, value):
        self.value = value  # Store the value of the node
        self.next = None  # Initialize the reference to the next node as None

class LinkedList:
    def __init__(self):
        self.head = None  # Initialize an empty linked list with no head node

    def append(self, value):
        new_node = Node(value)  # Create a new node with the given value
        if self.head is None:  # If the list is empty, make the new node the head
            self.head = new_node
        else:
            current_node = self.head
            while current_node.next:  # Traverse to the last node
                current_node = current_node.next
            current_node.next = new_node  # Append the new node at the end

    def display(self):
        current_node = self.head
        while current_node:  # Traverse through each node and print its value
            print(current_node.value, end=" ")
            current_node = current_node.next
        print()

# Create a new linked list
my_list = LinkedList()

# Append elements to the linked list
my_list.append(10)
my_list.append(20)
my_list.append(30)

# Display the linked list
my_list.display()
```
2. Stack:
A stack is a Last-In-First-Out (LIFO) data structure where elements are inserted and removed from the same end. Here's a simple stack implementation:

```python
class Stack:
    def __init__(self):
        self.stack = []  # Initialize an empty list to store the stack elements

    def push(self, value):
        self.stack.append(value)  # Add the value to the top of the stack

    def pop(self):
        if not self.is_empty():
            return self.stack.pop()  # Remove and return the topmost value from the stack

    def peek(self):
        if not self.is_empty():
            return self.stack[-1]  # Return the value at the top of the stack without removing it

    def is_empty(self):
        return len(self.stack) == 0  # Check if the stack is empty

    def size(self):
        return len(self.stack)  # Return the number of elements in the stack
```
### Stack using Linked List:

```python
class Node:
    def __init__(self, value):
        self.value = value  # Store the value of the node
        self.next = None  # Initialize the reference to the next node as None

class Stack:
    def __init__(self):
        self.head = None  # Initialize an empty stack with no head node

    def push(self, value):
        new_node = Node(value)  # Create a new node with the given value
        if self.head is None:  # If the stack is empty, make the new node the head
            self.head = new_node
        else:
            new_node.next = self.head  # Set the next reference of the new node to the current head
            self.head = new_node  # Update the head to the new node

    def pop(self):
        if not self.is_empty():
            value = self.head.value  # Get the value of the current head
            self.head = self.head.next  # Update the head to the next node
            return value

    def peek(self):
        if not self.is_empty():
            return self.head.value  # Return the value of the current head without removing it

    def is_empty(self):
        return self.head is None  # Check if the stack is empty

    def size(self):
        current_node = self.head
        count = 0
        while current_node:  # Traverse through each node and count the number of elements
            count += 1
            current_node = current_node.next
        return count
```
3. Queue:
A queue is a First-In-First-Out (FIFO) data structure where elements are inserted at one end and removed from the other end. Here's a basic queue implementation:

```python
class Queue:
    def __init__(self):
        self.queue = []  # Initialize an empty list to store the queue elements

    def enqueue(self, value):
        self.queue.append(value)  # Add the value to the end of the queue

    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)  # Remove and return the value from the front of the queue

    def is_empty(self):
        return len(self.queue) == 0  # Check if the queue is empty

    def size(self):
        return len(self.queue)  # Return the number of elements in the queue
```
### Queue using Linked List:

```python
class Node:
    def __init__(self, value):
        self.value = value  # Store the value of the node
        self.next = None  # Initialize the reference to the next node as None

class Queue:
    def __init__(self):
        self.head = None  # Initialize an empty queue with no head node
        self.tail = None  # Initialize the reference to the tail node as None

    def enqueue(self, value):
        new_node = Node(value)  # Create a new node with the given value
        if self.tail is None:  # If the queue is empty, make the new node both the head and the tail
            self.head = new_node
            self.tail = new_node
        else:
            self.tail.next = new_node  # Set the next reference of the tail to the new node
            self.tail = new_node  # Update the tail to the new node

    def dequeue(self):
        if not self.is_empty():
            value = self.head.value  # Get the value of the current head
            self.head = self.head.next  # Update the head to the next node
            if self.head is None:  # If the queue becomes empty after dequeueing
                self.tail = None  # Update the tail to None as well
            return value

    def is_empty(self):
        return self.head is None  # Check if the queue is empty

    def size(self):
        current_node = self.head
        count = 0
        while current_node:  # Traverse through each node and count the number of elements
            count += 1
            current_node = current_node.next
        return count
```
4. Tree:
A tree is a hierarchical data structure composed of nodes. Each node can have child nodes, forming a branching structure. Here's a simple binary tree implementation:
```python
class Node:
    def __init__(self, value):
        self.value = value  # Store the value of the node
        self.left = None  # Initialize the reference to the left child as None
        self.right = None  # Initialize the reference to the right child as None

class BinaryTree:
    def __init__(self, root):
        self.root = Node(root)  # Create a root node with the given value

    def preorder_traversal(self, node):
        if node:
            print(node.value, end=" ")  # Print the value of the current node
            self.preorder_traversal(node.left)  # Recursively traverse the left subtree
            self.preorder_traversal(node.right)  # Recursively traverse the right subtree

    def inorder_traversal(self, node):
        if node:
            self.inorder_traversal(node.left)  # Recursively traverse the left subtree
            print(node.value, end=" ")  # Print the value of the current node
            self.inorder_traversal(node.right)  # Recursively traverse the right subtree

    def postorder_traversal(self, node):
        if node:
            self.postorder_traversal(node.left)  # Recursively traverse the left subtree
            self.postorder_traversal(node.right)  # Recursively traverse the right subtree
            print(node.value, end=" ")  # Print the value of the current node
```