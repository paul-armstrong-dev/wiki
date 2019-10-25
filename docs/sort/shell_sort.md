## Python Program to Implement Shell Sort

1. Create a generator gaps that takes the size of the list as argument and returns the next element in the sequence of gaps on each successive call. Here the gap sequence chosen is given by 2^k – 1.
2. Create a function shell_sort that takes a list as argument.
3. For each gap returned by gaps, call insertion_sort_with_gap with gap as argument.
4. Create a function insertion_sort_with_gap that takes a variable gap as argument.
5. The function insertion_sort_with_gap performs insertion sort on all elements at a distance of gap from each other. Thus it performs insertion sort on the indexes k, k + gap, k + 2*gap, k + 3*gap, … of the list for all values of k.

```python
def gaps(size):
    # uses the gap sequence 2^k - 1: 1, 3, 7, 15, 31, ...
    length = size.bit_length()
    for k in range(length - 1, 0, -1):
        yield 2**k - 1
 
 
def shell_sort(alist):
    def insertion_sort_with_gap(gap):
        for i in range(gap, len(alist)):
            temp = alist[i]
            j = i - gap
            while (j >= 0 and temp < alist[j]):
                alist[j + gap] = alist[j]
                j = j - gap
            alist[j + gap] = temp
 
    for g in gaps(len(alist)):
        insertion_sort_with_gap(g)
 
 
alist = input('Enter the list of numbers: ').split()
alist = [int(x) for x in alist]
shell_sort(alist)
print('Sorted list: ', end='')
print(alist)
```

**Runtime Test Cases**

- Case 1:
    - Enter the list of numbers: 5 2 3 1 10
    - Sorted list: 1, 2, 3, 5, 10
- Case 2:
    - Enter the list of numbers: 7 6 5 4
    - Sorted list: 4, 5, 6, 7
- Case 3:
    - Enter the list of numbers: 2
    - Sorted list: 2