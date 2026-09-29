# Kadane (subarray DP)

## When to use

Use for **maximum (or minimum) sum of a contiguous subarray** in one pass. At each index, decide: extend the previous subarray or start fresh at the current element (`cur = max(nums[i], cur + nums[i])`, track global best). Clues: "subarray with largest sum", "contiguous", Kadane / DP on "best ending here". Works in O(n) time, O(1) space.

## Problems

- <a href="https://leetcode.com/problems/maximum-subarray/" target="_blank" rel="noopener noreferrer">Maximum Subarray</a> (LC 53) — [day-1.md](../../Day/day-1.md)
  - Input => integer array `nums`
  - Output => largest sum of any contiguous subarray (at least one element)
