---
name: source-credibility
description: Assess the credibility, authority, bias, and reliability of any research source — website, article, social media post, dataset, or publication. Use this skill when asked to evaluate whether a source is trustworthy, apply the CRAAP test or lateral reading to a source, detect potential misinformation or propaganda, rate a source for use in academic or professional research, or determine which of several sources is most reliable. Combines CRAAP, SIFT, RADAR, and lateral reading frameworks. Grounded in APA 7th and MLA 9th source standards.
license: MIT
metadata:
  author: Ronald Dean Strawbridge
  version: 1.0.0
  category: research
  tags: [credibility, bias, sources, CRAAP, SIFT, lateral-reading, misinformation, evaluation]
---

# Source Credibility Assessment

Evaluate any source using layered, established frameworks — not intuition.

## Frameworks Used

| Framework | Origin | Core contribution |
|---|---|---|
| **CRAAP Test** | Sarah Blakeslee, Cal State Chico (2004) | Five-dimension scoring: Currency, Relevance, Authority, Accuracy, Purpose |
| **SIFT** | Mike Caulfield, UW (2019) | Stop before sharing; Investigate the source; Find better coverage; Trace claims |
| **RADAR** | Radford University | Rationale, Authority, Date, Accuracy, Relevance |
| **Lateral Reading** | Stanford History Education Group | Look outward before reading deeply |

---

## Step 1 — Lateral Reading (always do this first)

Before engaging with the source's content, look outward:

1. **Search the publisher name**: Use the search query `"[publisher or site name]" bias` or `"[publisher name]" credibility`. Look for media bias charts, press coverage, and Wikipedia entries — not to cite them, but to calibrate.
2. **Search the author name**: Use `"[author full name]" [institution or field]`. Verify the credentials claimed in the byline match what independent sources say.
3. **Check fact-checkers**: Search `"[claim or headline]" site:snopes.com OR site:factcheck.org OR site:politifact.com OR site:reuters.com/fact-check`. If the claim has been assessed, read the verdict before reading the source.
4. **Read the Wikipedia entry for the publisher** (if one exists): Look at the description, ownership, and any "criticism" or "controversies" section. Do not use Wikipedia as a research source — use it only to quickly assess reputation.

**What a useful lateral reading result looks like**: independent coverage of the publisher's track record, editorial standards, ownership, or funding. A result that only repeats the source's own claims is not useful.

**If no lateral reading results exist**: the source is unestablished. Score Authority at 2 maximum in Step 2 and flag for corroboration.

**Why first**: A convincing-looking but unreliable source can anchor your judgment if you read it first. Lateral reading calibrates your assessment before you invest in the content.

---

## Step 2 — CRAAP Test

Score each dimension 1–5 (1 = poor, 5 = excellent).

### C — Currency
- When was it published or last updated?
- For fast-moving fields (technology, medicine, current events): sources older than 3–5 years require justification
- For slow-moving fields (history, foundational theory): older sources may be appropriate
- Are links and references within the source functional?
- **Score: __ / 5**

### R — Relevance
- Does it directly address the research question?
- Is the scope appropriate — not too broad to be useful, not too narrow to generalize?
- Is the intended audience appropriate (scholarly, professional, general public)?
- Is the source type right for the purpose (primary data, secondary analysis, opinion)?
- **Score: __ / 5**

### A — Authority
- Who is the author? What are their credentials and institutional affiliation?
- Is the author an expert in the specific subject matter of this source (not just a related field)?
- What is the publishing organization — peer-reviewed journal, university press, government agency, news organization, blog, advocacy group?
- Can the author's identity and affiliation be independently verified?
- **Score: __ / 5**

### Ac — Accuracy
- Is every factual claim supported by evidence within the source?
- Are sources cited and verifiable?
- Has the work been reviewed by independent experts before publication?
- Are there factual errors, typos, or signs of hasty production?
- Does the content match what the title and abstract promise?
- **Score: __ / 5**

### P — Purpose
- What is the intent of this source: inform, persuade, sell, entertain, or advocate?
- Is bias stated openly or is it hidden?
- Are multiple perspectives represented, or is only one side presented?
- Who benefits if readers accept this source's claims?
- **Score: __ / 5**

**CRAAP Total: __ / 25**

