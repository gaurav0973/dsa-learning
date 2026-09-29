# Templates (match existing `Day/day-1.md` style)

## LeetCode link (always new tab)

```markdown
<a href="https://leetcode.com/problems/slug/" target="_blank" rel="noopener noreferrer">Problem Title</a> (LC N)
```

Use as the first part of a list item in Day/, root daily log, and pattern problem lists.

## Daily file header

```markdown
Today I solved N problems and these are the ones which I solved

```

## Per-problem block (Day/)

```markdown
- <a href="https://leetcode.com/problems/slug/" target="_blank" rel="noopener noreferrer">Problem Title</a> (LC N)
    - Input => ...
    - Output => ...
    - what is <concept> ?
        - ...

My approach
    ...

Patterns: [Pattern Name](../Patterns/<pattern-slug>/readme.md)
```

Use **one** `Patterns:` line — slug must match the best approach only.

## Pattern `readme.md`

```markdown
# Pattern Display Name

## When to use

<Signals in problem statements.>

## Problems

- <a href="https://leetcode.com/problems/slug/" target="_blank" rel="noopener noreferrer">Title</a> (LC N) — [day-X.md](../../Day/day-X.md)
  - Input => ...
  - Output => ...
```

## New pattern folder checklist

1. Create `Patterns/<new-slug>/readme.md` (When to use + first problem).
2. Add `- [<new-slug>](Patterns/<new-slug>/readme.md)` to root **Patterns (index)**.
3. Add row to `patterns-catalog.md`.

## Root `readme.md` — Daily log

```markdown
## Daily log

- [day-1](Day/day-1.md)
  - <a href="https://leetcode.com/problems/slug/" target="_blank" rel="noopener noreferrer">Title</a> (LC N)
    - Input => ...
    - Output => ...
```

## Root `readme.md` — Patterns index

Grows as you solve more problems; one entry per folder:

```markdown
## Patterns (index)

- [two-pointers](Patterns/two-pointers/readme.md)
- [monotonic-stack](Patterns/monotonic-stack/readme.md)
```
