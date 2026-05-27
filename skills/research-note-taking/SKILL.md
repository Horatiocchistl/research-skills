---
name: research-note-taking
description: Create and maintain a structured folder of markdown notes from web research. Use this skill to initialize a research session folder, create individual note files from retrieved web sources, update the session index, and produce a clean, cited record of all findings. The LLM creates and manages all files directly. Only sources that pass citation verification are logged as note files. Raw, uncited content is not saved.
license: MIT
metadata:
  author: Ronald Dean Strawbridge
  version: 1.0.0
  category: research
  tags: [note-taking, markdown, file-management, citations, index, session-log]
---

# Research Note-Taking

Create and manage a folder of markdown notes from web research. The LLM writes every file. The folder is the record — not memory, not a summary at the end. Notes are written source by source as research happens.

## Core Rules

1. **One note file per source**: each retrieved source gets its own `.md` file.
2. **Cited sources only**: if a source cannot produce a valid APA 7 or MLA 9 citation, it does not get a note file. Log it in the index as `uncitable` and move on.
3. **Index is always current**: every time a note file is created, the index is updated immediately.
4. **Exact quotes are marked**: anything copied verbatim is wrapped in `>` blockquote and labeled `QUOTE`. Paraphrases are labeled `PARAPHRASE`. No unlabeled text.

---

## Step 1 — Initialize the Session Folder

At the start of every research session, create the folder structure:

```
research-notes/
└── YYYY-MM-DD-[topic-slug]/
    ├── index.md
```

**Folder naming**: use today's date and a short slug from the research objective.  
Example: `research-notes/2026-05-27-local-seo-ranking-factors/`

**Create `index.md` immediately** with this structure:

```markdown
# Research Session: [Research Objective]

**Date:** YYYY-MM-DD  
**Objective:** [copied from plan-the-support output]  
**Status:** In progress

## Sources

| ID | Title | Author | Date | Credibility | Citation status | File |
|---|---|---|---|---|---|---|

## Deferred

| URL | Reason |
|---|---|

## Session Notes

[running observations, patterns noticed, gaps identified]
```

The index table starts empty. It is filled in Step 3 each time a note file is created.

---

## Step 2 — Create a Note File for Each Source

When a source is retrieved and passes the citation check (see `cited-source-parser` Step 0 and `source-credibility`), create a note file:

**File naming**: `[ID]-[slug-from-title].md`  
Example: `S1-google-local-ranking-factors.md`

**Note file structure:**

```markdown
# [Title of Source]

**Source ID:** S1  
**URL:** [full URL]  
**Author:** [name or organization]  
**Publication date:** [as shown; "no date" if absent]  
**Date accessed:** [today]  
**Source type:** [academic / government / news / blog / report]  
**Credibility tier:** [1–5 from source-credibility assessment]

## Citation

**APA 7:**  
[formatted citation]

**MLA 9:**  
[formatted citation]

---

## Relevance

[One sentence: which part of the research objective does this source address?]

---

## Findings

[Key findings extracted from this source, one per bullet]

- [Finding 1]
- [Finding 2]

## Quotes

> QUOTE: "Exact verbatim text." (Author, Year, p. X or URL)

## Paraphrases

PARAPHRASE [S1]: [Your words summarizing the author's point — not their words]

## Notes

[Anything notable about this source: limitations, conflicts with other sources, follow-up questions it raises]
```

---

## Step 3 — Update the Index

Immediately after creating each note file, add a row to the `index.md` source table:

```markdown
| S1 | [Title] | [Author] | [Date] | [Tier 1–5] | Valid | [S1-slug.md] |
```

If a source fails the citation check, add it as:

```markdown
| — | [URL or title] | — | — | — | Uncitable — [reason] | no file |
```

The index must reflect the current state of the session at all times. Do not batch-update at the end.

---

## Step 4 — Close the Session

When the session ends (timebox reached or sufficiency threshold met from `plan-the-support`), update `index.md`:

1. Change `Status:` from `In progress` to `Complete` or `Incomplete — [reason]`
2. Add a session summary under `## Session Notes`:

```markdown
## Session Summary

**Sources logged:** [count]  
**Uncitable sources skipped:** [count]  
**Objectives covered:** [list]  
**Objectives not covered:** [list — insufficient sources found]  
**Deferred items:** [count]  
**Recommended next skill:** [research-synthesis / iterative-validation / more research needed]
```

---

## Folder Output Example

```
research-notes/
└── 2026-05-27-local-seo-ranking-factors/
    ├── index.md
    ├── S1-google-business-profile-ranking.md
    ├── S2-moz-local-seo-study.md
    └── S3-search-engine-journal-local-factors.md
```

The folder is the complete, citable record of the research session. Hand it to `research-synthesis` when ready to write.
