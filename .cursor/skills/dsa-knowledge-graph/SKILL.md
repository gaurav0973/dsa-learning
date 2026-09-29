---
name: dsa-knowledge-graph
description: Maintains the DSA learning knowledge graph in this repo—Day journals, Patterns folders, and root index. Classifies problems via web search, adds LeetCode links (new tab), fills day-X.md, assigns each problem to exactly one pattern (best approach), grows Patterns/ as new techniques appear, and syncs Input/Output in readme files. Use when solving LeetCode/DSA problems, writing day logs, updating Patterns, or when the user mentions DSA journey, patterns, or knowledge graph.
---

# DSA Knowledge Graph

This repo is a **pattern-indexed DSA journal**. Each solved problem lives in a daily log (`Day/day-X.md`) and in **exactly one** pattern hub (`Patterns/<pattern>/readme.md`) chosen by the **best (final) approach**. The root `readme.md` indexes **all** pattern folders (the list grows) and lists each day's problems with links and Input/Output.

**Web search is mandatory** for (1) canonical problem URLs and (2) confirming which pattern fits the optimal solution. Do not guess slugs or pattern names from memory alone.

## LeetCode links (open in new tab)

Plain markdown `[title](url)` opens in the same tab in most viewers. For **every external LeetCode problem link**, use HTML:

```markdown
- <a href="https://leetcode.com/problems/slug/" target="_blank" rel="noopener noreferrer">Problem Title</a> (LC N)
```

Use this in `Day/`, root `readme.md` daily log, and `Patterns/*/readme.md` problem lists.

**Internal links** (day files, pattern readmes under `Patterns/`) stay normal markdown: `[day-1.md](../../Day/day-1.md)`.

## Repository layout

```
DSA/
├── readme.md                 # Pattern index (grows) + daily log
├── Day/
│   └── day-X.md
└── Patterns/
    └── <pattern-slug>/       # New folders added as you solve more problems
        └── readme.md
```

**Pattern folder naming:** lowercase kebab-case. [patterns-catalog.md](patterns-catalog.md) is a **starter list**, not exhaustive.

## Growing the pattern index

As question count increases, **new patterns will appear**. Whenever the best approach does not fit an existing `Patterns/<slug>/`:

1. Web search the technique name and confirm it is a distinct pattern.
2. Create `Patterns/<new-slug>/readme.md` with **When to use** and **Problems** (can start with one problem).
3. **Append** a new bullet to **Patterns (index)** in root `readme.md`: `- [<slug>](Patterns/<slug>/readme.md)`.
4. Add a row to [patterns-catalog.md](patterns-catalog.md) for future reference.
5. File the problem only under the new pattern readme.

Never force a problem into a weak-fit folder when a new slug is more accurate.

## End-to-end workflow

```
- [ ] Read latest Day/*.md and scan Patterns/ for duplicate LC entries
- [ ] Web search: problem → LeetCode URL + LC number
- [ ] Web search: best approach → pattern slug (existing or new)
- [ ] If new pattern: create folder + readme + root index line + catalog row
- [ ] Update day-X.md (new-tab LeetCode link, one Patterns: line)
- [ ] Add problem to exactly ONE pattern readme (new-tab link + I/O)
- [ ] Remove same problem from any other pattern readme
- [ ] Update root readme.md Daily log (new-tab link + I/O)
```

### Step 1: Analyze `Day/` folder

1. List all `Day/day-*.md`; work on the **latest** day unless the user names a file.
2. Fill placeholders and incomplete "best approach" sections.
3. Match style in [templates.md](templates.md).

### Step 2: Web search — problem link

Search: `"<problem name>" site:leetcode.com/problems`

**Preferred URL:** `https://leetcode.com/problems/<slug>/`

Record with new-tab HTML (see above).

### Step 3: Web search — single pattern (best approach)

The pattern folder is determined **only** by the technique in **"Another approach (best approach)"** (or the approach the user submitted).

- Brute force or hash map in the day file does **not** decide the pattern if the best approach is different.
- Do **not** list the same LC problem under two pattern folders.
- If no folder fits, **create a new pattern** (see "Growing the pattern index").

If the user later changes their best approach, **move** the problem: delete from the old pattern readme, add to the new one (create folder if needed), update root index if new, update the `Patterns:` line in the day file.

### Step 4: Update `day-X.md`

Checklist per problem:

- [ ] New-tab LeetCode link + LC number
- [ ] Input => / Output =>
- [ ] Key concept Q&A
- [ ] Brute → intermediate → **best** approach with time/space
- [ ] Single line: `Patterns: [Name](../Patterns/<slug>/readme.md)`

### Step 5: Update `Patterns/<pattern>/readme.md`

1. **When to use**
2. **Problems** — each entry:

```markdown
- <a href="https://leetcode.com/problems/slug/" target="_blank" rel="noopener noreferrer">Problem Name</a> (LC N) — [day-X.md](../../Day/day-X.md)
  - Input => ...
  - Output => ...
```

Before adding, **grep** `Patterns/` for the problem slug or LC number; if found elsewhere, remove that entry.

### Step 6: Update root `readme.md`

**Patterns (index):** one link per folder under `Patterns/`; add a line when a new pattern is created.

**Daily log:**

```markdown
- [day-1](Day/day-1.md)
  - <a href="https://leetcode.com/problems/slug/" target="_blank" rel="noopener noreferrer">Problem Name</a> (LC N)
    - Input => ...
    - Output => ...
```

## Knowledge graph rules

1. **One pattern per problem** in `Patterns/*/readme.md`.
2. **Best approach wins** for pattern assignment.
3. **I/O everywhere** — Day, root daily log, pattern readme.
4. **LeetCode links** — always `target="_blank"` HTML form.
5. **Growing patterns** — root index and `Patterns/` stay in sync; catalog is updated when adding slugs.
6. **No orphans** — every problem in `Day/` appears in one pattern readme and under its day in root `readme.md`.

## Anti-patterns

- Do not use markdown-only links for LeetCode URLs in indexes.
- Do not duplicate a problem across pattern readmes.
- Do not invent LeetCode slugs.
- Do not add a pattern folder without adding it to root **Patterns (index)**.

## Additional resources

- [templates.md](templates.md)
- [patterns-catalog.md](patterns-catalog.md)
