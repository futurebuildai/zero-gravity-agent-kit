# Dual-Agent Spec Kit

A reusable template for structured software development using the **Dual-Agent (Antigravity + Claude Code)** workflow.

## Overview

This kit defines a two-phase development process:

1. **Antigravity (Planning)** — An AI agent acts as Product Manager, UX Designer, and System Architect. It generates 5 comprehensive blueprint documents that fully specify what needs to be built.
2. **Claude Code (Execution)** — An AI agent acts as Execution Engineer and Zero-Trust Auditor. It implements code strictly to the blueprints, auditing each step for security, architecture, and stability.

## How to Use

1. **Copy the `.agents/` folder** into any new project repository.
2. **Run the Antigravity workflow** (`antigravity_init.md`) to generate blueprints for your feature or product. The 5 core blueprints will be placed in `.agents/handoff/`:
   - `PRD.md` — Product requirements and scope
   - `UI_UX_DESIGN.md` — Design tokens, mockups, and aesthetic vision
   - `ARCHITECTURE.md` — Interfaces, schemas, and tech stack specs
   - `TESTING_STRATEGY.md` — Zero-trust audit criteria
   - `EXECUTION_PLAN.md` — Step-by-step implementation checklist
3. **Hand off to Claude Code**, which will ingest the blueprints, summarize its understanding, wait for your approval, and then execute the plan step-by-step with zero-trust auditing after each step.

## Directory Structure

```
.agents/
├── claude_instructions.md          # Claude Code execution protocol
├── orchestrator_instructions.md    # Antigravity orchestrator role
├── workflows/
│   └── antigravity_init.md         # Blueprint generation workflow
├── skills/                         # Add reusable agent skills here
└── handoff/                        # Blueprints go here (generated per project)
```

## Principles

- **Specification first** — No code is written until blueprints are complete and approved.
- **Zero-trust auditing** — Every implementation step is audited for security, architecture adherence, and stability.
- **No unauthorized deviations** — Claude Code follows the architecture exactly; changes require user approval.
