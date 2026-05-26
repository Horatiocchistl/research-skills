# Validation Framework Reference

## Evidence Hierarchy (strongest → weakest)

### Scientific / Medical Claims
1. Systematic reviews and meta-analyses of RCTs (e.g. Cochrane Reviews)
2. Randomized controlled trials (RCTs)
3. Prospective cohort studies
4. Retrospective cohort / case-control studies
5. Cross-sectional studies
6. Case reports / case series
7. Expert opinion / editorial
8. Anecdote / testimonial

### Social Science & Humanities Claims
1. Peer-reviewed empirical study (large n, validated instrument)
2. Peer-reviewed qualitative study (robust methodology)
3. Government or institutional report with transparent methodology
4. Scholarly book (university press, peer-reviewed)
5. Reputable journalism with named primary sources
6. Expert commentary
7. Personal account

### Legal / Policy Claims
1. Primary legal text (statute, regulation, court ruling)
2. Official government publication
3. Legal commentary in peer-reviewed law journal
4. Reputable legal journalism

---

## Common Validation Errors

| Error | Description | Detection method |
|---|---|---|
| **Cherry-picking** | Citing only supporting studies; ignoring contradicting ones | Search specifically for contradicting evidence |
| **Overgeneralization** | Applying narrow findings to broad populations | Check study's sample vs claim's scope |
| **Correlation as causation** | Treating co-occurrence as proof of causal relationship | Ask: was a causal mechanism demonstrated? |
| **Outdated data** | Citing studies superseded or retracted | Check publication date; search for retractions |
| **Misrepresentation** | Claim does not match what the cited source actually says | Return to original source and read the cited section |
| **Circular citation** | A cites B cites A — no independent origin | Trace every citation back to primary data |
| **Appeal to authority** | Using credentials as a substitute for evidence | Ask: what evidence does the authority cite? |
| **Excluded middle** | Treating a contested question as having only two options | Check whether the field recognizes more positions |
| **Moving the goalposts** | Redefining terms mid-argument | Check whether key terms are used consistently |

---

## Corroboration Thresholds by Claim Type

| Claim type | Sources required for Confirmed |
|---|---|
| Scientific fact (established) | 2+ peer-reviewed studies |
| Statistical figure | Original dataset + 1 independent aggregator |
| Historical event | 2 scholarly sources or 1 primary document |
| Legal / policy fact | Primary legal text + 1 legal commentary |
| Current event | 2 reputable news organizations with independent reporting |
| Expert consensus claim | Evidence of formal consensus body position (e.g. IPCC, APA, CDC) |

---

## Source Independence Test

Two sources are **independent** if:
- They were produced by different authors and institutions
- Neither cites the other as its primary basis
- They used different data sets or methodologies
- They were not funded by the same organization

Two sources are **not independent** if:
- One is a press release about the other
- Both cite the same single underlying study
- Both authors share an institution or funding source

---

## Bias Detection Prompts (Round 5)

Ask these questions about the document under review:

1. Which side of the debate is given more space and better evidence?
2. What would a credible critic of this document's thesis say, and is that voice present?
3. Are the sources geographically and institutionally diverse?
4. Is the language neutral, or does it frame the evidence emotionally?
5. Are the limitations of the evidence stated, or buried, or absent?
6. Does the conclusion claim more certainty than the evidence warrants?
