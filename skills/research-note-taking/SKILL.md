---
name: research-note-taking
description: Initialize and maintain a structured research session log. Use this skill when setting up a workspace for a research session, logging a source at the moment of retrieval, recording a direct quote with attribution, or producing a session summary at the end of research. Called by plan-the-support during workspace setup. Every source retrieved during research must be logged through this skill before content is extracted.
license: MIT
metadata:
  author: Ronald Dean Strawbridge
  version: 1.0.0
  category: research
  tags: [note-taking, logging, workspace, citations, quotes, session-management]
---

# Research Note-Taking

Maintain a structured session log throughout a research engagement. Notes not captured at retrieval time are lost or misattributed. This skill enforces logging at the point of contact with every source.

## Core Rules

1. **Log at retrieval, not after**: record source metadata before reading the content.
2. **Quotes are exact or they are not quotes**: if not copied verbatim, it is a paraphrase — label it as such.
3. **Every note links to a source**: no floating observations without a source ID attached.
4. **The log is the record**: at session end, the log is the authoritative record of what was found and where.

---

## Step 1 — Initialize Session Log

At the start of every research session, create a new session entry:

```
Session ID:       [date + topic slug, e.g., 2026-05-27-local-seo]
Research Objective: [copied from plan-the-support output]
Started:          [timestamp]
Researcher:       [human / AI / both]
```

The session log remains open and active until the session ends. All steps below append to this log.

---

## Step 2 — Log Each Source

When a source is retrieved, immediately record the following before reading:

```
Source ID:        [S1, S2, S3... sequential]
URL:              [full URL as retrieved]
Title:            [exact page or article title]
Author:           [name(s) or organization; "no author" if absent]
Publication date: [as shown on page; "no date" if absent]
Date accessed:    [today's date]
Source type:      [academic / government / news / blog / report / other]
Objective link:   [which research objective does this address?]
APA 7 citation:   [formatted immediately — see cited-source-parser]
MLA 9 citation:   [formatted immediately — see cited-source-parser]
```

**Do not extract content from a source until this record is complete.**

---

## Step 3 — Log Quotes and Findings

For each piece of content extracted from a source:

**Direct quote:**
```
[S1] "Exact text copied verbatim from the source." (Author, Year, or URL if no page number)
```

**Paraphrase:**
```
[S1] PARAPHRASE: The author argues that... [your words, not theirs]
```

**Key finding:**
```
[S1] FINDING: [one sentence summarizing the relevant data point or claim]
Relevance: [why this matters to the research objective]
```

Never mix quotes and paraphrases without clear labeling. Mislabeled paraphrases become accidental plagiarism.

---

## Step 4 — Flag and Defer

When a source or finding falls outside the current research objective:

```
DEFERRED: [URL or finding]
Reason deferred: [outside current objective / follow-up question / different session]
```

Do not follow deferred items during the current session. Log them and return to the objective.

---

## Step 5 — Session Summary

At session end, produce:

```
Session ID:         [from Step 1]
Ended:              [timestamp]
Sources logged:     [count]
Objectives covered: [list]
Objectives incomplete: [list — insufficient sources found]
Deferred items:     [count and brief description]
Recommended next:   [next skill to run — process-web-research / research-synthesis / iterative-validation]
```

---

## Tool Integration

<!-- 
This skill requires connection to the note-taking tool configured for this agent.
Supported integrations: [to be specified by deployment — Notion, Evernote, local markdown, etc.]
The session log format above is tool-agnostic. The integration layer maps these fields 
to the target tool's data structure.
-->

**Pending:** tool integration details to be specified. Until integrated, maintain the session log as a structured markdown block in the active conversation or a local file.
