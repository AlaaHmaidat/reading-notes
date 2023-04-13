# Linked Lists

A linked list is a linear data structure, in which the elements are not stored at contiguous memory locations. The elements in a linked list are linked using pointers as shown in the below image:

![](https://miro.medium.com/v2/resize:fit:720/format:webp/1*hk2vLhF9CK94grEu93pzLQ.png) 

## Insertion in Linked List
1. Find the head node of the linked list.
2. Create a new node and set its pointer to the current first node of the list.
3. Rearrange the head node's pointer to point at the new node.

![](https://cdn.procoding.org/datastructures/linkedlist/singly-linked-list/singly-linked-list-insert-at-end.gif) 

Following are the 6 steps to add a node at the end.

```python
# Define the Node class
class Node:
  
    # Constructor to initialize the node object
    def __init__(self, data):
        self.data = data  # Assign data
        self.next = None  # Initialize next as null
  
# Define the LinkedList class
class LinkedList:
  
    # Constructor to initialize the head of the linked list
    def __init__(self):
        self.head = None
  
    # This method appends a new node at the end of the linked list
    def append(self, new_data):
        
        # Create a new node with the given data
        new_node = Node(new_data)

        # If the linked list is empty, make the new node the head
        if self.head is None:
            self.head = new_node
            return

        # Traverse the linked list to find the last node
        last = self.head
        while last.next:
            last = last.next

        # Change the next of the last node to the new node
        last.next = new_node
  
    # This method prints the linked list starting from the head
    def printList(self):
        temp = self.head
        while temp:
            print(temp.data)
            temp = temp.next

# Example usage:
if __name__ == '__main__':
    # Create a new linked list object
    llist = LinkedList()

    # Add nodes to the linked list
    llist.append(1)
    llist.append(2)
    llist.append(3)

    # Print the contents of the linked list
    llist.printList()
```
## Types of linked lists

### There are three types of linked lists: singly, doubly and circular

1. A singly linked list is a linear data structure in which the elements are not stored in contiguous memory locations and each element is connected only to its next element using a pointer

2. A doubly linked list is a complex type of linked list in which a node contains a pointer to the previous as well as the next node in the sequence. Therefore, in a doubly linked list, a node consists of three parts: node data, pointer to the next node in sequence (next pointer) , pointer to the previous node (previous pointer).

![](../img/linked%20list%20-%20singly%20and%20doubly.png) 

3. A circular linked list is a type of linked list in which the first and the last nodes are also connected to each other to form a circle.

![](../img/circular%20linked%20list.png)

## Big O

 [Click here to now what is the Big(O)](../ReadClass01/README.md) 


 ### Comparing Arrays and Linked Lists

 | Data Structure Type | Access Time | Insert Time | Delete Time | Search Time |
|---------------------|-------------|-------------|-------------|-------------|
| Array               | O(1)        | O(n)        | O(n)        | O(n)        |
| Linked List         | O(n)        | O(1) or O(n)| O(1) or O(n)| O(n)        |


### WHY Big O for Linked Lists = O(n) and Arrays = O(1)

In a linked list, each element (or node) has a reference or pointer to the next element in the list. To access an element in a linked list, you have to traverse the list starting from the head node until you find the desired element.

This means that the time it takes to access an element in a linked list is proportional to the size of the list, because you may have to traverse the entire list to find the element you're looking for. Therefore, the time complexity of accessing an element in a linked list is O(n), where n is the size of the list.

On the other hand, in an array, you can access an element directly by its index because the elements are stored contiguously in memory. Therefore, the time complexity of accessing an element in an array is constant, or O(1), regardless of the size of the array.


## Things I want to know more about