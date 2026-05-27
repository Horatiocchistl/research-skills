---
name: cited-source-parser
description: Parse, extract, validate, and structure citations from any research document. Use this skill when asked to identify or extract citations from text; validate whether references are correctly formatted in APA 7th or MLA 9th edition for web and electronic sources; convert raw citations into structured records; flag incomplete, malformed, or unverifiable sources; check that in-text citations match reference list entries; or reformat a citation from one style to the correct standard.
license: MIT
metadata:
  author: Ronald Dean Strawbridge
  version: 1.0.0
  category: research
  tags: [citations, APA, MLA, parsing, validation, web-sources, electronic-sources]
---

# Cited Source Parser

Extract, validate, and structure citations from any research text — with specific authority from APA 7th edition (webpage/website references) and MLA 9th edition (electronic sources).

## Authoritative Sources

All rules in this skill derive from:
- **APA 7th**: https://apastyle.apa.org/style-grammar-guidelines/references/examples/webpage-website-references
- **MLA 9th**: https://www.owl.purdue.edu/owl/research_and_citation/mla_style/mla_formatting_and_style_guide/mla_works_cited_electronic_sources.html

When rules conflict with memory or intuition, defer to these two sources. Full format specifications, field-by-field rules, and worked examples for every case are in the reference files — consult them before making any validation decision:

- **[`references/apa7-web-format.md`](./references/apa7-web-format.md)** — APA 7th edition: all webpage/website cases, field rules, validation checklist
- **[`references/mla9-electronic-format.md`](./references/mla9-electronic-format.md)** — MLA 9th edition: all electronic source cases, container logic, DOI/URL rules, date formatting

## Instructions

### Step 0 — Assess Citation Presence

Before parsing, determine whether the document contains citations at all.

- **Citations present**: in-text markers (Author, Year) or (Author page) are visible, OR a reference list / works cited section exists at the end. Proceed to Step 1.
- **No citations found**: the document makes factual claims but provides no sourcing. Do not proceed with parsing — there is nothing to parse. Instead:
  1. Identify every factual claim in the document (any assertion that can be verified or falsified).
  2. Output a numbered list of uncited claims.
  3. Flag the document: *"No citations found. The following claims require sourcing before this document can be validated."*
  4. Use the `process-web-research` skill to locate and attach sources for each flagged claim.

**Do not silently pass a document with no citations** — absence of citations is itself a finding.

---

### Step 1 — Detect Citation Style

Examine the text and identify the citation format in use. Key signals:

| Style | In-text marker | Reference list signals |
|---|---|---|
| APA 7 | (Author, Year) or (Author, Year, p. X) | Author, A. A. (Year). *Title*. Site. URL |
| MLA 9 | (Author page) | Last, First. "Title." *Website*, Date, URL. |
| Mixed | Both patterns present | Note each citation's style separately |
| Unknown | No standard pattern | Flag for manual review |

### Step 2 — Extract Every Citation

Pull every citation from the text — in-text markers AND reference list entries. Do not skip partial or malformed ones; flag them instead. Match in-text citations to their reference list counterparts where possible.

### Step 3 — Structure Each Citation as a Record

Produce one record per citation with these fields:

```
id:          (sequential integer)
raw:         (exact text as found, unchanged)
style:       APA7 | MLA9 | unknown
in_text:     (the in-text marker, if found)
reference:   (the reference list entry, if found)
authors:     [array of names as given]
year:        (4-digit integer, or null)
title:       (work title, string)
site_name:   (website/publication name)
doi:         (DOI string if present, else null)
url:         (URL if present, else null)
access_date: (retrieval/access date if present, else null)
source_type: webpage | social_media | online_news | database_article | video | other
status:      valid | incomplete | unverifiable
notes:       (any flags or anomalies)
```

### Step 4 — Apply APA 7th Edition Rules (Webpages & Websites)

Validate each APA citation using the full rules in **[`references/apa7-web-format.md`](./references/apa7-web-format.md)**.

Quick reference — standard format:
> Author, A. A. (Year, Month Day). *Title of page*. Website Name. URL

Key decision points:
- No date → `(n.d.)` in place of year; still `valid` if all other fields present
- No author → title-first entry; site name stands in
- Author = site name → omit site name field
- Retrieval date → only for pages designed to change over time and not archived
- Social media, YouTube, online news → see the reference file for exact formats

**Required fields for `valid` status (APA7 web):** author or title substitute, date or n.d., italicized title, URL or DOI.
**Mark `incomplete` if:** any required field is absent without a recognized substitute.

### Step 5 — Apply MLA 9th Edition Rules (Electronic Sources)

Validate each MLA citation using the full rules in **[`references/mla9-electronic-format.md`](./references/mla9-electronic-format.md)**.

Quick reference — standard format (webpage with author):
> Last, First. "Title of Page." *Website Name*, Publisher (if different from site), Day Mon. Year, URL.

Key decision points:
- No author → title-first entry
- Two containers (e.g. article in journal found via database) → complete each container block before starting the next; each ends with a period
- DOI always preferred over URL; format as `https://doi.org/10.XXXX/XXXXX`
- Access date → required for pages with no publication date or that change frequently; format: `Accessed Day Mon. Year.` at end of entry
- Social media, YouTube, institutional pages → see the reference file for exact formats

**Required fields for `valid` status (MLA9 electronic):** author or title-first, quoted title of page, italicized container name, date, URL or DOI.

### Step 6 — Cross-Check In-Text vs Reference List

- Flag any in-text citation with no matching reference list entry
- Flag any reference list entry with no corresponding in-text citation
- Flag duplicate entries in the reference list

### Step 7 — Anomaly Detection

Check for:
- **Hallucinated sources**: plausible-sounding citations that cannot be verified (no DOI resolves, URL does not exist, author + title combination returns no results)
- **Mismatched dates**: in-text year differs from reference list year
- **Broken URLs**: URLs that appear malformed or inaccessible
- **Circular citation**: Source A cites Source B which cites Source A

### Step 8 — Output

Produce:

1. **Summary**: total citations found; breakdown by style (APA7 / MLA9 / unknown); breakdown by status (valid / incomplete / unverifiable)
2. **Citation records**: numbered list of structured records (Step 3 format)
3. **Anomaly report**: each flagged issue with citation ID, description, and recommended action
4. **Corrected versions** (optional, if requested): reformat each incomplete citation to the correct APA7 or MLA9 standard

## Examples

**Input (APA):**
> Smith, J. (2023, April 14). *How misinformation spreads online*. The Media Lab. https://themedialab.org/misinformation

**Output record:**
```
id: 1
style: APA7
authors: [Smith, J.]
year: 2023
title: How misinformation spreads online
site_name: The Media Lab
url: https://themedialab.org/misinformation
source_type: webpage
status: valid
```

---

**Input (MLA):**
> "Climate Change Facts." *NASA*, NASA, 12 Mar. 2024, climate.nasa.gov/evidence/.

**Output record:**
```
id: 2
style: MLA9
authors: [] (no author — title-first entry)
title: Climate Change Facts
site_name: NASA
publisher: NASA
year: 2024
url: climate.nasa.gov/evidence/
source_type: webpage
status: valid
notes: No author; title-first format correctly applied.
```

## Troubleshooting

- If a DOI is present, treat it as the authoritative identifier and use it to verify the source exists before marking `valid`.
- For Chicago or Vancouver citations found in a mixed document, note the style but apply no validation rules — this skill covers APA7 and MLA9 only.
- If a citation is entirely in a language other than English, note the language and parse what fields are identifiable; do not guess at field values.
