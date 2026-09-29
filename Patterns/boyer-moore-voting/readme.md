# Boyer-Moore voting

## When to use

Use when you need an element that appears **more than ⌊n/2⌋** times (or, generalized, more than **n/k** times with k−1 candidates), and you want **one pass** with **O(1) extra space** instead of a frequency map. Clues: "majority element", "appears more than half", follow-up asking for linear time and O(1) space. The problem often **guarantees** a majority exists; if not, add a second pass to verify the candidate's count.

## Problems

- <a href="https://leetcode.com/problems/majority-element/" target="_blank" rel="noopener noreferrer">Majority Element</a> (LC 169) — [day-1.md](../../Day/day-1.md)
  - Input => array of size n
  - Output => return the majority element (integer)
