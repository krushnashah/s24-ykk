---
num: "Lecture 14"
desc: "MergeSort and Binary Search Analysis"
ready: true
lecture_date: 2024-05-16 15:30:00 -0700
---

* [Slides folder]({{ site.slides_url }}){:target="_blank"}
* [Lecture recording](https://www.loom.com/share/42a487a77e02493a9671ee372cc91acd?sid=2c5b0abd-bddd-4258-8bc0-6d11c79a925f){:target="_blank"}

# Plan for today
- Announcement about class on Tuesday
- Overview important points about mergesort
- Mergesort activity
- Mergesort walkthrough
- Quicksort overview

# Class Announcement
- No class on Tuesday (5/21)
- Watch posted recordings on website about quicksort
- Review week 6 linear data structures videos

# Divide and Conquer Algorithms
- Subdivide a larger problem into smaller problems
- Solve each small part
- Combine smaller subproblem solutions to a larger problem
- Similar to recursion

# Mergesort highlights 
- Break the list into two equal parts in each recursive iteration
- Note the height is log n
- For each level, the merge step needs to compare n elements (O(n))
- If there are log n levels and we need to do n comparisions to merge the elements for each level, then we have:
  - n * log n results in O(n log n) running time
- Disadvantage of mergesort: O(n) additional space when creating left and right lists

# Mergesort Activity
- list1 and list2 are two lists that are in sorted order (ascending)
- Store the sorted list that has elements from list1 and list2 in the provided list final
- What asserts do we need to test the accuracy of the function?
  - Empty list1 and/or list 2
  - One element in each list

```
def sort_sorted_lists(listleft, listright, final):
  # TODO: add solution
```

The point of this exercise is to create your own solution, so that when you look at the code example in the textbook, it makes more sense how to goes about doing the merging. 
In this exercise, we are storing the resulting list in the empty list passed through the `final` parameter, however, in the merge sort, we are operating directly on the larger list, 
which is why we need the `k` index -- it keeps the position in the list that's passed directly into the function; we are effectively overwriting its contents, because the values are stored in the 
left and right _copies_ of the list.

# Visualize Mergesort 
- Splitting - O(log n)
- Merging - O(n)

[The visualization of the algorithm](lectures/lect14-merge-sort-viz-alg.jpg){:target="_blank"}

[The visualization of O(n log n) derivation](lectures/lect14-merge-sort-big-o.jpg){:target="_blank"}

# Iclicker check-in

Question 1: Given a list `[5, 4, 3, 2, 1]`, according to the book, what is the 2nd call added to the stack for the `merge_sort()`?

```
A. merge_sort([5, 4, 3, 2, 1])
B. merge_sort([5, 4, 3])
C. merge_sort([5, 4])
D. merge_sort([3, 2, 1])
E. merge_sort([2, 1])
```

Question 2: Given a list `[5, 4, 3, 2, 1]`, according to the book, what is the 3rd call added to the stack for the `merge_sort()`?

```
A. merge_sort([5, 4, 3])
B. merge_sort([5, 4])
*C. merge_sort([5])*
D. merge_sort([4])
E. merge_sort([2, 1])
```

# Binary Search
- Binary search is a useful algorithm to search for an item if the list you're looking in is sorted
- Since the collection is in sorted order, we can check the middle to see if the item we're looking for is there
  - If the middle element is the one we're looking for, then great!
  - If the item we're looking for is < the middle element, then we don't have to search the right side of the list
  - If the item we're looking for is > the middle element, then we don't have to search the left side of the list


