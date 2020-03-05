Midterm Exam Review: CMS 170 Fall 2020
========================================

2-D Arrays
----------
Write methods to perform operations on 2-D arrays. Here are some examples:

- print
- sum all of the elements
- calculate the average element
- find the maximum or minimum value
- find the maximum or minimum element in each row or column
- compute the sum of each row or the sum of each column


Objects and Object-Oriented Programming
---------------------------------------
Define the term "encapsulation" as it applies to OOP.

What is the Epoch? List two Java functions that can be used to
measure time in programs.

What are the four access modifiers available in Java classes?

Review our example classes and be prepared to write a class with
private instance variables and a specified set of methods.

- For example, write a `Book` class with `private` `author` and `title`
    fields, `get` methods for each field, and a `toString` method.
    
- Think of other real-world objects that you might use as class
    templates.
    

ArrayLists
----------
Be familiar with the common `ArrayList` methods: `get`, `set`, `remove`, `add`,
`toString`.

Consider an `ArrayList` class built using a fixed-size 1-D array as
its backing storage for the elements in the list. Know how to

- Construct a new ArrayList
- Append to the list
- Get the item at a given index
- Remove and return the item at a given index
- Set the item at a given index to a given value
    
Be prepared to write pseudocode implementations of these methods.
    
What are the worst-case complexities (in Big-O notation) of each of the `ArrayList` methods?

Make an argument, in your own words, for why appending to an `ArrayList` requires
O(1) time on average.


Searching
---------
Be familiar with linear and binary search. Be able to write them as
both pseudocode and Java methods using arrays as inputs.

What are the complexities of linear and binary search?

Big-O
-----
What is the formal definition of Big-O notation?

Be able to express the order of growth of mathematical functions in
Big-O notation. For example,

```
f(n) = 10 n^2 + 100 n + 3 is O(n^2)
```

Be able to use the formal definition of Big-O notation and the "Get Huge" approach to 
prove the complexity of a mathematical function. For example, find a value of a constant `c` to show that

```
3n^2 + 10n + 5 is O(n^2)
```

What is the complexity of adding two N-digit numbers by hand, using
traditional digit-by-digit arithmetic? How about multiplying them?

Suppose I upgrade to a new supercomputer that is 1000 times as fast
as my current machine. I would like to run an algorithm that has a
complexity of O(N<sup>3</sup>). On my old computer, I could run this code on
an input of size 100 in 1 second. What size input should I be able
to compute in 1 second on my new, faster computer?

What is the complexity of the following code fragment?

```
Random rand = new Random();  // Initializing Random is O(1)
for (int i = 0; i < a.length; i++) {
    int randValue = rand.nextInt(1000);  // O(1)
    for (int r = 0; r < randValue; r++) {
        a[i]++;
    }
}
```


Sorting
-------
Know the three quadratic sorting algorithms: selection, bubble,
and insertion. Be able to apply them to example lists. I WILL NOT ask
you to write their code.

Make an argument that selection sort is O(N<sup>2</sup>).

Know that practical sorting algorithms are O(N log N) and that this
is a lower-bound for comparison-based sorting: there is no comparison
algorithm that has BETTER worst-case performance that O(N log N).

Be able to apply the quicksort partition operation to an example array.

What is the worst case for quick sort if the pivot is chosen to be
the last element? What is its complexity in this worst case?

Make an argument that the average case performance of quicksort on a randomized
array is O(n lg n).


Recursion
---------
Be able to identify the base case and recursive case and write
recursive methods. Examples:

- Factorial
- Fibonacci sequence
- Mutant bunny ears
- Palindromes
- String reversal
    
    
Recurrence Relations
--------------------
Show that f(n) = log n satisfies the relation

    T(n) = T(n / 2) + 1
    
Show the f(n) = 2<sup>n</sup> - 1 satisfies the relation

    T(n) = 2 * T(n - 1) + 1
    
Shpw that f(n) = n lg n satisfies the relation

    T(n) = 2 * T(n / 2) + n
