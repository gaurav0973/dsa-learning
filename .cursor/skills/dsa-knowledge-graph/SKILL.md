---
name: dsa-knowledge-graph
description: Maintains the DSA learning knowledge graph in this repo—Day journals, Patterns folders, and root index. Classifies problems via web search, adds official LeetCode links, fills day-X.md, assigns each problem to exactly one pattern (best approach), and syncs Input/Output in readme files. Use when solving LeetCode/DSA problems, writing day logs, updating Patterns, or when the user mentions DSA journey, patterns, or knowledge graph.
---

# DSA Knowledge Graph

This repo is a **pattern-indexed DSA journal**. Each solved problem lives in a daily log (`Day/day-X.md`) and in **exactly one** pattern hub (`Patterns/<pattern>/readme.md`) chosen by the **best (final) approach**. The root `readme.md` indexes patterns and lists each day's problems with links and Input/Output.

**Web search is mandatory** for (1) canonical problem URLs and (2) confirming which pattern fits the optimal solution. Do not guess slugs or pattern names from memory alone.

## Repository layout

```
DSA/
├── readme.md                 # Pattern index + daily log with problem links & I/O
├── Day/
│   └── day-X.md              # Full thought process; same I/O as index/pattern lists
└── Patterns/
    └── <pattern-slug>/
        └── readme.md         # When to use + problems (link + I/O + day link)
```

**Pattern folder naming:** lowercase kebab-case. See [patterns-catalog.md](patterns-catalog.md).

## End-to-end workflow

```
- [ ] Read latest Day/*.md and scan all Patterns/*/readme.md for duplicates
- [ ] Web search: problem title → LeetCode URL + LC number
- [ ] Web search: best approach → single pattern slug
- [ ] Update day-X.md (fill gaps, one Patterns: line)
- [ ] Add/update problem in exactly ONE Patterns/<slug>/readme.md (with I/O)
- [ ] Remove same problem from any other pattern readme if present
- [ ] Update root readme.md Daily log (problem link + I/O under each day)
- [ ] Add new pattern slug to root index if folder was created
```

### Step 1: Analyze `Day/` folder

1. List all `Day/day-*.md`; work on the **latest** day unless the user names a file.
2. Fill placeholders and incomplete "best approach" sections.
3. Match style in [templates.md](templates.md).

### Step 2: Web search — problem link

Search: `"<problem name>" site:leetcode.com/problems`

**Preferred URL:** `https://leetcode.com/problems/<slug>/`

```markdown
- [Majority Element](https://leetcode.com/problems/majority-element/) (LC 169)
```

### Step 3: Web search — single pattern (best approach)

The pattern folder is determined **only** by the technique in **"Another approach (best approach)"** (or the approach the user says they submitted).

- Brute force or hash map in the day file does **not** decide the pattern if the best approach is different.
- Do **not** list the same LC problem under two pattern folders.
- Alternate approaches belong only in the day file under `My approach`.

| Problem | Best approach → single pattern |
|---------|--------------------------------|
| Majority Element | Boyer-Moore → `boyer-moore-voting` (not `hash-map` if best is voting) |
| Maximum Subarray | Kadane → `kadane-dp` |

If the user later changes their best approach, **move** the problem: delete from the old pattern readme, add to the new one, update the `Patterns:` line in the day file.

### Step 4: Update `day-X.md`

Checklist per problem:

- [ ] Markdown link + LC number
- [ ] Input => / Output => (same text used in root + pattern readmes)
- [ ] Key concept Q&A
- [ ] Brute → intermediate → **best** approach with time/space
- [ ] Single line: `Patterns: [Name](../Patterns/<slug>/readme.md)`

### Step 5: Update `Patterns/<pattern>/readme.md`

1. **When to use** — when this technique applies.
2. **Problems** — each entry:

```markdown
- [Problem Name](https://leetcode.com/problems/slug/) (LC N) — [day-X.md](../../Day/day-X.md)
  - Input => ...
  - Output => ...
```

Before adding, **grep** `Patterns/` for the problem slug or LC number; if found elsewhere, remove that entry.

### Step 6: Update root `readme.md`

Under **Daily log**, for each `day-X.md` link, nest every problem that day:

```markdown
- [day-1](Day/day-1.md)
  - [Problem Name](https://leetcode.com/problems/slug/) (LC N)
    - Input => ...
    - Output => ...
```

Keep the **Patterns (index)** list of pattern readme links. Copy Input/Output verbatim from the day file (short form).

## Knowledge graph rules

1. **One pattern per problem:** Each LC problem appears in at most one `Patterns/*/readme.md`.
2. **Best approach wins:** Pattern assignment follows the optimal solution, not earlier attempts in the day log.
3. **I/O everywhere:** Same Input/Output under the problem in `Day/`, root `readme.md` daily section, and pattern readme.
4. **Bidirectional links:** Pattern entry links to day file; day file links to one pattern readme.
5. **No orphans:** Every problem in `Day/` must appear in exactly one pattern readme and under its day in root `readme.md`.
6. **Stable links:** Use `leetcode.com/problems/` URLs in indexes.

## When the user is actively solving

1. Web-search link and pattern as soon as the problem is named.
2. Log I/O in day file first; mirror to root + pattern when best approach is known.
3. If best approach is still unknown, omit pattern readme until the final approach is written.

## Anti-patterns

- Do not duplicate a problem across multiple pattern readmes.
- Do not assign pattern from brute-force or hash-map sections when best approach is different.
- Do not invent LeetCode slugs.
- Do not list a problem in root Daily log without Input/Output lines.

## Additional resources

- [templates.md](templates.md)
- [patterns-catalog.md](patterns-catalog.md)
