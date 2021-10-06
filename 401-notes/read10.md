# Stacks and Queues

**What is Stack and where it can be used?**

- Stack is a linear data structure which the order LIFO(Last In First Out) or FILO(First In Last Out) for accessing elements. Basic operations of the stack are: Push, Pop, Peek


Applications of Stack: 

  - Infix to Postfix Conversion using Stack
  - Evaluation of Postfix Expression
  - Reverse a String using Stack
  - Implement two stacks in an array
  - Check for balanced parentheses in an expression


 ![](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/how-to-implement-stack-push-operation-cf97479ab11316c4.png)


**What is a Queue, how it is different from the stack and how is it implemented?** 
- Queue is a linear structure that follows the order is First In First Out (FIFO) to access elements. Mainly the following are basic operations on queue: Enqueue, Dequeue, Front, Rear 
The difference between stacks and queues is in removing.

- In a stack we remove the item the most recently added; in a queue, we remove the item the least recently added. Both Queues and Stacks can be implemented using Arrays and Linked Lists. 


***How to implement a stack using queue?***

- A stack can be implemented using two queues. Let stack to be implemented be ‘s’ and queues used to implement be ‘q1’ and ‘q2’. Stack ‘s’ can be implemented in two ways: 

   - Method 1 (By making push operation costly)
  - Method 2 (By making pop operation costly)

- How to implement a queue using stack? 
A queue can be implemented using two stacks. Let queue to be implemented be q and stacks used to implement q be stack1 and stack2. q can be implemented in two ways: 

  - Method 1 (By making enQueue operation costly)
  -  Method 2 (By making deQueue operation costly) See Implement Queue using Stacks

![](https://cdn.programiz.com/sites/tutorial2program/files/queue-implementation.png)


![](https://pics.me.me/i-think-they-mean-stack-and-queue-68776185.png)