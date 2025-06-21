Answers to TODO:

1. LinkedList vs ArrayList:
   Using a LinkedList instead of an ArrayList does not affect the correctness of the iterator behavior in our tests. However, LinkedList has different performance characteristics — better for insertions/removals in the middle, worse for indexed access.

2. testNonempty() assertions:
   The expected values in the assertions were initially incorrect. They should match the values in the list added in that method:
   [33, 77, 44, 77, 55, 77, 66]

3. testRemove() - Why use iterator.remove() instead of list.remove():
   Using `iterator.remove()` safely removes the current element during iteration.
   Using `list.remove(Integer.valueOf(77))` inside the loop can cause a `ConcurrentModificationException`
   because it modifies the list structure directly while iterating through it.

4. testRemove() - Remaining list values:
   After removing all 77s using the iterator, the remaining list is: [33, 44, 55, 66]

5. testAverageValues() - Iterator usage:
   Used an iterator with a while loop to iterate through the list, compute the sum, and count the elements to get the average.
