# Research Skills

Agent skills for rigorous, citation-backed research. Follows the [agentskills.io](https://agentskills.io) open standard.

These skills teach an LLM to research and validate the way human researchers do — iteratively, with sourced evidence, and with explicit checks against bias. The citation foundation is grounded in two authoritative references:

- **APA 7th Edition** — [Webpage & Website References](https://apastyle.apa.org/style-grammar-guidelines/references/examples/webpage-website-references) (APA Style, American Psychological Association)
- **MLA 9th Edition** — [Works Cited: Electronic Sources](https://www.owl.purdue.edu/owl/research_and_citation/mla_style/mla_formatting_and_style_guide/mla_works_cited_electronic_sources.html) (Purdue OWL)

## Research Workflow

These skills are designed to run in sequence. Start at the top.

1. [`plan-the-support`](./skills/plan-the-support/) — Define objectives, select source types, set up workspace, formulate keywords, establish a timebox. **Run first. Do not search without a confirmed plan.**
2. [`research-note-taking`](./skills/research-note-taking/) — Initialize the session log. Called by `plan-the-support`. Every source must be logged here at retrieval before content is extracted.
3. [`process-web-research`](./skills/process-web-research/) — Retrieve and process raw web content. Verify value and authenticity. Feed results into the session log.
4. [`source-credibility`](./skills/source-credibility/) — Assess any source using CRAAP, SIFT, lateral reading, and bias rating before including it.
5. [`research-synthesis`](./skills/research-synthesis/) — Synthesize cited sources thematically with full attribution and integrity check.
6. [`iterative-validation`](./skills/iterative-validation/) — Validate claims across five rounds. Fetches new corroborating sources through step 3.
7. [`peer-review`](./skills/peer-review/) — Structured, unbiased review of a finished research document.
8. [`cited-source-parser`](./skills/cited-source-parser/) — Extract, validate, and fix citations in any existing document. Use when citations are missing or malformed.

Steps 1–3 are the **gathering phase**. Steps 4–8 are the **processing phase**. Do not run processing skills on sources that have not passed through the gathering phase.

## Skills

| Skill | What it teaches |
|---|---|
| [`plan-the-support`](./skills/plan-the-support/) | Define objectives, select sources, build keyword strategy, set timebox — before any search begins |
| [`research-note-taking`](./skills/research-note-taking/) | Initialize and maintain a structured session log — URLs, quotes, citations at point of retrieval |
| [`process-web-research`](./skills/process-web-research/) | Process raw web content — verify authenticity, extract findings, feed the session log |
| [`source-credibility`](./skills/source-credibility/) | Assess any source using CRAAP, SIFT, lateral reading, and bias rating |
| [`research-synthesis`](./skills/research-synthesis/) | Synthesize multiple sources thematically with full attribution and integrity check |
| [`iterative-validation`](./skills/iterative-validation/) | Validate research claims across five successive rounds, producing a scored confidence assessment |
| [`peer-review`](./skills/peer-review/) | Conduct structured, unbiased peer review with mandatory bias self-audit |
| [`cited-source-parser`](./skills/cited-source-parser/) | Extract, structure, and validate citations — APA 7 and MLA 9 for web/electronic sources |

## Standard

Follows the [agentskills.io specification](https://agentskills.io/specification). Each skill:

```
skills/
└── skill-name/
    ├── SKILL.md        # YAML frontmatter + playbook instructions
    └── references/     # Detailed frameworks, format guides, rubrics
```

## Usage

Place skill directories into your agent's skills path:
- **Claude Code**: `~/.claude/skills/`
- **Codex CLI**: `~/.codex/skills/`
- **Gemini CLI**: `~/.gemini/skills/`

## License
MIT
