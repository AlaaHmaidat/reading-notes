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
# This function is defined in Linked List class
# Appends a new node at the end. This method is
# defined inside LinkedList class shown above


def append(self, new_data):

		# 1. Create a new node
		# 2. Put in the data
		# 3. Set next as None
		new_node = Node(new_data)

		# 4. If the Linked List is empty, then make the
		# new node as head
		if self.head is None:
			self.head = new_node
			return

		# 5. Else traverse till the last node
		last = self.head
		while (last.next):
			last = last.next

		# 6. Change the next of last node
		last.next = new_node

```

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

