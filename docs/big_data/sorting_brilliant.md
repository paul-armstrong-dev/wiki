https://brilliant.org/wiki/sorting-algorithms/

A sorting algorithm is an algorithm made up of a series of instructions that takes an array as input, performs specified operations on the array, sometimes called a list, and outputs a sorted array. Sorting algorithms are often taught early in computer science classes as they provide a straightforward way to introduce other key computer science topics like Big-O notation, divide-and-conquer methods, and data structures such as binary trees, and heaps. There are many factors to consider when choosing a sorting algorithm to use.

Sorting Algorithms
In other words, a sorted array is an array that is in a particular order. For example, [a,b,c,d][a,b,c,d] is sorted alphabetically, [1,2,3,4,5][1,2,3,4,5] is a list of integers sorted in increasing order, and [5,4,3,2,1][5,4,3,2,1] is a list of integers sorted in decreasing order.

A sorting algorithm takes an array as input and outputs a permutation of that array that is sorted.

There are two broad types of sorting algorithms: integer sorts and comparison sorts.

Comparison Sorts

Comparison sorts compare elements at each step of the algorithm to determine if one element should be to the left or right of another element.

Comparison sorts are usually more straightforward to implement than integer sorts, but comparison sorts are limited by a lower bound of O(n \log n)O(nlogn), meaning that, on average, comparison sorts cannot be faster than O(n \log n)O(nlogn). A lower bound for an algorithm is the worst-case running time of the best possible algorithm for a given problem. The "on average" part here is important: there are many algorithms that run in very fast time if the inputted list is already sorted, or has some very particular (and overall unlikely) property. There is only one permutation of a list that is sorted, but n!n! possible lists, so the chances that the input is already sorted is very unlikely, and on average, the list will not be very sorted.

The running time of comparison-based sorting algorithms is bounded by \Omega(n \log n)Ω(nlogn).

A comparison sort can be modeled as a large binary tree called a decision tree where each node represents a single comparison. Because the sorted list is some permutation of the input list, for an input list of length nn, there are n!n! possible permutations of that list. This is a decision tree because each of the n!n! is represented by a leaf, and the path the algorithm must take to get to each leaf is the series of comparisons and outcomes that yield that particular ordering.

At each level of the tree, a comparison is made. Comparisons happen, and we keep traveling down the tree; until the algorithm reaches the leaves of the tree, there will be a leaf for each permutation, so there are n!n! leaves.

Each comparison halves the number of future comparisons the algorithm must do (since if the algorithm selects the right edge out of a node at a given step, it will not search the nodes and paths connected to the left edge). Therefore, the algorithm performs O(\log n!)O(logn!) comparisons. Any binary tree, with height hh, has a number of leaves that is less than or equal to 2^h2 
h
 .

From this,
2^h \geq n!.
2 
h
 ≥n!.
Taking the logarithm results in
h \geq \log(n!).
h≥log(n!).
From Stirling's approximation,
n! > \left(\frac{n}{e}\right)^n.
n!>( 
e
n
​     |          
 ) 
n
 .
Therefore,
\begin{aligned} h &\geq \log\left(\frac{n}{e}\right)^n \\ &= n\log \left(\frac{n}{e}\right) \\ &= n\log n- n \log e\\ &= \Omega(n\log n). \end{aligned}
h
​     |          
  
≥log( 
e
n
​     |          
 ) 
n
 
=nlog( 
e
n
​     |          
 )
=nlogn−nloge
=Ω(nlogn).
​     |          
 
Integer Sorts

Integer sorts are sometimes called counting sorts (though there is a specific integer sort algorithm called counting sort). Integer sorts do not make comparisons, so they are not bounded by \Omega(n\log n)Ω(nlogn). Integer sorts determine for each element​ xx how many elements are less than xx. If there are 1414 elements that are less than xx, then xx will be placed in the 15^\text{th}15 
th
  slot. This information is used to place each element into the correct slot immediately—no need to rearrange lists.

