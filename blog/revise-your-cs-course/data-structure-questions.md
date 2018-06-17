# Data Structure Questions

**1\. What is data structure?**

A data structure is a way of organizing data that considers not only the items stored, but also their relationship to each other. Advance knowledge about the relationship between data items allows designing of efficient algorithms for the manipulation of data.

**2\. List out the areas in which data structures are applied extensively?**

1. Compiler Design,
2. Operating System,
3. Database Management System,
4. Statistical analysis package,
5. Numerical Analysis,
6. Graphics,
7. Artificial Intelligence,
8. Simulation

**3\. What are the major data structures used in the following areas : RDBMS, Network data model and Hierarchical data model.**

1. RDBMS = Array (i.e. Array of structures)
2. Network data model = Graph
3. Hierarchical data model = Trees

**4\. If you are using C language to implement the heterogeneous linked list, what pointer type will you use?**

The heterogeneous linked list contains different data types in its nodes and we need a link, pointer to connect them. It is not possible to use ordinary pointers for this. So we go for void pointer. Void pointer is capable of storing pointer to any type as it is a generic pointer type.

**5\. Minimum number of queues needed to implement the priority queue?**

Two. One queue is used for actual storing of data and another for storing priorities.

**6\. What is the data structures used to perform recursion?**

Stack. Because of its LIFO (Last In First Out) property it remembers its ‘caller’ so knows whom to return when the function has to return. Recursion makes use of system stack for storing the return addresses of the function calls.

Every recursive function has its equivalent iterative (non-recursive) function. Even when such equivalent iterative procedures are written, explicit stack is to be used.

**7\. Briefly explain recursive algorithm.**

Recursive algorithm targets a problem by dividing it into smaller, manageable sub-problems. The output of one recursion after processing one sub-problem becomes the input to the next recursive process.

**8\. Convert the expression ((A + B) * C – (D – E) ^ (F + G)) to equivalent Prefix and Postfix notations.**

1. **Prefix Notation:** – \* +ABC ^ – DE + FG
2. **Postfix Notation:** AB + C * DE – FG + ^ –

**9\. Sorting is not possible by using which of the following methods? (Insertion, Selection, Exchange, Deletion)**

**Sorting is not possible in Deletion.** Using insertion we can perform insertion sort, using selection we can perform selection sort, using exchange we can perform the bubble sort (and other similar sorting methods). But no sorting method can be done just using deletion.

**10\. What are the methods available in storing sequential files ?**

1. Straight merging,
2. Natural merging,
3. Polyphase sort,
4. Distribution of Initial runs.

**11\. List out few of the Application of tree data-structure?**

1. The manipulation of Arithmetic expression,
2. Symbol Table construction,
3. Syntax analysis.

**12\. List out few of the applications that make use of Multilinked Structures?**

1. Sparse matrix,
2. Index generation.

**13\. In tree construction which is the suitable efficient data structure? (Array, Linked list, Stack, Queue)**

Linked list is the suitable efficient data structure.

**14\. What is the type of the algorithm used in solving the 8 Queens problem?**

Backtracking.

**15\. In an AVL tree, at what condition the balancing is to be done?**

If the ‘pivotal value’ (or the ‘Height factor’) is greater than 1 or less than -1.

**16\. What is the bucket size, when the overlapping and collision occur at same time?**

One. If there is only one entry possible in the bucket, when the collision occurs, there is no way to accommodate the colliding value. This results in the overlapping of values.

**17\. Classify the Hashing Functions based on the various methods by which the key value is found.**

1. Direct method,
2. Subtraction method,
3. Modulo-Division method,
4. Digit-Extraction method,
5. Mid-Square method,
6. Folding method,
7. Pseudo-random method.

**18\. What are the types of Collision Resolution Techniques and the methods used in each of the type?**

1. **Open addressing (closed hashing),** The methods used include: Overflow block.
2. **Closed addressing (open hashing),** The methods used include: Linked list, Binary tree.

**19\. In RDBMS, what is the efficient data structure used in the internal storage representation?**

B+ tree. Because in B+ tree, all the data is stored only in leaf nodes, that makes searching easier. This corresponds to the records that shall be stored in leaf nodes.

**20\. What is a spanning Tree?**

A spanning tree is a tree associated with a network. All the nodes of the graph appear on the tree once. A minimum spanning tree is a spanning tree organized so that the total edge weight between nodes is minimized.

**21\. Does the minimum spanning tree of a graph give the shortest distance between any 2 specified nodes?**

No. The Minimal spanning tree assures that the total weight of the tree is kept at its minimum. But it doesn’t mean that the distance between any two nodes involved in the minimum-spanning tree is minimum.

**22\. Which is the simplest file structure? (Sequential, Indexed, Random)**

Sequential is the simplest file structure.

**23\. Whether Linked List is linear or Non-linear data structure?**

According to Access strategies Linked list is a linear one.  
According to Storage Linked List is a Non-linear one.

**24\. How to find middle element of linked list in one pass?**

