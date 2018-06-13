# Basic Programming Interview Questions

This is a simple collection of  problems for interview from the basic knowledge of C programming.

**Part 1: Write Short Procedure or Pseudo-code**  

1. Write a program to print numbers from 1 to 100 without using loops.
2. Write a C program to swap two variables without using a temporary variable.
3. What is the 8 queens problem? Write a C program to solve it?
4. Write a C program to print a square matrix helicaly.
5. Write a C program to reverse a string.
6. Write a C program generate permutations.
7. Write a C program for calculating the factorial of a number.
8. Write a C program to calculate pow(x,n)?
9. How do you calculate the maximum sum of a list of numbers?
10. How to generate fibonacci numbers with recurison? Can you optimize it?
11. Solve the Rat In A Maze problem using backtracking.
12. Write C code to solve the Tower of Hanoi problem (generalize form).
13. Write a C program which produces its own source code as its output.
14. Write a C program to convert from decimal to any base (binary, hex, oct etc…).
15. Write C code to check if an integer is a power of 2 or not in a single line?
16. Write a C program to find the GCD of two numbers.
17. Write code to remove duplicates in a sorted array.
18. Find the maximum of three integers using the ternary operator.
19. Write C code to dynamically allocate one, two and three dimensional arrays (using malloc()).
20. How would you find the size of structure without using sizeof()?
21. Write a C program to multiply two matrices.
22. Write a C program to check for palindromes.
23. Write a C program to convert a decimal number into a binary number.
24. Write C code to implement the Binary Search algorithm.
25. How do you compare floating point numbers?
26. Write a program to check if a given year is a leap year or not?
27. Is there something we can do in C but not in C++?
28. Can you write general sieve method for finding prime numbers?
29. What is the difference between scanf(“%s”, str) and gets(str)?
30. Write your own sqrt() function in C.
31. How can we sum the digits of a given number in single statement?

------

**Part 2: Find The Output** 

1\. Find the output –

int counter = 0, i;
for(i=0;;i++) {
  if (i<100) continue;
      counter ++;
  if (counter == 100) break;
}
printf(%d%d”,i, counter);

2\. what is the value of EOF..?? ans=-1

3\. What is the output?

class test{ };
int main()
{
  cout<<sizeof(test);
  return 0;
}

ans: 1

4\. What is the output?

class test
{
  static int x;
  int* ptr;
}
int main()
{
  test t1;
  cout<<sizeof(t1)<< " " << sizeof(test);
  return 0;
}

ans: 4 4

5\. What is the output?

char* fun()
{
  return("samsung india");
}
main()
{
  printf("%s",printf("electronics")+fun());
}

ans: electronicsia

printf(“electronics”) first print “electronics” and return a int value which the length of the string, that means 11, adding this 11 to the address of the “samsung india” will eventually point 11th character results in printing “ia”.

6\. What is the output?

main()
{
  char* ptr={"samsung","electronics","india"};
  char**ptr1;
  ptr1=ptr;
  *ptr1++;
}

ans:

7\. What is the output?

main()
{
  extern int i;
  {
    int i=20;
    printf("%d",i);
  }
}

ans: linker error

8\. How to access the next element of arr?

struct book arr\[10\];

ans: since arr is an array of 10 variables of book type, so to access the next element add the sizeof(struct) in the base address of the arr.

9\. What is the output

main()
{
  int i=10;
  switch(i)
  {
   printf("something here");
   case 10:
     printf("case10");
     break;
   case 5*2:
     printf("another case 10";);
     break;
   default:
     printf("its default");
  }
}

ans: case constant already used..10 and 5*2 are same..error

**Part 3: OS Related** 

------

1. Threads don’t share their ___________________with other threads. Ans: stack,register,and counter
2. Advantage of using large pages and small pages in paging ___________________.
3. Which program loads first when system starts? Ans: bootstrap loader.
4. What does CPU do when interrupt occurs? Ans: CPU at once switches over it control to the interrupt.
5. Technique used for avoiding page fault frequency? ans:locality of reference.

------

**Part 4: Data Structure**

1. Recursive function uses more__________________than non recursive function. Ans: stack space.
2. In heap each node is _______. Ans: each node is greater than its left and right child node.
3. Complexity of binary search. Ans: nlognr
4. Total no. of nodes in a full binary tree of 4 levels. Ans:15

------