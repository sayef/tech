Linked List Basics
==================

A linked list is a data structure for storing, searching, manipulating and doing many more with a list of data. ‘Array’ data structure has some limitations that can be overcome easily by the linked list having some dynamic features. Let’s see what a linked list can do –

*   Successive elements are connected by pointers.
*   Last element points to NULL.
*   It can grow or shrink in size during execution of a program.
*   It can be made just as long as required.
*   It does not waste memory space.

![1](https://rawgit.com/sayef/tech/master/uploads/2015/08/1.png?w=300)

Fig: Liked List Structure

We must know the pointer to the first element of the list (called start, head, etc.).  
**Insertion and Deletion in linked list:  
**  
For insertion:

*   A record is created holding the new item.
*   The nextpointer of the new record is set to link it to the item which is to follow it in the list.
*   The nextpointer of the item which is to precede it must be modified to point to the new item.

![linked list insertion](https://rawgit.com/sayef/tech/master/uploads/2015/08/2.png?w=300)Fig: Linked List Insertion

For deletion:

*   The nextpointer of the item immediately preceding the one to be deleted is altered, and made to point to the item following the deleted item.

![Fig: Linekd List Deletion](https://rawgit.com/sayef/tech/master/uploads/2015/08/3.png?w=300)

Fig: Linekd List Deletion

**Array versus Linked Lists**

*   Inserting/deleting an element at the end.
*   Randomly accessing any element.
*   Searching the list for a particular value.
*   Inserting an element.
*   Deleting an element.
*   Applications where sequential access is required.
*   In situations where the number of elements cannot be predicted beforehand.

**Types of Lists**  
Depending on the way in which the links are used to maintain adjacency, several different types of linked lists are possible.

**2\. Circular linked list :** The pointer from the last element in the list points back to the first element.

![Fig: Circular Linked List](https://rawgit.com/sayef/tech/master/uploads/2015/08/4.png?w=300)

Fig: Circular Linked List

**3\. Doubly linked list:**

*   Pointers exist between adjacent nodes in both directions.
*   The list can be traversed either forward or backward.
*   Usually two pointers are maintained to keep track of the list, head and tail.

![Fig: Doubly Linked List](https://rawgit.com/sayef/tech/master/uploads/2015/08/5.png?w=300)

Fig: Doubly Linked List

**Basic Operations on a List**

*   Creating a list
*   Traversing the list
*   Inserting an item in the list
*   Deleting an item from the list
*   Concatenating two lists into one

First of all we need to declare a user defined structure that will carry the information and same type of pointer variable that will lead us to the next address of the element of the list.Let’s declare a node which will hold student info containing roll, name, age of any student and the pointer to the next student of the list.

``` c++
/* definition of a data node for holding student information */

struct node {
   int roll;
   char name[20];
   int  age;
   struct node *next;
};

```



Initialization of the head node of the list from where we will always start our look up for insertion, deletion and searching any node on any key i.e. name, roll or age –

```
/* head points to first node in list*/
struct node *head = (struct node *) NULL;
```

Allocating memory for the newly created node will be looking like the following-

```c++
/* this initialises a node, allocates memory for the node, and returns   */
/* a pointer to the new node. Must pass it the node details, name and id */
struct node * initnode( int roll, char *name, int age )
{
   struct node *ptr;
   ptr = (struct node *) calloc( 1, sizeof(struct node ) );
   if( ptr == NULL )                       /* error allocating node?      */
       return (struct node ) NULL;         /* then return NULL, else      */
   else {                                  /* allocated node successfully */
       ptr->roll = roll;                   /* copy roll                   */
       strcpy( ptr->name, name );          /* fill in name details        */
       ptr->age = age;                     /* copy age                    */
       return ptr;                         /* return pointer to new node  */
   }
}
```



Or if we want to allocate memory so simply C++ provides the following API. Just we need to assign the name and id.

```c++
struct node * initnode( int roll, char *name, int age )
{
  node *ptr; 
  ptr = new node();
  str->roll = roll;
  strcpy(ptr->name, name);
  ptr->age = age;
  return ptr;
}
```



So our first node is created-

![Fig: Head/First node](https://rawgit.com/sayef/tech/master/uploads/2015/08/6.png?w=300)

Fig: Head/First node

* * *

###### **CREATING LIST**

* * *

If there are n number of nodes in the initial linked list:

1. Allocate n records, one by one.

2. Read in the fields of the records.

3. Modify the links of the records so that the chain is formed.

  ```c++
  node create_list(int n, node *head)	 	 
  {	 	 
   int i, n;	 	 
   node *p; // pointer that will iterate through the list	 	 
   p = head; //first pointer must be the head node	 	 
   for(i=1; i<=n; i++) { 	 	 
       scanf("%d %s %d", &p->roll, p->name, &p->age); //put the values in p	 	 
       if(i==n) // for the last element	 	 
       {	 	 
          p->next = NULL; //there is no next element and this is the end of the list
       }	 	 
       else	 	 
       {	 	 
          node *nextNode = (node *) malloc(sizeof(node)); //allocating memory for the next node	 	 
          p->next = nextNode; //pointing nextNode as the next node of p	 	 
          p = p->next; //now p be the next node for the sake of iteration	 	 
       }	 	 
    }	 	 
   }
  ```

  

* * *

**TRAVERSING LIST**

* * *

1. Follow the pointers.

2. Display the contents of the nodes as they are traversed.

3. Stop when the nextpointer points to NULL.

  ```c++
  void display (node *head)	 	 
  {	 	 
   int i = 1;	 	 
   node *p;	 	 
   p = head;	 	 
   while (p != NULL)	 	 
   {	 	 
      printf("\nNode%d: %d %s %d", i, p->roll, p->name, p->age);	 	 
      i++;	 	 
      p = p->next;	 	 
    }	 	 
    printf("\n");	 	 
   }
  
  ```

  

**INSERTING AN ITEM IN THE LIST**  

* * *

Suppose the problem is to insert a node before a specified node.

*   Specified means some value is given for the node (called key).
*   In this example, we consider it to be roll.

We have to maintain three different cases here.  
**Case 1: When a node is added at the beginning-**

1.  Only one next pointer needs to be modified.
2.  A new node is made the head
3.  New node points to the previously first element.

![Fig: Insert Before Head](https://rawgit.com/sayef/tech/master/uploads/2015/08/7.png?w=300)

Fig: Insert Before Head

**Case 2: When a node is added at the end-**

1.  Two next pointers need to be modified.
2.  Last node now points to a new node.
3.  New node points to NULL.

![Fig: Insert at the end](https://rawgit.com/sayef/tech/master/uploads/2015/08/8.png?w=300)

Fig: Insert at the end

1.  Two next pointers need to be modified.
2.  Previous node now points to the new node.
3.  New node points to the next node.

![Fig: Insert at the middle of two nodes](https://rawgit.com/sayef/tech/master/uploads/2015/08/9.png?w=300)

Fig: Insert at the middle of two nodes

Let’s see the code snippet for the insertion into the existing list:  
Convention: Put it before a key (here we assume roll). If there is no such key put it to the last.

```c++
 //node new has new roll, name, age	 	 
 //key is the roll of the node before which we will put the new node	 	 
 void insert (node *head, node *new, int key)	 	 
 {	 	 
   node *p, *q;	 	 
   p = *head; // iterate starts from the head	 	 
   if(p == null)	 
   {	 	 
      new->next = p;	 	 
      head = new;	 	 
   }	 	 
   else	 	 
   {	 	 
     while (p != NULL && p->roll != key) //iterate as long as we reach the end or get the key	 	 
     {	 	 
        q = p; // q keeps track of the previous node	 	 
        p = p->next;	 	 
     }	 	 
     else 
     {	 	 
       q->next = new;	 	 
       new->next = NULL;	 	 
     }	 	 
   }	 	 
 }	 
 
int main()	 	 
{	 	 
   ......	 	 

   //assume the head and initial list is already created so far	 	 

   ......	 	 

   node *new = (node *) malloc(sizeof(node));	 	 
   int key;	 	 
   scanf("%d %s %d %d", &new->roll, new->name, &new->age, &key); // take the info of new node and the key	 	 
   insert(head, new, key);	 	 
 }
```



* * *

**DELETING AN ITEM FROM THE LIST**  

* * *

Here also we are required to delete a specified node. Say, the node whose roll field is given as the key for the deletion. Here also three conditions arise:  
**Case 1: Delete the node at the beginning**

![Fig: Delete the head ](https://rawgit.com/sayef/tech/master/uploads/2015/08/10.png?w=300)

Fig: Delete the first node / head

**Case 2: Delete the node at the end**  


![Fig: Delete the last node](https://rawgit.com/sayef/tech/master/uploads/2015/08/11.png?w=300)

Fig: Delete the last node

**Case 3: Delete the node at the middle of two nodes**  



![12](https://rawgit.com/sayef/tech/master/uploads/2015/08/12.png?w=300)



Let’s see the code snippet which is as simple as the pictures say:

 ```c++
void delete (node *head, int key)	 	 
 {	 	 
    node *p, *q;	 	 
    p = *head; // iterate from the head	 	 
    if (p->roll == key) /* if the first item to be deleted */	 	 
    {	 	 
      *head = p->next;	 	 
      free (p); // free the memory allocated to the deleting node	 	 
    }	 	 
    else	 	 
    {	 	 
        while(p != NULL && p->roll != key)	 	 
        {	 	 
           q = p; //storing the address of the previous node	 	 
           p = p->next;	 	 
        }	 	 
        if(p == NULL) /* Element not found */	 	 
           printf("\nNomatch :: deletion failed");	 	 
        else if (p->roll == key) /* Delete a node at the middle of two nodes */	 	 
        {		 
           q->next = p->next; //Previous node now points the next node of the deleting item	 	 
           free (p); // free the memory allocated to the deleting node	 	 
        }	 	 
    }	 	 
 }
 ```

So, these are the basics of the linked list. If you understand these operation, hope you will be able to implement the followings-

1.  Concatenate two given list into one big list.
2.  Push, pop operation for Stack and Queue.
3.  Implement Circular and Doubly linked list.

Comment if anything is unclear to you or point me out if any mistake is sighted. Thanks.

Some implementations:

1.  ftp://gd.tuwien.ac.at/languages/c/programming-bbrown/c_094.htm
2.  http://www.thegeekstuff.com/2012/08/c-linked-list-example/

* * *