| Score | Interpretation |
|---|---|
| 21–25 | Highly credible — appropriate for research citation |
| 15–20 | Moderately credible — use with corroboration |
| 9–14 | Low credibility — significant caution; seek stronger sources |
| 0–8 | Not credible for research use |

---

## Step 3 — Bias Assessment

Assess the source's evident perspective independently of its CRAAP score. A source can score high on accuracy and still carry significant bias through selective emphasis.

| Bias level | Description |
|---|---|
| **Neutral** | Multiple perspectives represented; language is even-handed |
| **Slight lean** | Perspective evident but evidence is fairly presented |
| **Moderate bias** | Consistent framing favoring one view; significant omissions |
| **Strong bias** | Advocacy source; evidence selected to support a predetermined conclusion |
| **Propaganda** | Designed to mislead; uses emotional manipulation, misrepresentation, or fabrication |

Note: bias and credibility are separate scores. A peer-reviewed advocacy journal can be highly accurate AND strongly biased.

---

## Step 4 — Source Classification

Classify the source by type, which determines its appropriate use in research:

| Type | Description | Research weight |
|---|---|---|
| Peer-reviewed journal article | Reviewed by independent experts before publication | Full — primary citation for empirical claims |
| Scholarly book (university press) | Reviewed; cites sources; author's credentials established | Full — check date and edition |
| Government / institutional data | Official statistics and reports; methodology usually documented | Full — verify methodology |
| Reputable news organization | Reporters with subject-matter expertise; editorial standards published | Moderate — for events, not technical claims |
| Advocacy organization | Perspective-driven; may cherry-pick evidence | Background only — always corroborate |
| Trade press | Industry-funded; useful for industry data; perspective evident | Low-moderate — note funding |
| Personal blog / social media | No editorial review; variable expertise | Lowest — treat as anecdote; verify independently |
| Preprint | Not yet peer-reviewed; results may change | Flag clearly; do not present as established |
| AI-generated content | No primary source access; may hallucinate citations | Do not cite unless verified against primary sources |

---

## Step 5 — APA 7 / MLA 9 Citability Check

Determine whether the source can be properly cited in a research document:

**APA 7 (webpage/website) — can it be cited?**
- [ ] Author (individual, group, or title-first) is identifiable
- [ ] Date (or n.d.) is available
- [ ] Title is retrievable
- [ ] URL is stable or DOI is present
→ If all checked: citable in APA 7

**MLA 9 (electronic source) — can it be cited?**
- [ ] Author or title-first entry is possible
- [ ] Container (site name) is identifiable and can be italicized
- [ ] Publication date or access date is available
- [ ] URL or DOI is present
→ If all checked: citable in MLA 9

If a source cannot be cited in either standard, it cannot be used as a research source regardless of its content.

---

## Step 6 — Output

```
Source:           [Title, Author, Publication, Date, URL/DOI]
Lateral reading:  [What other sources say about this publisher/author]
CRAAP scores:     C: __ R: __ A: __ Ac: __ P: __ | Total: __ / 25
Bias rating:      [Level + 1-sentence justification]
Classification:   [Source type]
APA 7 citable:    Yes / No / Partially (explain)
MLA 9 citable:    Yes / No / Partially (explain)
Recommendation:   Use freely | Use with corroboration | Do not use for research
Rationale:        [1 sentence]
```

---

## Red Flags Checklist

Flag any source that shows these signs:

- [ ] Author name cannot be independently verified
- [ ] No date of publication or last update
- [ ] No citations for specific factual claims
- [ ] Emotionally charged, all-caps, or sensationalist headline
- [ ] URL mimics a credible outlet (e.g., ABCnews.com.co)
- [ ] "About" page is missing, vague, or defensive
- [ ] Claims directly contradict scientific consensus without peer-reviewed evidence
- [ ] Excessive advertising, pop-ups, or sponsored content mixed with editorial
- [ ] No editorial policy or contact information published
- [ ] Sources cited are circular (the page cites itself or a sister site)

Three or more red flags: recommend Do not use for research.

---

## Troubleshooting

- If the source has no identifiable author, score Authority at 1 automatically.
- For sources older than 10 years in rapidly evolving fields (AI, medicine, policy), score Currency at 1–2 unless the work is a foundational or canonical text.
- A high CRAAP score does not override a Strong Bias or Propaganda rating — both must appear in the output.
- Social media posts cannot be `Use freely` regardless of CRAAP score — they are always `Use with corroboration` at best.
