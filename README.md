# powerbi-skill

A skill for agentic Power BI semantic model development — TMDL authoring, PBIP project structure, DAX quality rules, and agentic workflows.

> Integrated with knowledge from [data-goblin/power-bi-agentic-development](https://github.com/data-goblin/power-bi-agentic-development).

## What's included

- **TMDL authoring** — tab-based indentation rules, `///` description annotations, name quoting, all TMDL constructs (measures, columns, roles, calculation groups, date tables, hierarchies, partitions)
- **PBIP project structure** — full file layout, thick vs thin reports, forking, cascade rename verification
- **DAX quality rules** — DIVIDE, SELECTEDVALUE, time intelligence patterns
- **Modeling best practices** — star schema, naming conventions, `summarizeBy` rules, `formatString` patterns, `PBI_FormatHint` guidance
- **Agentic workflows** — discovery → plan → execute → verify phases
- **Bulk operations** — parallel edits, rename cascades, post-rename grep verification

## Installation

```bash
git clone git@github.com:bahramkhanlarov/powerbi-claude-skill-.git
cp powerbi-claude-skill-/SKILL.md ~/.claude/skills/powerbi/SKILL.md
```

## Skill file

The skill is defined in [`SKILL.md`](SKILL.md).

## Related

- [data-goblin/power-bi-agentic-development](https://github.com/data-goblin/power-bi-agentic-development) — marketplace of Power BI agentic development skills (Tabular Editor, PBIR, Deneb, R/Python visuals)
- [Microsoft TMDL overview](https://learn.microsoft.com/en-us/analysis-services/tmdl/tmdl-overview)
- [Microsoft PBIP overview](https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-overview)
