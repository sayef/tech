# Sorting Algorithms

There are many types of Sorting techniques, differentiated by their efficiency and space requirements. Following are some sorting techniques which we will be covering in next sections.

1. [Bubble Sort](https://cdn.rawgit.com/sayef/tech/master/blog/revise-your-cs-course/bubble-sort.html)
2. [Insertion Sort](https://cdn.rawgit.com/sayef/tech/master/blog/revise-your-cs-course/insertion-sort.html)
3. [Selection Sort](https://cdn.rawgit.com/sayef/tech/master/blog/revise-your-cs-course/selection-sort.html)
4. [Quick Sort](https://cdn.rawgit.com/sayef/tech/master/blog/revise-your-cs-course/quick-sort.html)
5. [Merge Sort](https://cdn.rawgit.com/sayef/tech/master/blog/revise-your-cs-course/merge-sort.html)
6. [Heap Sort](https://cdn.rawgit.com/sayef/tech/master/blog/revise-your-cs-course/heap-sort.html)

The following chart compares sorting algorithms on the various criteria outlined above; the algorithms with higher constant terms appear first, though this is clearly an implementation-dependent concept and should only be taken as a rough guide when picking between sorts of the same big-O efficiency.

| Sort                  | Average     | Best        | Worst       | Space    | Remarks                                                      |
| --------------------- | ----------- | ----------- | ----------- | -------- | ------------------------------------------------------------ |
| Bubble Sort           | O(n^2)      | O(n^2)      | O(n^2)      | Constant | Always use a modified bubble sort                            |
| Modified  Bubble sort | O(n^2)      | O(n)        | O(n^2)      | Constant | Stops after reaching a sorted array                          |
| Selection  Sort       | O(n^2)      | O(n^2)      | O(n^2)      | Constant | Even a perfectly sorted input requires scanning the entire array |
| Insertion  Sort       | O(n^2)      | O(n)        | O(n^2)      | Constant | In the best case (already sorted), every insert requires constant time |
| Heap  Sort            | O(n*log(n)) | O(n*log(n)) | O(n*log(n)) | Constant | By using input array as storage for the heap, it is possible to achieve constant space |
| Merge  Sort           | O(n*log(n)) | O(n*log(n)) | O(n*log(n)) | Depends  | On arrays, merge sort requires O(n) space; on linked lists, merge sort requires constant space |
| Quicksort             | O(n*log(n)) | O(n*log(n)) | O(n^2)      | Constant | Randomly picking a pivot value (or shuffling the array prior to  sorting) can help avoid worst case scenarios such as a perfectly sorted  array. |

Here is a nice video for feeling the simulation of different types of sorting.  

------