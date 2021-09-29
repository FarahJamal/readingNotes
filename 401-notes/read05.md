# Read: Linked Lists


## [Linked Lists](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)

**What is a Linked List**
* *Linked List* - a sequence of Nodes that are connected/linked to each other, and the defining feature of it is that each Node references the next Node in the link.
* Two types of Linked List
  - *Singly* - refers to the number of references the node has. 
    * Singly linked list - has only one reference, and the reference points to the Next node in a linked list
  - *Doubly* - refers to there being two references within the node
    * Doubly linked list - a reference to both the Next and Previous node
* *Node* - individual items/links that live in a linked list, and contains the data for each link
* *Next* - a property each node contains, and contains the reference to the next node
* *Head* - a reference type of type Node to the first node in a linked list
* *Current* - a reference type of type Node that is currently being looked at
* *Traversal* - traversing a linked list
  - Not able to use a foreach or for loop, so you have to use the Next value.
  - Next property - lead us where the next node is and allow us to extract the data appropriately.
  - while() loop - allows us to continually check that the Next node in the list is not null
  - Current node - tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end
  - NullReferenceException - gets thrown when you try to traverse on a node that is null.
* Big O 
  - Big O of time for Includes would be O(n), and in the worse case the node we are looking for will be the very last node in the linked list. 
    * n - represents the number of nodes in the linked list
  - Big O of space for Includes would be O(1), and this is because there is no additional space being used. 
* Adding a node O(1) - order of operations is extremely important when it comes to working with a Linked List.
  - To add a node with an O(1) efficiency, replace the current Head of the linked list with the new node, without losing the reference to the next node in the list.
* Adding a node O(n) - to add a node to the middle of the list first create a new node, and set the value, and then you can start adding the Add method
* Print out nodes by using the Print() method, and we will be leveraging our Current Node and a while loop to traverse through the existing linked list. The while loop will check and make sure we are not at the end of a linked list, and before before the while loop restarts move Current to equal the next node in the list. At the end it will point to null.


## [What’s a Linked List, Anyway pt1](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)

**What’s a Linked List**
* *Data structures* - different ways that we can organize our data
  - Types of data structures: variables, arrays, hashes, and objects 
* Linked lists
  - A characteristic of linked lists are linear data structures.
  - *Linear data structures* - have a sequence and an order to how they are constructed and traversed
  - Look at it like a game of hopscotch where you go through the items sequentially.
  - *Non-linear data structures* - items don’t have to be arranged in order, and can traverse data structure non-sequentially
  - *hashes* - where you organize data, and are a non-linear data structure.
  - Trees and graphs = non-linear data structures 
  - Arrays = linear data structures
* Memory management - have to pay attention the amount of memory being used with Java
  - *Abstraction* - hiding away things that you don’t need to see or deal with all of the time
  - Arrays need a certain amount of blocks of memory. They are static data structures.
  - Linked list don’t need to take up a single block of memory, and the memory that they use can be scattered throughout. It is a dynamic data structures.
  - *Static data structures* - needs all of its resources to be allocated when the structure is created, can grow or shrink, and needs a given size and amount of memory.
  - *Dynamic data structures* - shrink and grow in memory, doesn’t need a set amount of memory to be allocated in order to exist, size and shape can change, and amount of memory can change
* Parts of a linked list
  - Linked list is made up of a series of nodes. 
  - *head* - starting point of the list is a reference to the first node
  - *null* - a node that points to the the end of the list 
  - A single node is composed of data and a refernce to the node.
* Lists for all shapes and sizes
  - *Singly linked lists* - go in one direction
  - *Doubly linked list* - has two references within each node
  - *Circular linked list* - has a node that acts as the tail of the list, and and the node after the tail node is the beginning of the list


## [What’s a Linked List, Anyway pt2](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)

**Big O Notation**
* *Big O Notation* - a way of evaluating the performance of an algorithm. Another way to think of it is a way to express the amount of time that a function, action, or algorithm takes to run based on how many elements we pass to that function.
  - O - order
  - n - variable that is used for the size of the input
  - 2 Types of Big O equations - O(1) and O(n)
    * O(1) function - takes constant time or takes the same amount of time and memory to run our algorithm
    * O(n) function - input grows the space and time that we need to run that algorithm grows linearly
* Growing a linked list
  - Inserting an element into a linked list at the begining by first finding the head node of the linked list. Then make a new node, and set its pointer to the current first node of the list. Finally rearrange our head node’s pointer to point at our new node.
  - Insert at the end of the list by finding the node we want to change the pointer of, create the new node we want to insert and set its pointer, and finally direct the preceding node’s pointer to our new node. 
* To list or not to list?
  - A linked list can be difficult to search through and find a element, but if its an array you can find things more easily and quickly.