Properties of Sorting Algorithms
All sorting algorithms share the goal of outputting a sorted list, but the way that each algorithm goes about this task can vary. When working with any kind of algorithm, it is important to know how fast it runs and in how much space it operates—in other words, its time complexity and space complexity. As shown in the section above, comparison-based sorting algorithms have a time complexity of \Omega(n\log n)Ω(nlogn), meaning the algorithm can't be faster than n \log nnlogn. However, usually, the running time of algorithms is discussed​ in terms of big O, and not Omega. For example, if an algorithm had a worst-case running time of O(n\log n)O(nlogn), then it is guaranteed that the algorithm will never be slower than O(n\log n)O(nlogn), and if an algorithm has an average-case running time of O(n^2)O(n 
2
 ), then on average, it will not be slower than O(n^2)O(n 
2
 ).

The running time describes how many operations an algorithm must carry out before it completes. The space complexity describes how much space must be allocated to run a particular algorithm. For example, if an algorithm takes in a list of size nn, and for some reason makes a new list of size nn for each element in nn, the algorithm needs n^2n 
2
  space.

O(1)
O(1)
O(n)
O(n)
O\big(n^2\big)
O(n 
2
 )
O(n\log n)
O(nlogn)
Find the big-O running time of a sorting program that does the following:

It takes in a list of integers.
It iterates once through the list to find the largest element, and moves that element to the end.
It repeatedly finds the largest element in the unsorted portion by iterating once through, and moves that element to the end of the unsorted portion.
At the end, the list is sorted low to high.

(Also, try implementing this program in your language of choice.)

Additionally, for sorting algorithms, it is sometimes useful to know if a sorting algorithm is stable.

Stability

A sorting algorithm is stable if it preserves the original order of elements with equal key values (where the key is the value the algorithm sorts by). For example,

[1]
When the cards are sorted by value with a stable sort, the two 5s must remain in the same order in the sorted output that they were originally in. When they are sorted with a non-stable sort, the 5s may end up in the opposite order in the sorted output.


Choosing a Sorting Algorithm
To choose a sorting algorithm for a particular problem, consider the running time, space complexity, and the expected format of the input list.

| Algorithm     |          Best-case     |          Worst-case     |          Average-case     |          Space Complexity     |          Stable?     |
|---------------|------------------------|-------------------------|---------------------------|-------------------------------|----------------------|
| Merge Sort     |          O(n \log n)O(nlogn)     |          O(n \log n)O(nlogn)     |          O(n \log n)O(nlogn)     |          O(n)O(n)     |          Yes     |        
| Insertion Sort     |          O(n)O(n)     |          O(n^2)O(n2)     |          O(n^2)O(n2)     |          O(1)O(1)     |          Yes     |        
| Bubble Sort     |          O(n)O(n)     |          O(n^2)O(n2)     |          O(n^2)O(n2     |          O(1)O(1)     |          Yes     |        
| Quicksort     |          O(n \log n)O(nlogn)     |          O(n^2)O(n2)     |          O(n \log n)O(nlogn)     |          \log nlogn best, nn avg     |          Usually not*     |        
| Heapsort     |          O(n<sub>log</sub> n)O(nlogn)     |          O(n \log n)O(nlogn)     |          O(n \log n)O(nlogn)     |          O(1)O(1)     |          No     |        
| Counting Sort     |          O(k+n)O(k+n)     |          O(k+n)O(k+n)     |          O(k+n)O(k+n)     |          O(k+n)O(k+n)     |          Yes     |        

--- 
- *Most quicksort implementations are not stable, though stable implementations do exist.            
When choosing a sorting algorithm to use, weigh these factors. For example, quicksort is a very fast algorithm but can be pretty tricky to implement; bubble sort is a slow algorithm but is very easy to implement. To sort small sets of data, bubble sort may be a better option since it can be implemented quickly, but for larger datasets, the speedup from quicksort might be worth the trouble implementing the algorithm


<sub>subscript</sub> and <sup>superscript</sup>