---
title: 'Leetcode and Hackerrank Problems'
description: 'Breakdown of Leetcode and Hackerrank Problems'
pubDate: 'May 14 2025'
heroImage: '/blog-placeholder-2.jpg'
---

# Leetcode and Hackerrank Problems

### Two-Median Problem

Given an array of integers, find the two median values. The median is the middle value in a sorted list of numbers. If the list has an even number of elements, there are two middle values.

```python
def find_two_medians(arr):
    arr.sort()
    n = len(arr)
    if n % 2 == 1:
        return arr[n // 2], arr[n // 2]
    return arr[n // 2 - 1], arr[n // 2]
```
![blog placeholder](/two-median.jpg)

## My Solution
Above is probably the best and most efficient solution, however for a small dataset, my solution fit within the confines barely.  What I did was extend, as I never used it, I wanted to try a new method.  I used extend to add the other list to the first list, or merged the lists, then I sorted the list, and returned the two middle values.  I also used the @cache decorator to cache the results of the function calls, which can help improve performance for large datasets.

```python
self.extend_arr(self.nums1, self.nums2)
        # Now sort the merged array.
        merged = sorted(self.nums1)
        # Define the Partition point.
        # If the length of the merged array is even, 
        # return the average of the two middle elements.
        # if odd return the middle element, or at position
        # of mid or median.
```
## Last Step
I explained in my code comments, but you have to get the average if the list size is even, and if it is odd, there is only one value.
```python
        mid = len(merged) // 2
        if len(merged) % 2 == 0:
            return (merged[mid - 1] + merged[mid]) / 2.0
        else:
            return merged[mid]
```

## An Interesting Find
I am sure this is well known, but I found it interesting that when I passed in the two lists, vs defined new lists in the extend_arr method, it was slower.  Not by much, but it was never 0ms.  I am not sure how this would add up, if it is standard deviation, or if it is a constant.  I will have to look into that.