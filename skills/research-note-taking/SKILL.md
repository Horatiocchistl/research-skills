---
name: research-note-taking
description: Create and maintain a structured folder of markdown notes from web research. This is a PRIMARY skill called by every other research skill in the workflow. Use it to initialize a research session folder, select a note-taking method, create individual note files from retrieved web sources, update the session index, and produce a clean, cited record of all findings. The LLM creates and manages all files directly — notes are written source by source as research happens, not summarized at the end.
license: MIT
metadata:
  author: Ronald Dean Strawbridge
  version: 1.1.0
  category: research
  tags: [note-taking, markdown, file-management, citations, index, session-log, cornell, zettelkasten, charting]
---

# Research Note-Taking

## Why This Skill Exists

The human brain stores approximately 7 items in short-term memory for about 20 seconds. Without notes, little survives a one-hour research session — and an agent's context window has the same problem at larger scale. Notes act as an **external storage device, similar to the role of the cloud** (BCIT Study Skills). The difference: the agent writes the notes, and the notes persist beyond the context window.

This is the same reason human researchers take notes: not to record everything, but to safely put something down so attention can move forward. Each source processed → one note file written → findings released from active context. The index tracks what exists. The folder is the memory.

**This skill is called by every other research skill.** Whenever a source is retrieved, evaluated, or produces a finding, that content goes into a note file immediately — not at the end of the session.

**Do not copy verbatim.** Per BCIT, copying content word for word is passive — it does not support understanding or retention. Every note file contains paraphrases and labeled quotes, not raw content dumps. The act of distilling to key points is itself part of the research process.

### How this skill is structured

The file-per-source system in this skill is the **Zettelkasten method** — one atomic note per source, unique identifier (S1, S2…), linked via the session index. Per Box, this is the most effective method for long-term research projects that require connecting ideas across sources.

---

## Core Rules

1. **One note file per source**: each retrieved source gets its own `.md` file.
2. **Cited sources only**: if a source cannot produce a valid APA 7 or MLA 9 citation, it does not get a note file. Log it in the index as `uncitable` and move on.
3. **Index is always current**: every time a note file is created, the index is updated immediately.
4. **Paraphrase, don't transcribe**: findings are written in the agent's own words. Verbatim text is wrapped in `>` blockquote and labeled `QUOTE`. Paraphrases are labeled `PARAPHRASE`. No unlabeled text.
5. **Preview before writing**: skim source headings, abstract, and section titles before writing any notes. Do not start recording until after previewing.

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
**Note-taking method:** [selected in Step 2]  
**Status:** In progress

## Sources

| ID | Title | Author | Date | Credibility | Citation status | File |
|---|---|---|---|---|---|---|

## Deferred

| URL | Reason |
|---|---|

## Open Questions

[Questions that arise during research that need follow-up — add throughout session]

## Session Notes

