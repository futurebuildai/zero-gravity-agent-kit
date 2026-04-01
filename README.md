# Zero-Gravity Agent Kit

An autonomous product-to-engineering pipeline powered by two AI agents. Describe your vision in a paragraph — get production-ready, L8-quality specs, architecture, and execution plans.

## How It Works

Write 1-2 paragraphs describing your feature or product idea. The **Antigravity** agent autonomously runs an 11-stage pipeline — using heavy browser research to ground every decision in real-world evidence — and produces 20+ specification artifacts. Then **Claude Code** executes the plan step-by-step with zero-trust auditing.

### The Pipeline

```
You write a vision paragraph
        ↓
┌─ DISCOVERY ────────────────────────────────┐
│ 00 Vision Intake    → Parse & plan research │
│ 01 Deep Research    → 20-50+ browser searches│
│ 02 User Research    → Personas, JTBD, journeys│
│ 03 Solution Design  → Ideate, evaluate, decide│
│ 04 Scope & Priority → MVP, metrics, roadmap   │
│    ⏸️  APPROVAL GATE                          │
├─ DESIGN ───────────────────────────────────┤
│ 05 Design System    → IA, tokens, components  │
├─ SPECIFICATION ────────────────────────────┤
│ 06 Product Spec     → L8-quality PRD          │
│ 07 Architecture     → System design, APIs     │
│    ⏸️  APPROVAL GATE                          │
│ 08 Testing Strategy → Zero-trust test plan    │
│ 09 Execution Plan   → Phased implementation   │
│ 10 Spec Review      → Final quality audit     │
│    ⏸️  FINAL APPROVAL                         │
└────────────────────────────────────────────┘
        ↓
Claude Code executes with zero-trust auditing
```

## Quick Start

1. Copy `.agents/` and `.claude/` into your project repository
2. Fill in `.agents/TECH_STACK.md` with your technology choices
3. Open a session in the **Antigravity** IDE agent and start the pipeline:

```
/start I want to build a real-time collaborative whiteboard app
for remote design teams. It should support infinite canvas, sticky notes,
freehand drawing, and live cursors. Think Figma meets Miro but focused
on async design critiques with threaded comments on any canvas element.
```

4. Antigravity runs stages 00-10 autonomously, pausing at approval gates for your review
5. When specs are ready, switch to a **Claude Code** session for execution:

```
/execute
```

### Slash Commands

| Command | Used In | What it does |
|---------|---------|-------------|
| `/start [vision]` | Antigravity | Kicks off the 11-stage planning pipeline with your vision paragraph |
| `/execute` | Claude Code | Ingests all blueprints and begins implementation with zero-trust auditing |

## Directory Structure

