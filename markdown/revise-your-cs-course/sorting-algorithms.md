# Sorting Algorithms

There are many types of Sorting techniques, differentiated by their efficiency and space requirements. Following are some sorting techniques which we will be covering in next sections.

1. [Bubble Sort](http://sketchingdream.com/blog/bubble-sort/)
2. [Insertion Sort](http://sketchingdream.com/blog/insertion-sort/)
3. [Selection Sort](http://sketchingdream.com/blog/selection-sort/)
4. [Quick Sort](http://sketchingdream.com/blog/quick-sort/)
5. [Merge Sort](http://sketchingdream.com/blog/merge-sort/)
6. [Heap Sort](http://sketchingdream.com/blog/heap-sort/)

The following chart compares sorting algorithms on the various criteria outlined above; the algorithms with higher constant terms appear first, though this is clearly an implementation-dependent concept and should only be taken as a rough guide when picking between sorts of the same big-O efficiency.

| Sort                                                         | Average     | Best        | Worst       | Space    | Remarks                                                      |
| ------------------------------------------------------------ | ----------- | ----------- | ----------- | -------- | ------------------------------------------------------------ |
| [Bubble  sort](http://sketchingdream.com/blog/bubble-sort/)  | O(n^2)      | O(n^2)      | O(n^2)      | Constant | Always use a modified bubble sort                            |
| [Modified  Bubble sort](http://sketchingdream.com/blog/bubble-sort/) | O(n^2)      | O(n)        | O(n^2)      | Constant | Stops after reaching a sorted array                          |
| [Selection  Sort](http://sketchingdream.com/blog/selection-sort/) | O(n^2)      | O(n^2)      | O(n^2)      | Constant | Even a perfectly sorted input requires scanning the entire array |
| [Insertion  Sort](http://sketchingdream.com/blog/insertion-sort/) | O(n^2)      | O(n)        | O(n^2)      | Constant | In the best case (already sorted), every insert requires constant time |
| [Heap  Sort](http://sketchingdream.com/blog/heap-sort/)      | O(n*log(n)) | O(n*log(n)) | O(n*log(n)) | Constant | By using input array as storage for the heap, it is possible to achieve constant space |
| [Merge  Sort](http://sketchingdream.com/blog/merge-sort/)    | O(n*log(n)) | O(n*log(n)) | O(n*log(n)) | Depends  | On arrays, merge sort requires O(n) space; on linked lists, merge sort requires constant space |
| [Quicksort](http://sketchingdream.com/blog/quick-sort/)      | O(n*log(n)) | O(n*log(n)) | O(n^2)      | Constant | Randomly picking a pivot value (or shuffling the array prior to  sorting) can help avoid worst case scenarios such as a perfectly sorted  array. |

Here is a nice video for feeling the simulation of different types of sorting.  

------