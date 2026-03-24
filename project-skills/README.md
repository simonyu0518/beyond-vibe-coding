# Beyond Vibe Coding — Project Skills

Six AI Agent Skills for AI-Native software engineering, designed to work with any tool that supports role-based configuration (Cursor Agent Skills, Claude Code, Gemini Gems, ChatGPT Codex, Windsurf, etc.).

## Architecture

Two independent toolkits that form a closed loop:

```
┌─────────────────────────────────────────────────────────┐
│                  BROWNFIELD TOOLKIT                     │
│            (Understand before you act)                  │
│                                                         │
│  ┌──────────────────┐    ┌──────────────────┐          │
│  │    Codebase       │───▶│     Logic        │          │
│  │   Cartographer    │    │    Decoder       │          │
│  │   (The Mapper)    │    │  (The Translator)│          │
│  └──────────────────┘    └────────┬─────────┘          │
│                                    │                    │
│                          Refactoring Recommendations    │
└────────────────────────────────────┼────────────────────┘
                                     │
                                     ▼
┌─────────────────────────────────────────────────────────┐
│                  GREENFIELD PIPELINE                    │
│            (Build with quality gates)                   │
│                                                         │
│  ┌─────────┐   ┌──────────┐   ┌─────────┐   ┌───────┐│
│  │Requirem.│──▶│  System   │──▶│ Implem. │──▶│Verif. ││
│  │ Analyst │   │ Architect │   │  Coder  │   │ Audit ││
│  │(Gate-   │   │(Designer) │   │(Builder)│   │(Bad   ││
│  │ keeper) │   │           │   │         │   │ Cop)  ││
│  └─────────┘   └──────────┘   └─────────┘   └───────┘│
│       ▲              ▲              ▲            │      │
│       │              │              │            │      │
│   Checkpoint A   Checkpoint B  Checkpoint C  Checkpoint D
│   (Spec Review)  (Arch Review) (Code Review) (Verification)
│                                                  │      │
└──────────────────────────────────────────────────┼──────┘
                                                   │
                                          Re-scan  │
                                     ┌─────────────┘
                                     ▼
                              Cartographer
                            (Verify integration)
```

## Quick Start

### For Cursor / Claude Code
Copy the `project-skills/` directory into your project:

```bash
cp -r project-skills/ .cursor/skills/
```

### For other tools
Each `SKILL.md` follows the [Agent Skills Open Specification](https://agentskills.io). Adapt the YAML frontmatter and Markdown body to your tool's configuration format.

## Agent Inventory

### Greenfield Pipeline (Build from scratch)

| # | Agent | Role | Trigger | Output |
|---|-------|------|---------|--------|
| 1 | **Requirements Analyst** | The Gatekeeper | New feature request, vague requirement | PRD + Gherkin AC |
| 2 | **System Architect** | The Designer | Approved PRD ready for design | PES + Mermaid diagrams + API contracts |
| 3 | **Implementation Coder** | The Builder | Approved PES ready for coding | Tested code (TDD-first) |
| 4 | **Verification Audit** | The Bad Cop | Code ready for final review | Verification Report + supplementary tests |

### Brownfield Toolkit (Understand existing code)

| # | Agent | Role | Trigger | Output |
|---|-------|------|---------|--------|
| 5 | **Codebase Cartographer** | The Mapper | Just cloned a repo, inherited a project | Codebase Map + dependency graph |
| 6 | **Logic Decoder** | The Translator | Need to understand specific module/logic | Analysis Report + refactoring recommendations |

## Human-in-the-Loop Checkpoints

The human is the **Orchestrator** — they don't write code, but they make every critical decision:

- **Checkpoint A (Spec Review):** Approve or revise PRD before architecture begins
- **Checkpoint B (Architecture Review):** Approve or revise PES before coding begins
- **Checkpoint C (Code Review):** Review implementation before verification
- **Checkpoint D (Verification Review):** Decide which findings to fix vs. accept as known risks

## Related

This repository accompanies the **[Beyond Vibe Coding](https://medium.com/@simonyu0518)** article series:

1. **Role Migration** — Why engineers must move upstream or downstream
2. **Methodology** — AI-Native Engineering Workflow with HITL
3. **Hands-On** — Greenfield pipeline + flash-sale system live simulation
4. **Archaeology** — Brownfield archaeology + legacy code reverse engineering
5. **Series Recap** — Your AI-Native toolkit and what's next

## License

MIT