[Running observations, patterns noticed, gaps identified]
```

The index table starts empty. It is filled in Step 4 each time a note file is created.

---

## Step 2 — Select a Note-Taking Method

Choose before starting. The method determines how findings are structured inside each note file. Record the chosen method in `index.md`.

| Method | Best for | Structure | Source |
|---|---|---|---|
| **Outline** *(default)* | Structured topics with clear hierarchy; sources with sections and arguments | Topic → subtopics → supporting facts (nested bullets) | UGA OSSA / Box |
| **Cornell** | Abstract subjects with central ideas; any source you will revisit or synthesize; NOT for heavy stats or terminology | Notes (right) + Cues/Questions (left) + Summary (bottom) | UGA OSSA / Box / BCIT |
| **Charting** | Fact/data-heavy material; comparing sources on the same dimensions; statistics, definitions, comparisons | Column per dimension, row per source — built into the index | UGA OSSA / Box |
| **Sentence** | Fast-paced unstructured sources; dense material; when organization can happen later | One complete sentence per fact/claim, numbered sequentially | UGA OSSA / Box |
| **Mapping** | Complex interconnected content; understanding how themes relate across sources; preview material first to gauge scope | Main topic → branches → sub-branches (use indented headers + `→`) | UGA OSSA / Box |
| **Boxing** | Multiple distinct discussion tracks; brainstorming sources; visual separation of topics | Sections wrapped in horizontal rules, each with a header + notes block | Box |
| **Zettelkasten** | Long-term multi-session research; building a knowledge base across many sources | One atomic note per source; unique ID; cross-linked via index | Box |

**Default rule:** Use **Outline** for single-session research. Use **Cornell** when sources contain abstract arguments you will need to synthesize. Use **Charting** when comparing multiple sources on the same dimensions. Use **Zettelkasten** (this skill's base system) automatically for multi-session research.

**Preparation before writing any note** (per UGA OSSA + BCIT):
1. **Preview the source first** — skim headings, abstract, section titles; look for main topics, bolded terms, and summaries/conclusions before writing anything
2. **Review the research plan** (plan-the-support output) as the road map before starting each session
3. **Review the session index** from any previous session — provides context so new sources connect to what is already recorded
4. **Decide method and folder structure before the first note file** — organization planned in advance, not retroactively
5. **For long sources**: write a brief preview summary (what's familiar, what's challenging) before full processing
6. **Include source reference in every note** — URL, date accessed, and section identifiers — so you can return to the source later

---

## Step 3 — Create a Note File for Each Source

When a source is retrieved and passes the citation check (see `cited-source-parser` Step 0 and `source-credibility`), create a note file:

**File naming**: `[ID]-[slug-from-title].md`  
Example: `S1-google-local-ranking-factors.md`

---

### Outline Template *(default)*

> Per BCIT: mark where each piece of information came from. Add the source URL or section title next to each supporting point so you can return to verify. Do not leave supporting points as orphaned bullets with no source reference.

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

[Key findings extracted from this source, one per bullet. Each bullet: finding + (source section or URL anchor)]

- [Finding 1] ([section title or URL])
- [Finding 2] ([section title or URL])

## Quotes

> QUOTE: "Exact verbatim text." (Author, Year, p. X or URL)

## Paraphrases

PARAPHRASE [S1]: [Your words summarizing the author's point — not their words]

## Notes

[Anything notable about this source: limitations, conflicts with other sources, follow-up questions it raises]
```

---

### Cornell Template

Use when the source deals in abstract ideas or central arguments you will return to during synthesis.

```markdown
# [Title of Source]

**Source ID:** S1  
**URL:** [full URL]  
**Author / Org:** [name]  
**Published:** [date or "no date"]  
**Accessed:** [today]  
**Credibility tier:** [1–5]

## Citation

**APA 7:** [formatted citation]  
**MLA 9:** [formatted citation]

---

| Cues / Questions | Notes |
|---|---|
| What is the central claim? | [finding close to the source's own language] |
| What evidence supports it? | [QUOTE or PARAPHRASE + label] |
| Who is the intended audience? | [observation about purpose and scope] |
| What is missing or contested? | [gap, limitation, or counterargument] |
| Follow-up question? | [any question this source raises for later] |

> Add cues after reading each section — not during. The cues column is for questions, key words, and what you do not yet understand. (BCIT)

## Summary

**Active recall first**: before writing, cover the Cues/Notes table above and attempt to recall the key points from memory. Then uncover and add anything missed. (BCIT)

[3–5 sentences in own words: what this source claims, how credible it is, and what it contributes to the research objective. Do NOT copy from the notes table — paraphrase.]
```

---

## Step 4 — Update the Index

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

### When Method = Charting

Add a comparison table to `index.md` directly below the Sources table. Columns are the research dimensions from the plan-the-support output. Rows are sources. Fill in one cell per source as it is processed — do not wait until all sources are gathered.

Example for a research objective comparing remote work productivity studies:

| Source | Sample size | Methodology | Finding | Year | Tier |
|---|---|---|---|---|---|
| S1 — Stanford Study | 16,000 workers | Randomized | +13% output | 2015 | 1 |

Charting is most useful when material is fact/data-heavy with statistics, comparisons, or definitions that need side-by-side reference — per Box and UGA OSSA.

---

## Step 5 — Close the Session

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

### Review Checklist

Before closing the session, complete the following (per Box note-taking best practices):

- [ ] Write down any unanswered questions that arose — add them under `## Open Questions` in `index.md`
- [ ] Flag sources that need follow-up (mark credibility tier as uncertain or add `NEEDS-CORROBORATION`)
- [ ] Confirm every note file has a Summary section filled in (Cornell) or a Relevance line (Outline) — not left blank
- [ ] Record the recommended next skill in the session summary

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