One of the most popular question from data structures and algorithm, mostly asked on telephonic interview. Since many programmer know that, in order to find length of linked list we need to first traverse through linked list till we find last node, which is pointing to null, and then in second pass we can find middle element by traversing only half of length. They get confused when interviewer ask him to do same job in one pass. In order to find middle element of linked list in one pass you need to maintain two pointer, one increment at each node while other increments after two nodes at a time, by having this arrangement, when first pointer reaches end, second pointer will point to middle element of linked list. See this trick to find middle element of linked list in single pass for more details.

**25\. What is data structure?**

Data structure refers to the way data is organized and manipulated. It seeks to find ways to make data access more efficient. When dealing with data structure, we not only focus on one piece of data, but rather different set of data and how they can relate to one another in an organized manner.

**26\. Differentiate file structure from storage structure.**

Basically, the key difference is the memory area that is being accessed. When dealing with the structure that resides the main memory of the computer system, this is referred to as storage structure. When dealing with an auxiliary structure, we refer to it as file structure.

**27\. When is a binary search best applied?**

A binary search is an algorithm that is best applied to search a list when the elements are already in order or sorted. The list is search starting in the middle, such that if that middle value is not the target search key, it will check to see if it will continue the search on the lower half of the list or the higher half. The split and search will then continue in the same manner.

**28\. What is LIFO?**

LIFO is short for Last In First Out, and refers to how data is accessed, stored and retrieved. Using this scheme, data that was stored last , should be the one to be extracted first. This also means that in order to gain access to the first data, all the other data that was stored before this first data must first be retrieved and extracted.

**29\. What is a queue?**

A queue is a data structure that can simulates a list or stream of data. In this structure, new elements are inserted at one end and existing elements are removed from the other end.

**30\. What are binary trees?**

