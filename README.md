# Research Skills

Agent skills for rigorous, citation-backed research. Follows the [agentskills.io](https://agentskills.io) open standard.

These skills teach an LLM to research and validate the way human researchers do — iteratively, with sourced evidence, and with explicit checks against bias. The citation foundation is grounded in two authoritative references:

- **APA 7th Edition** — [Webpage & Website References](https://apastyle.apa.org/style-grammar-guidelines/references/examples/webpage-website-references) (APA Style, American Psychological Association)
- **MLA 9th Edition** — [Works Cited: Electronic Sources](https://www.owl.purdue.edu/owl/research_and_citation/mla_style/mla_formatting_and_style_guide/mla_works_cited_electronic_sources.html) (Purdue OWL)

## Skills

| Skill | What it teaches |
|---|---|
| [`cited-source-parser`](./skills/cited-source-parser/) | Extract, structure, and validate citations — APA 7 and MLA 9 for web/electronic sources |
| [`iterative-validation`](./skills/iterative-validation/) | Validate research claims across five successive rounds, producing a scored confidence assessment |
| [`peer-review`](./skills/peer-review/) | Conduct structured, unbiased peer review with mandatory bias self-audit |
| [`source-credibility`](./skills/source-credibility/) | Assess any source using CRAAP, SIFT, lateral reading, and bias rating |
| [`research-synthesis`](./skills/research-synthesis/) | Synthesize multiple sources thematically with full attribution and integrity check |

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
