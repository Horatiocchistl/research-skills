---
name: plan-the-support
description: Plan and prepare a research engagement before any searching begins. Use this skill when starting a new research task — whether the researcher is human, AI, or both working together. Establishes clear objectives, source targets, a note-taking workspace, keyword strategy, and a time boundary before any search tool is invoked. This skill runs first. No other research skill should begin until this plan is complete and confirmed.
license: MIT
metadata:
  author: Ronald Dean Strawbridge
  version: 1.0.0
  category: research
  tags: [planning, preparation, objectives, keywords, workspace, research-intake]
---

# Plan the Support

Prepare the research engagement before any searching begins. A research session without a plan produces unfocused results, uncited sources, and wasted time. This skill produces a confirmed Research Plan that all downstream skills reference.

## Core Principle

Do not search until the plan is confirmed. Every action in this skill happens before a single search query is run.

---

## Step 1 — Define Objectives

Clearly write out what needs to be known. Vague topics produce generic results — specificity directs the search.

| Vague (do not use) | Specific (use this) |
|---|---|
| "learn about SEO" | "find the top 5 ranking factors for local service businesses" |
| "research climate change" | "find peer-reviewed studies on Arctic ice loss rates 2015–2025" |
| "understand the housing market" | "find median home price trends in mid-size US cities 2020–2024" |

**Output:** Write the research objective as one or two sentences. If the human researcher has provided a topic, restate it in specific, answerable form and confirm before proceeding.

---

## Step 2 — Select Sources

Match the research objective to the appropriate tier of the web resource hierarchy before searching. Starting at the highest applicable tier prevents defaulting to low-credibility results.

| Tier | Source type | Specific databases / where to search | Use when |
|---|---|---|---|
| **1 — Highest** | Peer-reviewed journals, university press, conference proceedings | Google Scholar, PubMed (biomedical), JSTOR, institutional library | Empirical claims, scientific or social science questions |
| **2 — High** | Government reports, international org data, think tank research | .gov portals, WHO, World Bank, Pew Research, ERIC (education), institutional repositories | Statistics, policy, regulatory facts, international data |
| **3 — Moderate-High** | Major newspapers, established trade and science publications | Publication websites, ProQuest, EBSCO | Current events, investigative findings, documented public facts |
| **4 — Variable** | Wikipedia, organizational blogs, commercial sites | Google, Bing | Background orientation only — not primary citation |
| **5 — Lowest** | Social media, forums, personal blogs | Platform search | Do not use as research sources — signal only |

**Output:** Identify which tiers apply to this objective. Start searching at the highest applicable tier. Document which tiers were searched in the Research Plan.

**Default rule:** If the objective is empirical (statistics, science, policy), begin at Tier 1–2. If the objective is current events or industry knowledge, begin at Tier 2–3. Do not begin at Tier 4 unless Tiers 1–3 return nothing relevant.

---

## Step 3 — Set Up the Workspace

Before the first search, prepare the note-taking environment. Use the `research-note-taking` skill to initialize a session log. Every URL, quote, and citation captured during research goes into this log — not into memory.

The workspace must be ready to record:
- Source URL
- Publication date
- Author or publishing organization
- Direct quotes (exact text, in quotation marks)
- Primary citation formatted in APA 7 or MLA 9
- Relevance note: which objective does this source address?

**Do not begin searching without an active workspace.** Sources not logged at retrieval time are lost.

---

## Step 4 — Formulate Keywords

Build the search strategy before opening any search tool.

1. **Exact phrases**: identify the core noun phrases from the objective. Wrap multi-word concepts in quotation marks (e.g., `"local service businesses"` not `local service businesses`).
2. **Operators**: select applicable search operators:
   - `site:edu` or `site:gov` — restrict to authoritative domains
   - `filetype:pdf` — surface reports and papers
   - `"[exact phrase]"` — require exact match
   - `-[term]` — exclude irrelevant results
3. **Synonyms**: list 2–3 alternative terms for the core concept. Run separate queries for each to avoid missing sources that use different terminology.
4. **Negations**: identify terms to exclude that would contaminate results.

**Output:** A keyword table:

| Core phrase | Synonym 1 | Synonym 2 | Operator to apply |
|---|---|---|---|
| | | | |

---

## Step 5 — Establish a Timebox

Set a time boundary for the research session before starting. Research without a boundary drifts into the rabbit hole — each source leads to another until the original objective is lost.

Define:
- **Session limit**: maximum time or number of sources for this session
- **Sufficiency threshold**: minimum sources needed before synthesis can begin (default: 3 independent sources per sub-question)
- **Rabbit hole rule**: if a search result addresses a different question than the current objective, log the URL for a future session — do not follow it now

**Output:** One sentence stating the session limit and sufficiency threshold. Example: *"This session runs for 45 minutes or until 3 independent sources per objective are logged, whichever comes first."*

---

## Research Plan Output

Before proceeding to any search skill, produce and confirm the following:

```
Research Objective:   [one or two specific sentences]
Source Types:         [list of 2–4 types]
Workspace:            [initialized — see research-note-taking log]
Keyword Table:        [core phrases, synonyms, operators]
Session Limit:        [time or source count]
Sufficiency Target:   [sources required per sub-question]
Confirmed by:         [human researcher / AI / both]
```

Do not proceed to `process-web-research` or any search tool until this plan is confirmed.