```
.claude/
├── skills/
│   ├── start/SKILL.md                     # /start slash command (used in Antigravity agent)
│   └── execute/SKILL.md                   # /execute slash command (used in Claude Code agent)
│
.agents/
├── TECH_STACK.md                              # Your tech stack config
├── orchestrator_instructions.md               # Antigravity pipeline controller
├── claude_instructions.md                     # Claude Code execution protocol
│
├── workflows/
│   ├── antigravity/                           # Planning agent (15 workflows)
│   │   ├── 00_vision_intake.md                # Parse vision → research agenda
│   │   ├── 01_deep_research.md                # Heavy browser research
│   │   ├── 02_user_research.md                # Personas, JTBD, journeys
│   │   ├── 03_solution_design.md              # Ideation, feasibility, build-vs-buy
│   │   ├── 04_scope_and_prioritization.md     # MVP scope, metrics
│   │   ├── 05_design_system.md                # IA, design tokens, components
│   │   ├── 06_product_spec.md                 # PRD with acceptance criteria
│   │   ├── 07_architecture_spec.md            # System design, API contracts
│   │   ├── 08_testing_strategy.md             # Zero-trust test plan
│   │   ├── 09_execution_plan.md               # Phased implementation plan
│   │   ├── 10_spec_review.md                  # Final quality audit
│   │   ├── feature_iteration.md               # Post-v1 feature deltas
│   │   ├── bug_triage.md                      # Bug → fix specification
│   │   ├── refactor_spec.md                   # Refactoring specification
│   │   └── post_mortem.md                     # Incident post-mortem
│   │
│   └── claude_code/                           # Execution agent (6 workflows)
│       ├── scaffold_project.md                # Project bootstrapping
│       ├── tdd_cycle.md                       # Test-driven development
│       ├── migration_execute.md               # Safe database migrations
│       ├── ci_cd_setup.md                     # Pipeline configuration
│       ├── dependency_audit.md                # Dependency maintenance
│       └── release_cut.md                     # Release preparation
│
├── skills/
│   ├── antigravity/                           # Planning skills (22 skills)
│   │   ├── browser_research.md                # Web research protocol
│   │   ├── competitive_teardown.md            # Competitor deep-dive
│   │   ├── opportunity_scoring.md             # JTBD scoring algorithm
│   │   ├── feature_prioritization.md          # RICE/ICE/Kano/MoSCoW
│   │   ├── assumption_mapping.md              # Risk-rated assumptions
│   │   ├── user_story_decomposition.md        # Epic → stories
│   │   ├── risk_assessment.md                 # Likelihood × impact
│   │   ├── tradeoff_analysis.md               # Decision matrices
│   │   ├── impact_estimation.md               # Fermi estimation
│   │   ├── experiment_design.md               # A/B & validation tests
│   │   ├── dependency_mapping.md              # Critical path analysis
│   │   ├── api_contract_design.md             # OpenAPI/protobuf design
│   │   ├── database_design.md                 # Schema & ERD
│   │   ├── data_model_design.md               # DDD modeling
│   │   ├── security_threat_model.md           # STRIDE analysis
│   │   ├── performance_budget.md              # Latency & bundle budgets
│   │   ├── accessibility_spec.md              # WCAG compliance
│   │   ├── error_taxonomy.md                  # Error code registry
│   │   ├── state_management_design.md         # State architecture
│   │   ├── component_library_spec.md          # UI component catalog
│   │   ├── deployment_topology.md             # Infrastructure spec
│   │   └── migration_plan.md                  # Migration planning
│   │
│   └── claude_code/                           # Execution skills (8 skills)
│       ├── code_review_self_check.md          # Self-review checklist
│       ├── performance_audit.md               # Performance measurement
│       ├── accessibility_audit.md             # A11y verification
│       ├── security_audit.md                  # Security scanning
│       ├── lint_format_fix.md                 # Code style enforcement
│       ├── test_coverage_report.md            # Coverage analysis
│       ├── documentation_sync.md              # Doc verification
│       └── git_hygiene.md                     # Commit practices
│
└── handoff/                                   # Artifacts generated per project
    └── .gitkeep
```

## Two Agents, Clear Roles

| | Antigravity (Planning) | Claude Code (Execution) |
|---|---|---|
| **Role** | PM, UX Researcher, System Architect | Execution Engineer, Zero-Trust Auditor |
| **Produces** | Specs, designs, architecture, plans | Working code, tests, deployments |
| **Uses browser** | Heavily (research, competitive analysis) | As needed (docs, error lookup) |
| **Writes code** | Never (pseudocode for concepts only) | Always (strictly to spec) |
| **Key principle** | Be opinionated, leave no ambiguity | Follow the spec exactly, escalate ambiguity |

## Lifecycle Support

After v1 ships, the kit supports ongoing development:

- **New features** → `feature_iteration.md` produces delta specs against existing blueprints
- **Bug fixes** → `bug_triage.md` produces surgical fix specifications
- **Refactoring** → `refactor_spec.md` documents current → target with behavior preservation
- **Incidents** → `post_mortem.md` produces root cause analysis + prevention specs

## Tech Stack Agnostic

The kit is parameterized via `TECH_STACK.md`. Fill in your technology choices once — all workflows and skills reference it automatically. Works with any stack: Go, Python, Rust, TypeScript, React, Lit, Flutter, PostgreSQL, MongoDB, etc.

## Principles

- **Research-grounded** — Every decision backed by browser research, not training data alone
- **Evidence-traced** — Every requirement traces back to user research, competitive analysis, or technical evidence
- **Spec-first** — No code until specs are complete and approved
- **Zero-trust auditing** — Every implementation step is audited across security, architecture, stability, performance, and accessibility
- **No unauthorized deviations** — Architecture changes require user approval; ambiguity triggers escalation, not improvisation