[![binary tree](http://cdn.career.guru99.com/wp-contenthttps://rawgit.com/sayef/tech/master/uploads/2012/05/binarytree-239x300.png "binary tree")](http://career.guru99.com/wp-content/uploads/2012/05/binarytree.png)

A binary tree is one type of data structure that has two nodes, a left node and a right node. In programming, binary trees are actually an extension of the linked list structures.

**31\. Which data structure is applied when dealing with a recursive function?**

Recursion, which is basically a function that calls itself based on a terminating condition, makes use of the stack. Using LIFO, a call to a recursive function saves the return address so that it knows how to return to the calling function after the call terminates.

**32\. What is a stack?**

A stack is a data structure in which only the top element can be accessed. As data is stored in the stack, each data is pushed downward, leaving the most recently added data on top.

**33\. Explain Binary Search Tree**

A binary search tree stores data in such a way that they can be retrieved very efficiently. The left subtree contains nodes whose keys are less than the node’s key value, while the right subtree contains nodes whose keys are greater than or equal to the node’s key value. Moreover, both subtrees are also binary search trees.

**34\. What are multidimensional arrays?**

Multidimensional arrays make use of multiple indexes to store data. It is useful when storing data that cannot be represented using a single dimensional indexing, such as data representation in a board game, tables with data stored in more than one column.

**35\. Are linked lists considered linear or non-linear data structure?**

It actually depends on where you intend to apply linked lists. If you based it on storage, a linked list is considered non-linear. On the other hand, if you based it on access strategies, then a linked list is considered linear.

**36\. How does dynamic memory allocation help in managing data?**

Aside from being able to store simple structured data types, dynamic memory allocation can combine separately allocated structured blocks to form composite structures that expand and contract as needed.

**37\. What is FIFO?**

FIFO is short for First-in, First-out, and is used to represent how data is accessed in a queue. Data has been inserted into the queue list the longest is the one that is removed first.

**38\. What is merge sort?**

Merge sort takes a divide-and-conquer approach to sorting data. In a sequence of data, adjacent ones are merged and sorted to create bigger sorted lists. These sorted lists are then merged again to form an even bigger sorted list, which continuous until you have one single sorted list.

**39\. Differentiate NULL and VOID.**

Null is actually a value, whereas Void is a data type identifier. A variable that is given a Null value simply indicates an empty value. Void is used to identify pointers as having no initial size.

**40\. What is the primary advantage of a linked list?**

A linked list is a very ideal data structure because it can be modified easily. This means that modifying a linked list works regardless of how many elements are in the list.

**41\. What is a linear search?**

A linear search refers to the way a target key is being searched in a sequential data structure. Using this method, each element in the list is checked and compared against the target key, and is repeated until found or if the end of the list has been reached.

**42\. How does variable declaration affect memory allocation?**

The amount of memory to be allocated or reserved would depend on the data type of the variable being declared. For example, if a variable is declared to be of integer type, then 32 bits of memory storage will be reserved for that variable.

**44\. What is the advantage of the heap over a stack?**

Basically, the heap is more flexible than the stack. That’s because memory space for the heap can be dynamically allocated and de-allocated as needed. However, memory of the heap can at times be slower when compared to that stack.

**45\. What is a postfix expression?**

A postfix expression is an expression in which each operator follows its operands. The advantage of this form is that there is no need to group sub-expressions in parentheses or to consider operator precedence.

**46\. What is Data abstraction?**

Data abstraction is a powerful tool for breaking down complex data problems into manageable chunks. This is applied by initially specifying the data objects involved and the operations to be performed on these data objects without being overly concerned with how the data objects will be represented and stored in memory.

**47\. How do you insert a new item in a binary search tree?**

Assuming that the data to be inserted is a unique value (that is, not an existing entry in the tree), check first if the tree is empty. If it’s empty, just insert the new item in the root node. If it’s not empty, refer to the new item’s key. If it’s smaller than the root’s key, insert it into the root’s left subtree, otherwise, insert it into the root’s right subtree.

**48\. How does a selection sort work for an array?**

The selection sort is a fairly intuitive sorting algorithm,, though not necessarily efficient. To perform this, the smallest element is first located and switched with the element at subscript zero, thereby placing the smallest element in the first position. The smallest element remaining in the subarray is then located next with subscripts 1 through n-1 and switched with the element at subscript 1, thereby placing the second smallest element in the second position. The steps are repeated in the same manner till the last element.

**49\. How do signed and unsigned numbers affect memory?**

In the case of signed numbers, the first bit is used to indicate whether positive or negative, which leaves you with one bit short. With unsigned numbers, you have all bits available for that number. The effect is best seen in the number range (unsigned 8 bit number has a range 0-255, while 8-bit signed number has a range -128 to +127.

**50\. What is the minimum number of nodes that a binary tree can have?**

A binary tree can have a minimum of zero nodes, which occurs when the nodes have NULL values. Furthermore, a binary tree can also have 1 or 2 nodes.

**51\. What are dynamic data structures?**

Dynamic data structures are structures that expand and contract as a program runs. It provides a flexible means of manipulating data because it can adjust according to the size of the data.

**52\. Do all declaration statements result in a fixed reservation in memory?**

Most declarations do, with the exemption of pointers. Pointer declaration does not allocate memory for data, but for the address of the pointer variable. Actual memory allocation for the data comes during run-time.

**53\. What is the minimum number of queues needed when implementing a priority queue?**

The minimum number of queues needed in this case is two. One queue is intended for sorting priorities while the other queue is intended for actual storage of data.

**54\. Which sorting algorithm is considered the fastest?**

There are many types of sorting algorithms: quick sort, bubble sort, balloon sort, radix sort, merge sort, etc. Not one can be considered the fastest because each algorithm is designed for a particular data structure and data set. It would depend on the data set that you would want to sort.

**55\. Differentiate STACK from ARRAY.**

Data that is stored in a stack follows a LIFO pattern. This means that data access follows a sequence wherein the last data to be stored will the first one to be extracted. Arrays, on the other hand, does not follow a particular order and instead can be accessed by referring to the indexed element within the array.

**56\. Give a basic algorithm for searching a binary search tree.**

1\. if the tree is empty, then the target is not in the tree, end search  
2\. if the tree is not empty, the target is in the tree  
3\. check if the target is in the root item  
4\. if target is not in the root item, check if target is smaller than the root’s value  
5\. if target is smaller than the root’s value, search the left subtree  
6\. else, search the right subtree

**57\. What is a dequeue?**

A dequeue is a double-ended queue. This is a structure wherein elements can be inserted or removed from either end.

**58\. What is a bubble sort and how do you perform it?**

A bubble sort is one sorting technique that can be applied to data structures such as an array. It works by comparing adjacent elements and exchanges their values if they are out of order. This method lets the smaller values “bubble” to the top of the list, while the larger value sinks to the bottom.

**59\. How does selection sort work?**

Selection sort works by picking the smallest number from the list and placing it at the front. This process is repeated for the second position towards the end of the list. It is the simplest sort algorithm.

**60\. What is a graph?**

A graph is one type of data structure that contains a set of ordered pairs. These ordered pairs are also referred to as edges or arcs, and are used to connect nodes where data can be stored and retrieved.

**61\. Differentiate linear from non linear data structure.**

Linear data structure is a structure wherein data elements are adjacent to each other. Examples of linear data structure include arrays, linked lists, stacks and queues. On the other hand, non-linear data structure is a structure wherein each data element can connect to more than two adjacent data elements. Examples of non linear data structure include trees and graphs.

**62\. What is an AVL tree?**

An AVL tree is a type of binary search tree that is always in a state of partially balanced. The balance is measured as a difference between the heights of the subtrees from the root. This self-balancing tree was known to be the first data structure to be designed as such.

**63\. What are doubly linked lists?**

Doubly linked lists are a special type of linked list wherein traversal across the data elements can be done in both directions. This is made possible by having two links in every node, one that links to the next node and other one that links to the previous node.

**64\. What is Huffman’s algorithm?**

Huffman’s algorithm is associated in creating extended binary trees that has minimum weighted path lengths from the given weights. It makes use of a table that contains frequency of occurrence for each data element.

**65\. What is Fibonacci search?**

Fibonacci search is a search algorithm that applies to a sorted array. It makes use of a divide-and-conquer approach that can greatly reduce the time needed in order to reach the target element.

------