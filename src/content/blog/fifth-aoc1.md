---
title: 'Advent of Code and LeetCode Solutions'
description: 'Reflections and solutions for Advent of Code and LeetCode challenges, including debugging tips and code structure.'
pubDate: 'May 11 2025'
heroImage: '/blog-placeholder-5.jpg'
---

# Advent of Code and LeetCode Solutions

## Advent of Code and LeetCode Challenges

**Advent of Code Day 1 2024:**  
- The input is a list of numbers in a text file  
- Solution implemented in Python: `aoc_day1.py`

Both the built-in Python `sorted` method and a custom quicksort were used to solve the problem. The challenge itself was fairly straightforward, requiring just a bit of thought to reach the correct answer. Debugging tools and print statements proved invaluable for stepping through the code and observing variable values at each stage, making it much easier to identify and resolve issues.

---

## Advent of Code Day 2

For part two, a different approach was taken, with the debugger playing a key role. One challenge involved parsing the input: splitting and stripping the data into lists, then converting to integers. The presence of a trailing newline in the input resulted in an empty string that couldn’t be stripped, which could have been avoided by using `rstrip` to remove newlines before processing.

---

## Alternative Approaches

Using `rstrip` remains a viable alternative for input handling. During debugging, it became clear that the input was being split correctly—first into lines, then into integers. The initial solution relied on functions, but refactoring into a class made the logic easier to follow, even though it required some adjustments. At one point, calculations weren’t being saved as expected, and the logic didn’t behave as it had before the refactor. Stepping through the debugger revealed the issue, and simplifying the logic helped resolve it.

While more advanced functions could have been used, opting for a straightforward approach provided a better understanding of the underlying process, rather than relying on built-in shortcuts.

---

## Testing and Debugging

Redundant logic was implemented to solve the problem in two ways, serving as a self-check. Assigning results to variables made the code cleaner, though not always universally applicable. Print statements were used extensively for both understanding and debugging. The logic itself isn’t difficult, but it does require careful planning and a methodical approach—much like any advanced algorithm. Type issues can be tricky, but the debugger simplifies the process of tracking them down.

---

## Final Thoughts

A misreading of the problem initially led to checking for "2 or less" instead of "3 or less," which affected the solution. Whether the sequence is gradually increasing or decreasing, careful reading and testing are essential. Plans are in place to refactor the code for greater clarity and efficiency, with additional comments to aid understanding. Print statements used for debugging have been left in place, and both solution methods arrive at the same answer. Advent of Code Day 2 for 2024 is complete.

---

## Numpy

Numpy was used to convert the list into an array, and `numpy.diff` generated a list of differences. This made it easy to check whether the sequence was consistently increasing or decreasing. While Numpy streamlines the process, the core logic remains effective in both approaches.

---

## Link to GitHub Repository

[Mike's Advent of Code GitHub](https://github.com/MikePfunk28/advent_of_code)
