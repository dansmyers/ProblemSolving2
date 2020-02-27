QuickSort
=========

Basic Strategy
--------------

```
quicksort(a, left, right) {

    if (right - left <= 0) {  // Base case
        return
    }

    Choose an element to be the pivot

    Partition the list so that elements less than or equal to the
    pivot are to its left and larger elements are to its right
    
    The pivot is now in its final position
    
    quicksort(a, left, pivot - 1)
    quicksort(a, pivot + 1, right)
}
```

Partition
---------
Most of the work in quicksort is done by the partition step. There
are a few different versions of the partition process.

Here's the original strategy, which was the one described in the
Sorting Out Sorting video.

Sort the following array:

    2 7 5 3 1 9 4
    
Choose the last element to be the pivot:

    2 7 5 3 1 9 4
                ^
                |
                |
              pivot
              
Use two indices, l and r to exchange items. Initally, l = 0 and
r = a.length - 2 (the next-to-last element)

2 7 5 3 1 9 4
^         ^ ^
|         | |
|         | |
l         r |
           pivot

Scan from the left until l points to an item greater than the pivot.
Then scan from the right until r points to an item less than the
pivot.

2 7 5 3 1 9 4
  ^     ^   ^
  |     |   |
  |     |   |
  l     r   |
           pivot
 
Swap the two items:

2 1 5 3 7 9 4
  ^     ^   ^
  |     |   |
  |     |   |
  l     r   |
           pivot
        
Repeat until l == r, then swap the pivot into its correct position.

Partition pseudocode:

    l = 0
    r = a.length - 2

    while (l != r) {

        while (l != r and a[l] <= pivot)
            l++
           
        while (l != r and a[r] > pivot)
            r--
            
        swap a[l] and a[r]
        
    }

    swap a[l] and the pivot

The pivot is now in its correct position and we can recursively sort
the left and right halves.


Practice
--------
Sort the following list

    5 4 9 3 7 2 6 1
    
    First time: do the partition step casually, just reorder the list
    without worrying about pointers. Work all the way through the
    sort process.
    
    Second time: repeat the first pass of the algorithm using
    pointers.
    
Now try sorting this list:

    1 2 3 4 5
    
    What happens to QuickSort when it processes a sorted list?


Merge Sort
==========

Basic Strategy
--------------

```
mergesort(a) {

    if (a.length == 1) {  // Base case
        return
    }

    left = a new array containing the left half of a
    right = a new array containing the right half of a
    
    sortedLeft = mergesort(left)
    sortedRight = mergesort(right)
    
    output = merge(sortedLeft, sortedRight)
}
```

Example
-------
Sort this list

    2 6 8 1 3 5 7 9  
    
Split the list into left and right halves

    2 6 8 1                 3 5 7 9
    
The left half is merge sorted first

    Split the left half into its own left and right halves
    
        2 6                8 1
    
    Call merge sort on each two-element list; at the end of that
    process, both sides will be sorted
    
        2 6                1 8
        
    Merge the two sorted lists back together to get one sorted four
    element list
    
        1 2 6 8
        
The left half is now sorted, next sort the right half:

    Split the right half into its own left and right parts
    
        3 5                7 9
        
    Call merge sort on those two-element lists; at the end of that
    process, both of those elements will be sorted
    
        3 5                7 9
        
    Merge the two lists together to get the sorted right half
    
        3 5 7 9
        
The two halves are now sorted. Merge them together to get the final
sorted list

    1 2 6 8        3 5 7 9
    
    1 2 3 5 6 7 9
    
How to Do the Merge
-------------------

    1 2 6 8        3 5 7 9
    ^              ^
    |              |
  left           right
  
Choose the smallest element of (left, right) and make it the first
output

    output: 1

    1 2 6 8        3 5 7 9
      ^            ^
      |            |
    left         right
    
Repeat, choosing the smallest element of (left, right)

    output: 1 2

    1 2 6 8        3 5 7 9
        ^          ^
        |          |
      left       right
  
Now the right element is the smallest of (left, right)

    output: 1 2 3

    1 2 6 8        3 5 7 9
        ^            ^
        |            |
      left         right
      
Et cetera...


merge(sortedLeft, sortedRight) {

    left = 0
    right = 0
    
    while (left < sortedLeft.length and right < sortedRight.length) {
    
        if (sortedLeft[left] < sortedRight[right]) {
            append sortedLeft[left] to output
            left++
        } else {
            append sortedRight[right] to output
            right++
        }

    }
    
    // The previous loop ends when all of the items in one list
    // have been merged into the output
    //
    // Append any remaining elements from the other list
    
    while (left < sortedLeft.length) {
        append sortedLeft[left] to output
        left++
    }
    
    while (right < sortedRight.length) {
        append sortedRight[right] to output
        right++
    }

}
