orting algorithms are often classified by:

* [[Computational complexity theory|Computational complexity]] ([[Best, worst and average case|worst, average and best]] behavior) in terms of the size of the list (''n''). For typical serial sorting algorithms good behavior is O(''n''&nbsp;log&nbsp;''n''), with parallel sort in O(log<sup>2</sup>&nbsp;''n''), and bad behavior is O(''n''<sup>2</sup>). (See [[Big O notation]].) Ideal behavior for a serial sort is O(''n''), but this is not possible in the average case. Optimal parallel sorting is O(log&nbsp;''n''). [[Comparison sort|Comparison-based sorting algorithms]] need at least Ω(''n''&nbsp;log&nbsp;''n'') comparisons for most inputs.
* [[Computational complexity theory|Computational complexity]] of swaps (for "in-place" algorithms).
* [[Memory (computing)|Memory]] usage (and use of other computer resources). In particular, some sorting algorithms are "[[In-place algorithm|in-place]]". Strictly, an in-place sort needs only O(1) memory beyond the items being sorted; sometimes O(log(''n'')) additional memory is considered "in-place".
* Recursion.  Some algorithms are either recursive or non-recursive, while others may be both (e.g., merge sort).
* Stability: [[#Stability|stable sorting algorithms]] maintain the relative order of records with equal keys (i.e., values).
* Whether or not they are a [[comparison sort]]. A comparison sort examines the data only by comparing two elements with a comparison operator.
* General method: insertion, exchange, selection, merging, ''etc.'' Exchange sorts include bubble sort and quicksort. Selection sorts include shaker sort and heapsort.
* Whether the algorithm is serial or parallel. The remainder of this discussion almost exclusively concentrates upon serial algorithms and assumes serial operation.
* Adaptability: Whether or not the presortedness of the input affects the running time.  Algorithms that take this into account are known to be [[Adaptive sort|adaptive]].

===Stability===
[[File:Sorting stability playing cards.svg|thumb|An example of stable sort on playing cards. When the cards are sorted by rank with a stable sort, the two 5s must remain in the same order in the sorted output that they were originally in. When they are sorted with a non-stable sort, the 5s may end up in the opposite order in the sorted output.]]
Stable sort algorithms sort repeated elements in the same order that they appear in the input. When sorting some kinds of data, only part of the data is examined when determining the sort order. For example, in the card sorting example to the right, the cards are being sorted by their rank, and their suit is being ignored. This allows the possibility of multiple different correctly sorted versions of the original list. Stable sorting algorithms choose one of these, according to the following rule: if two items compare as equal, like the two 5 cards, then their relative order will be preserved, so that if one came before the other in the input, it will also come before the other in the output.

Stability is important for the following reason: say, if the data is sorted first by student name, in some cases, dynamically on the webpage, and now the data is again sorted by which class section they are in. Imagine for students that appear in the same section, the order of their names is shuffled up and not in any particular order, and this can be annoying. If a sorting algorithm is stable, the student names will still be in good order. A user might want to have the previous chosen sort orders preserved on the screen and a stable sort algorithm can do that. Another reason why stability is important: if the users are not programmers, then they can choose to sort by section and then by name, by first sorting using name and then sort again using section. If the sort algorithm is not stable, the users won't be able to do that.

More formally, the data being sorted can be represented as a record or tuple of values, and the part of the data that is used for sorting is called the ''key''. In the card example, cards are represented as a record (rank, suit), and the key is the rank. A sorting algorithm is stable if whenever there are two records R and S with the same key, and R appears before S in the original list, then R will always appear before S in the sorted list.

When equal elements are indistinguishable, such as with integers, or more generally, any data where the entire element is the key, stability is not an issue. Stability is also not an issue if all keys are different.

Unstable sorting algorithms can be specially implemented to be stable. One way of doing this is to artificially extend the key comparison, so that comparisons between two objects with otherwise equal keys are decided using the order of the entries in the original input list as a tie-breaker. Remembering this order, however, may require additional time and space.

One application for stable sorting algorithms is sorting a list using a primary and secondary key. For example, suppose we wish to sort a hand of cards such that the suits are in the order clubs (♣), diamonds (<span style="color:#ff0000">♦</span>), hearts (<span style="color:#ff0000">♥</span>), spades (♠), and within each suit, the cards are sorted by rank. This can be done by first sorting the cards by rank (using any sort), and then doing a stable sort by suit:

[[File:Sorting playing cards using stable sort.svg|400px]]

Within each suit, the stable sort preserves the ordering by rank that was already done. This idea can be extended to any number of keys and is utilised by [[radix sort]]. The same effect can be achieved with an unstable sort by using a lexicographic key comparison, which, e.g., compares first by suit, and then compares by rank if the suits are the same.