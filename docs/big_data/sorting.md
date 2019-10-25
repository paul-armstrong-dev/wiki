The techniques of sorting can be divided into two categories. These are:

- Internal Sorting:
    - If all the data that is to be sorted can be adjusted at a time in the main memory, the internal sorting method is being performed.
- External Sorting:
    - When the data that is to be sorted cannot be accommodated in the memory at the same time and some has to be kept in auxiliary memory such as hard disk, floppy disk, magnetic tapes etc, then external sorting methods are performed.
    
    
- In data processing, there are various sorting methods and techniques that are not only used for sorting algorithms but are also used for analyzing the performance of other algorithms. In this post, you will find a brief description of the different types of sorting algorithms.
- Sorting algorithms can be categorized as
1. **Simple Sorts**:
    - These types of algorithms are efficient on the small amount of data but cannot handle large data. They are fast and efficient due to low overhead. Two simplest sort algorithms are insertion sort and selection sorts
2. **Effecient Sorts**: 
    - Practical sorting algorithms are usually based on algorithms with average time complexity. Some most common of these are merge sort, heap sort, and quicksort.
    - These algorithms can be used on large lists and complicated programs but each of them has its own drawbacks and advantages. Some may require additional space or more iterations, thus resulting in more complex algorithms.
    - Examples: 
        - MergeSort: 
        - Compares two elements of the list and then swaps them in the order required (ascending or descending).
        - It applies the divide and rule concept. 
        - Merge sort works on sequential access and can work on large lists.
            - This algorithm is popularly used in practical programming as it is used in the sophisticated algorithm Timsort.
            - Timsort is used for standard sorting in languages such as Python and Jana. Merge sort algorithm is itself a standard routine in Perl.
        - Algorithm:
            1. Divide the list recursively into two or more sub-problems until it can no more be divided
            2. Solve the sub-problems until it is reached to the base case
            3. Merge the smaller lists into the new list in sorted order
        - HeapSort: 
            - An advanced and efficient version of the selection sort algorithm. 
            - It works similarly by sorting the elements in the ascending or descending order by comparing but this is done by using a data structure called heap, which is a special tree base structure. 
            - Heap has the following properties:
                - It is a complete tree
                - Root has a greater value than any other element in the subtree
            - Algorithm:
                1. Form a heap from the given data
                2. Remove the largest item from the heap
                3. From the remaining data reform the heap
                4. Repeat step 2 and 3 until all the data is over
        - QuickSort: 
            - Similar to merge sort which uses divide and conquers technique. 
            - Recursive algorithm. 
            - But quicksort performs in a little different manner than mergesort does. 
            - In merge sort, the work does not happen in the division stage but it happens in the combined stage. 
            - But in quicksort it is totally opposite, everything happens in the division stage.
            - Algorithm:
                1. Divide the list by any chosen element and call it a Pivot element. Rearrange the elements, all the elements that are less than equal to the pivot element must be in left and larger ones on the right. This procedure is called Partitioning.
                2. Conquer which mean recursively ordering the subarrays
                3. There is nothing left in the combined stage as the conquer stage organizes everything. The smaller or equal elements to the pivot are organized at the left side and larger elements are organized at the right.


      
          

