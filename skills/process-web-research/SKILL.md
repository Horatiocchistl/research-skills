---
name: process-web-research
description: Process and evaluate raw web research using the 5-tier source hierarchy. Use this skill when executing searches from a plan-the-support research plan, retrieving raw web content, evaluating what was found against credibility standards, and feeding verified findings into the research-note-taking session log. Applies the web resource hierarchy to determine where to search and how to weight what is found.
license: MIT
metadata:
  author: Ronald Dean Strawbridge
  version: 1.1.0
  category: research
  tags: [web-research, search, credibility, hierarchy, retrieval, evaluation]
---

# Process Web Research

Execute searches and evaluate raw web content using the 5-tier source hierarchy. Do not retrieve and accept — retrieve, evaluate, and log only what meets the standard for the research objective.

## Core Rule

Search from the top of the hierarchy down. Start at Tier 1 or 2 for empirical and policy claims. Only descend to lower tiers when higher tiers return insufficient results — and document why.

---

## The Web Resource Hierarchy

Sources rank by credibility, editorial rigor, and proximity to original data.

### Tier 1 — Peer-Reviewed Academic & Scholarly (Highest Credibility)
Written by field experts. Scrutinized by other researchers before publication.

**Examples:** Peer-reviewed journals, university press books, conference proceedings  
**Where to search:** Google Scholar, PubMed (biomedical), JSTOR, institutional library databases  
**Assign credibility:** Highest — primary citation for empirical claims

### Tier 2 — Evaluated & Official Reports (High Credibility)
Curated data and professional analysis. No peer review but strict institutional accountability.

**Examples:** Government (.gov) white papers, World Bank, WHO, Pew Research, think tank reports  
**Where to search:** Official .gov portals, institutional repositories, ERIC (education), WHO, World Bank data  
**Assign credibility:** High — verify methodology before citing statistics

### Tier 3 — Reputable Journalism & Media (Moderate-High Credibility)
Secondary analysis and investigative reporting. Employ editors and fact-checkers but may carry bias.

**Examples:** The New York Times, The Wall Street Journal, Scientific American, The Economist  
**Where to search:** Publication websites directly, ProQuest, EBSCO  
**Assign credibility:** Moderate-High — corroborate technical claims with Tier 1–2

### Tier 4 — General Web Content & Wikis (Variable Credibility)
Open internet. Quality ranges from accurate to agenda-driven.

**Examples:** Wikipedia, organizational blogs, commercial websites  
**Where to search:** Google, Bing  
**Assign credibility:** Variable — background orientation only; never primary citation

### Tier 5 — Social Media & Unmoderated Forums (Lowest Credibility)
Unverified personal opinion or first-hand accounts. No editorial oversight.

**Examples:** Reddit, X, TikTok, personal blogs  
**Assign credibility:** None for research — log as signal only; verify any claim through Tier 1–3

---

## Step 1 — Match Search to Tier

From the Research Plan (plan-the-support output), identify the required tier for each sub-question:

- Empirical / scientific claim → begin Tier 1
- Policy / statistics / regulatory → begin Tier 2
- Current events / documented public facts → begin Tier 3
- Background context only → Tier 4 acceptable, note limitation

Do not begin at Tier 4 when Tier 1–3 sources exist for the topic.

---

## Step 2 — Execute Search

Use the keyword table from plan-the-support. Apply operators appropriate to the target tier:
- `site:edu` or `site:gov` → bias toward Tier 1–2
- `filetype:pdf` → surface reports and papers
- Database-specific search → use the database's own search interface for Tier 1–3

Record which query and which database produced each result.

---

## Step 3 — Evaluate Before Extracting

Before reading the content of any retrieved source:
1. Identify the tier it belongs to
2. Check that it meets the tier requirement for this sub-question
3. Run the credibility gate from `source-credibility` if tier is uncertain

If the source does not meet the tier requirement: log as rejected in the session index. Do not extract content from it.

---

## Step 4 — Log and Hand Off

For every source that passes Step 3: hand to `research-note-taking` to create a note file. Do not extract content directly into conversation or memory — it goes into the note file.

Record in the session index:
- Tier assigned
- Database or search tool used
- Query that found it
- Pass / Reject decision and reason
