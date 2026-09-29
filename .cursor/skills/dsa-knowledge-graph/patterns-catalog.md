# Pattern catalog (grows with your journey)

**Not exhaustive.** When a new best approach does not fit any row below, create `Patterns/<new-slug>/`, add the problem there, append the slug to root `readme.md` **Patterns (index)**, and add a row here.

Use web search to confirm placement. Each problem lives in **one** folder—the slug that matches the **best approach** documented in the day file.

| Slug | Use when (best / final technique) |
|------|-----------------------------------|
| `arrays` | Best solution is plain array scan/manipulation, no named pattern |
| `hash-map` | Best solution relies on a frequency or complement map |
| `two-pointers` | Best solution uses two indices from ends or slow/fast |
| `sliding-window` | Best solution expands/shrinks a contiguous window |
| `prefix-sum` | Best solution uses prefix sums (± hash map for target) |
| `boyer-moore-voting` | Best solution is Boyer-Moore / majority vote O(1) space |
| `kadane-dp` | Best solution is Kadane (extend-or-reset subarray DP) |
| `dp` | Best solution is general DP (not Kadane-only) |
| `trees` | Best solution is tree traversal / recursion on nodes |
| `binary-search` | Best solution binary-searches answer or sorted structure |
| `stack` | Best solution uses a stack / monotonic stack |
| `heap` | Best solution uses a heap for top-K / merging |
| `graphs` | Best solution is BFS/DFS/shortest path / UF |
| `backtracking` | Best solution is search with undo |
| `greedy` | Best solution is greedy with proof |
| `bit-manipulation` | Best solution is bitwise |

## One problem, one pattern

- Alternate approaches (e.g. hash map before Boyer-Moore) stay in `Day/day-X.md` only.
- Before adding a problem to a pattern readme, search all `Patterns/**/readme.md` for that LC number or slug and remove duplicates.
- Changing best approach → move the problem entry to the new pattern readme.

## Naming new patterns

1. Search: `"<technique>" leetcode pattern`
2. Slug: kebab-case technique name
3. Add a row to this table when the folder is created
