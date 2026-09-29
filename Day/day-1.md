Today I solved 2 problems and these are the ones which I solved



- <a href="https://leetcode.com/problems/majority-element/" target="_blank" rel="noopener noreferrer">Majority Element</a> (LC 169)

    - Input => array of size n

    - Output => return the majority element (integer)

    - what is majority element ?

        - element whose count is greater than n/2 in the array



My approach

    - First thought

        - take one element at a time, traverse the entire array and count

        - if count > n/2 => return that element

        - Time Complexity

            - O(n²) — for each candidate, scan whole array



    - Another approach

        - Take a hashmap

        - Traversal 1: traverse on array and count the elements and cnt

        - traversal 2: traverse on the hashmap and see if count is greater than n/2

        - Complexity

             - Time: O(n)

             - space: O(n)



    - Another approach (best approach) — Boyer-Moore voting

        - Keep a `candidate` and a `count`

        - Scan once: if count is 0, set candidate to current element and count = 1

        - Else if current element equals candidate, count++

        - Else count-- (cancel one vote from candidate vs one other element)

        - Problem guarantees a majority, so return candidate after one pass (no verify pass needed here)

        - Complexity

             - Time: O(n)

             - space: O(1)



Patterns: [Boyer-Moore voting](../Patterns/boyer-moore-voting/readme.md)



- <a href="https://leetcode.com/problems/maximum-subarray/" target="_blank" rel="noopener noreferrer">Maximum Subarray</a> (LC 53) — Kadane's algorithm

    - Input => integer array `nums`

    - Output => largest sum of any **contiguous** subarray (at least one element)

    - what is Kadane's idea ?

        - At each index, either extend the best subarray ending at i−1, or start a new subarray at i



My approach

    - First thought

        - Check every subarray [i..j], sum and track max

        - Time Complexity

            - O(n²) or O(n³) depending on how sum is computed

        - Space

            - O(1)



    - Another approach

        - Prefix sums: for each start i, use running sum to j — still many pairs

        - Complexity

             - Time: O(n²)

             - space: O(1) or O(n) if storing prefix array



    - Another approach (best approach) — Kadane

        - `cur` = max sum of subarray **ending at current index**

        - For each `x`: `cur = max(x, cur + x)` then `ans = max(ans, cur)`

        - Initialize `ans` and `cur` with `nums[0]` (handles all-negative arrays)

        - Complexity

             - Time: O(n)

             - space: O(1)



Patterns: [Kadane (subarray DP)](../Patterns/kadane-dp/readme.md)


