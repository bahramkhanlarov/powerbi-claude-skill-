# powerbi-skill

A skill for agentic Power BI semantic model development — TMDL authoring, PBIP project structure, DAX quality rules, and agentic workflows.

> Integrated with knowledge from [data-goblin/power-bi-agentic-development](https://github.com/data-goblin/power-bi-agentic-development).

---

## Visual Use Cases

👉 **[View full visual use case page](https://bahramkhanlarov.github.io/powerbi-claude-skill-/)** — interactive HTML with star schema, workflow phases, TMDL rules, and summarizeBy reference.

---

## Agentic Workflow

```mermaid
flowchart LR
    A["🔍 Discovery\nGlob + Read\nall .tmdl files"] --> B["📋 Plan\nList every file\nto change\n⏸ Wait for approval"]
    B --> C["⚙️ Execute\nWrite files\nin parallel"]
    C --> D["✅ Verify\nRe-read · Check refs\nValidate DAX\nRun pbip-validator"]

    style A fill:#0f3460,stroke:#F2C811,color:#e0e0e0
    style B fill:#0f3460,stroke:#F2C811,color:#e0e0e0
    style C fill:#0f3460,stroke:#F2C811,color:#e0e0e0
    style D fill:#0f3460,stroke:#F2C811,color:#e0e0e0
```

---

## PBIP Project Structure

```mermaid
graph TD
    ROOT["📁 MyProject/"]
    ROOT --> PBIP["📄 MyProject.pbip"]
    ROOT --> SM["📁 MyProject.SemanticModel/"]
    ROOT --> RPT["📁 MyProject.Report/"]

    SM --> DEF["📁 definition/"]
    DEF --> MODEL["model.tmdl"]
    DEF --> REL["relationships.tmdl"]
    DEF --> TABLES["📁 tables/\n Sales.tmdl · Customer.tmdl · Date.tmdl"]
    DEF --> ROLES["📁 roles/"]
    DEF --> CULTURES["📁 cultures/"]
    SM --> PLATFORM1["📄 .platform"]

    RPT --> PBIR["📄 definition.pbir"]
    RPT --> RDEF["📁 definition/\n pages/ · visuals/"]
    RPT --> STATIC["📁 StaticResources/\n themes · images"]
    RPT --> PLATFORM2["📄 .platform"]

    style ROOT fill:#1a1a2e,stroke:#F2C811,color:#F2C811
    style SM fill:#16213e,stroke:#2980b9,color:#5dade2
    style RPT fill:#16213e,stroke:#2980b9,color:#5dade2
    style DEF fill:#0f3460,stroke:#444,color:#e0e0e0
    style TABLES fill:#0f3460,stroke:#444,color:#e0e0e0
    style RDEF fill:#0f3460,stroke:#444,color:#e0e0e0
```

---

## Star Schema Pattern

```mermaid
erDiagram
    SALES_FACT {
        int _DateKey FK
        int _CustomerKey FK
        int _ProductKey FK
        decimal Revenue
        int Quantity
        decimal Cost
    }
    DATE_DIM {
        int DateKey PK
        date Date
        int Year
        string Quarter
        string MonthName
    }
    CUSTOMER_DIM {
        int CustomerKey PK
        string CustomerName
        string Region
        string Segment
    }
    PRODUCT_DIM {
        int ProductKey PK
        string ProductName
        string Category
        string SubCategory
    }
    MEASURES_TABLE {
        measure TotalRevenue
        measure YTDRevenue
        measure GrossMarginPct
        measure CustomerCount
    }

    DATE_DIM     ||--o{ SALES_FACT : "DateKey"
    CUSTOMER_DIM ||--o{ SALES_FACT : "CustomerKey"
    PRODUCT_DIM  ||--o{ SALES_FACT : "ProductKey"
```

---

## What's Included

| Area | Details |
|------|---------|
| **TMDL authoring** | `///` descriptions, tab indentation depths, name quoting, all constructs |
| **PBIP structure** | Full file layout, thick vs thin reports, forking, rename cascade |
| **DAX quality** | `DIVIDE()`, `SELECTEDVALUE()`, explicit `ALL()`, time intelligence |
| **Best practices** | Star schema, naming conventions, `summarizeBy` rules, `formatString` patterns |
| **Agentic workflow** | Discovery → Plan → Execute → Verify phases |
| **Bulk operations** | Parallel edits, cascade rename verification with grep patterns |

---

## Installation

```bash
git clone git@github.com:bahramkhanlarov/powerbi-claude-skill-.git
cp powerbi-claude-skill-/SKILL.md ~/.claude/skills/powerbi/SKILL.md
```

---

## Related

- [data-goblin/power-bi-agentic-development](https://github.com/data-goblin/power-bi-agentic-development) — Power BI agentic development skill marketplace
- [Microsoft TMDL overview](https://learn.microsoft.com/en-us/analysis-services/tmdl/tmdl-overview)
- [Microsoft PBIP overview](https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-overview)
