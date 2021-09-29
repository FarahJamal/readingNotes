# Read: Linked Lists


## [Linked Lists]
A linked list is a linear data structure, in which the elements are not stored at contiguous memory locations.

Singly linked lists are the simplest type of linked list, based solely on the fact that they only go in one direction.

Doubly linked list are two references contained within each node: a reference to the next node, as well as the previous node.

A circular linked list is a sequence of elements in which every element has a link to its next element in the sequence and the last element has a link to the first element. That means circular linked list is similar to the single linked list except that the last node points to the first node in the list.

Big O – evaluates the performance of an algorithm. One of the important things to consider w/ Big O is the time it requires at runtime and how much memory is needed (time and space).

 - gets thrown when you try to traverse on a node that is null.

* Big O 
  - Big O of time for Includes would be O(n), and in the worse case the node we are looking for will be the very last node in the linked list. 
    * n - represents the number of nodes in the linked list
  - Big O of space for Includes would be O(1), and this is because there is no additional space being used. 
* Adding a node O(1) - order of operations is extremely important when it comes to working with a Linked List.
  - To add a node with an O(1) efficiency, replace the current Head of the linked list with the new node, without losing the reference to the next node in the list.
* Adding a node O(n) - to add a node to the middle of the list first create a new node, and set the value, and then you can start adding the Add method
* Print out nodes by using the Print() method, and we will be leveraging our Current Node and a while loop to traverse through the existing linked list. The while loop will check and make sure we are not at the end of a linked list, and before before the while loop restarts move Current to equal the next node in the list. At the end it will point to null.

![](https://i.redd.it/ueszgegodtl21.png)


