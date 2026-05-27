---
name: iterative-validation
description: Validate research claims through five successive rounds of cross-checking — mirroring how human researchers and fact-checkers iteratively verify findings before drawing conclusions. Use this skill when asked to fact-check a claim, validate a research assertion, verify whether evidence supports a conclusion, assess whether findings are reproducible across multiple independent sources, audit a document for unsupported or contested claims, or produce a scored confidence assessment and overall document reliability percentage for a body of research.
license: MIT
metadata:
  author: Ronald Dean Strawbridge
  version: 1.0.0
  category: research
  tags: [validation, fact-checking, evidence, rigor, iteration, cross-checking]
---

# Iterative Validation

Validate research claims in successive, independent rounds — the way rigorous human researchers do it before publishing conclusions.

## Why Iteration

A single pass at fact-checking is insufficient. Human researchers iterate because:
- First reads surface obvious problems; later reads catch subtler ones
- Each round examines a different dimension (existence → evidence → consistency → context → bias)
- Iteration produces a confidence level, not a binary true/false
- Each round's findings inform what to probe in the next

This skill runs five rounds in sequence. Do not skip rounds; each depends on the previous.

**Reference:** Evidence hierarchies, corroboration thresholds, source independence tests, and bias detection prompts are in **[`references/validation-framework.md`](./references/validation-framework.md)**. Consult it during Rounds 2 and 3.

---

## Round 1 — Claim Isolation

**Goal:** Know exactly what is being validated before evaluating anything.

1. Read the full document before labeling any claim.
2. Identify every distinct factual claim — any assertion that can be true or false independent of opinion or preference.
3. Exclude pure value judgments ("X is good"), predictions, and hypotheticals unless they are presented as established facts.
4. Assign each claim a unique ID: C1, C2, C3…
5. Note the claim's source: who makes it, and where in the document.

**Output:** A numbered list of claims with IDs, exact text, and source location.

---

## Round 2 — Evidence Inventory

**Goal:** Understand what support the author actually provides.

For each claim, document:
- All evidence the author provides to support it
- The evidence type:

| Type | Description |
|---|---|
| **Primary** | Original data, experiment, direct observation, primary document |
| **Secondary** | Synthesis or analysis of primary sources (meta-analysis, scholarly article) |
| **Tertiary** | Textbook, encyclopedia, review aggregation |
| **Anecdotal** | Single case, personal account, testimonial |
| **None** | Asserted without any cited evidence |

Note whether the cited source actually says what the author claims it says — this is one of the most common research errors.

---

## Round 3 — Independent Corroboration

**Goal:** Find evidence from sources independent of the original author.

For each claim:
1. Derive a search query directly from the claim text — use the key noun phrases and entity names, not the topic generally. Example: for the claim "remote work increases productivity by 13%," search `"remote work" productivity 13% study` not `remote work benefits`. Use `site:edu`, `site:gov`, or `filetype:pdf` operators to bias toward authoritative sources. Run at least two query variants per claim before concluding a search found nothing.
2. Seek corroborating OR contradicting evidence from sources that have no connection to the original author or their institution. Apply the source independence test in `references/validation-framework.md` to every source found.
3. Record for each source found:
   - Source name and publication
   - Year and credibility tier (peer-reviewed / institutional / journalism / other)
   - Stance: **supports** | **contradicts** | **neutral** | **unrelated**
3. Apply thresholds:
   - **Confirmed**: ≥2 independent sources support the claim; no significant contradicting evidence
   - **Plausible**: ≥1 credible independent source supports; no strong contradicting evidence
   - **Contested**: credible sources both support and contradict
   - **Unsupported**: no credible corroborating evidence found after reasonable search
   - **False**: credible evidence directly contradicts the claim

---

## Round 4 — Consistency & Accuracy Check

**Goal:** Catch internal contradictions and source distortion.

1. **Internal consistency**: Do the document's own claims contradict each other? Map any conflicts.
2. **Source accuracy**: Go back to each cited source the author provides. Does the source actually say what the author claims?
   - Look for: misquotation, selective quotation, quote taken out of context, overstated findings
3. **Statistical accuracy**: For any numerical claim, verify:
   - Is the statistic drawn from the correct population?
   - Is the cited study actually the origin, or does it itself cite another source?
   - Is correlation being presented as causation?
4. **Date accuracy**: Are sources current for the claims made? Outdated data presented as current is a form of inaccuracy.

---

## Round 5 — Bias & Completeness Audit

**Goal:** Assess what the document omits as well as what it includes.

1. **Perspective coverage**: Does the document acknowledge significant competing views? List any major perspective on the topic that is absent.
2. **Source diversity**: Are all citations from one institution, one ideological tradition, or one country? Flag homogeneous sourcing.
3. **Cherry-picking**: Are there widely available studies that contradict the document's thesis that are not cited?
4. **Framing**: Does the language used to present evidence load the reader toward a conclusion before the evidence is evaluated?
5. **Omission of limitations**: Does the document acknowledge the limits of its evidence, or does it present preliminary findings as settled fact?

---

## Confidence Scoring

After all five rounds, assign each claim a final confidence rating:

| Rating | Criteria |
|---|---|
| **Confirmed** | ≥2 independent sources; no significant contradiction; source accurately represented |
| **Plausible** | ≥1 credible source; no strong contradiction; no misrepresentation found |
| **Contested** | Credible sources on both sides; disagreement is genuine and unresolved |
| **Unsupported** | No credible corroborating evidence found |
| **False** | Credible evidence directly contradicts the claim |
| **Unverifiable** | Cannot be confirmed or denied with available sources; often a highly specialized technical claim |

---

## Output Format

**Claim-by-claim table:**

| ID | Claim (shortened) | Evidence type | Corroborating sources | Contradicting sources | Round 4 issues | Round 5 issues | Rating |
|---|---|---|---|---|---|---|---|

**Narrative findings:** Write one paragraph for any claim rated Contested, Unsupported, False, or Unverifiable explaining the specific evidence gap or conflict.

**Overall document reliability score:**  
`(Confirmed + Plausible claims) ÷ total claims = X%`  
Interpret: 85–100% reliable | 60–84% use with caution | below 60% do not cite without independent verification

**Bias summary:** One paragraph on Round 5 findings — what perspectives are missing and what the omission pattern suggests.

---

## Troubleshooting

- If a claim is highly technical (specific lab result, proprietary dataset), mark `Unverifiable` and note what domain expertise would be needed to verify it.
- Statistical claims: always check whether the cited study's own methodology supports the conclusion being drawn from it.
- For legal or policy claims, the primary source (statute text, court ruling, official policy document) overrides any secondary commentary.
