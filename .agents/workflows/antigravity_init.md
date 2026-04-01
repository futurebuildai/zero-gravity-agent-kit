---
description: Run the Antigravity initialization workflow to act as the primary PM, UX/UI designer, and System Architect.
---

# Antigravity Initialization Workflow

This workflow is designed to generate the blueprint artifacts required for the Dual-Agent Software Development Philosophy. During this phase, Antigravity acts as the thought partner, deep researcher, product manager, project planner, UI/UX designer via Stitch, spec manager, and system architect.

**Goal:** Generate the 5 core blueprints and place them in the `.agents/handoff/` directory for Claude Code to execute against.

## 1. Product Requirements & Scope
Analyze the user's request. Create `.agents/handoff/PRD.md`.
- Detail the high-level user stories.
- Define the exact scope of the minimum viable feature or product.
- Specify non-functional requirements.

## 2. UI/UX Design & Stitching
If the request involves a user interface (e.g., Vite/Lit frontend or Flutter mobile), leverage Stitch. Create `.agents/handoff/UI_UX_DESIGN.md`.
- Define the aesthetic vision, color palettes, and typography.
- Generate UI mockups and design tokens.
- Specify interactive elements and dynamic animations.

## 3. System Architecture & Tech Stack Specs
Create `.agents/handoff/ARCHITECTURE.md`.
- For **Golang:** Define rigorous interfaces, struct definitions, package boundaries, and data flow.
- For **Vanilla Plus TS (Vite + Lit) / Flutter:** Define the component hierarchy, state management flow, and data encapsulation strategies.
- Include any database schemas or API contracts (OpenAPI/gRPC).

## 4. Comprehensive Zero-Trust Testing Strategy
Create `.agents/handoff/TESTING_STRATEGY.md`.
- Outline a comprehensive zero-trust audit strategy covering *every angle*: security (auth, input validation), architecture (strict SOLID adherence, no circular dependencies), type-safety, and edge cases.
- Define what constitutes a successful test before Claude Code can mark a feature as production-ready.

## 5. Execution Plan Generation
Create `.agents/handoff/EXECUTION_PLAN.md`.
- Break down the architecture into a granular, step-by-step checklist of tasks.
- Ensure the steps are ordered by dependency (e.g., scaffolding and DB schema first, then backend API, then UI).

Once these 5 artifacts are placed in `.agents/handoff/`, notify the user that the handoff to Claude Code is ready.
