# Templates (match existing `Day/day-1.md` style)

## Daily file header

```markdown
Today I solved N problems and these are the ones which I solved

```

## Per-problem block (Day/)

```markdown
- [Problem Title](https://leetcode.com/problems/slug/) (LC N)
    - Input => ...
    - Output => ...
    - what is <concept> ?
        - ...

My approach
    - First thought
        - ...
        - Time Complexity
            - ...

    - Another approach
        - ...
        - Complexity
             - Time: ...
             - Space: ...

    - Another approach (best approach)
        - ...
        - Complexity
             - Time: ...
             - Space: ...

Patterns: [Pattern Name](../Patterns/<pattern-slug>/readme.md)
```

Use **one** `Patterns:` line — slug must match the best approach only.

## Pattern `readme.md`

```markdown
# Pattern Display Name

## When to use

<Signals in problem statements.>

## Problems

- [Title](https://leetcode.com/problems/slug/) (LC N) — [day-X.md](../../Day/day-X.md)
  - Input => ...
  - Output => ...
```

## Root `readme.md` — Daily log

```markdown
## Daily log

- [day-1](Day/day-1.md)
  - [Title](https://leetcode.com/problems/slug/) (LC N)
    - Input => ...
    - Output => ...
```

Mirror Input/Output from the day file; add a nested bullet per problem for each day.

## Root `readme.md` — Patterns index

```markdown
## Patterns (index)

- [two-pointers](Patterns/two-pointers/readme.md)
```
