---
name: protocol-driven-build
description: Use a stage-gated, protocol-first workflow for product building. Prioritize boundary, state, memory, effects, API, route, risk, env, verification, and traceability in that order. Do not start implementation until required stage artifacts are confirmed.
---

This skill is for protocol-driven product building in AI-native workflows.

It is not a UI-first skill.

It is a full-stack planning and execution skill that forces the assistant to define machine-readable constraints before implementation.

Use this skill when:

- the user wants a reusable product workflow
- the user wants templates that constrain AI before coding
- the project needs staged clarification instead of one giant PRD
- the task involves product logic, data, API, route, runtime, or environment boundaries

Do not start by discussing visual style unless the user explicitly asks for it or the current stage requires UI confirmation.

## Mandatory Input Strategy

The assistant must begin from existing project inputs whenever possible.

Before asking the user to fill anything from scratch, first scan for:

- PRD and product docs
- ideas and scoping docs
- developer handoff docs
- design specs that contain product behavior
- existing code that already implements part of the feature

If such inputs exist, the assistant must:

1. extract relevant facts
2. normalize them
3. generate a Stage 0 or Stage 1 draft
4. ask the user to confirm or correct the draft

Do not default to blank templates when project documents already exist.

## Core Principle

The assistant must guide the user through staged constraint definition.

The assistant must not dump every template at once.

The assistant must unlock only the current stage and the next immediate question set.

The assistant must prefer:

- `extract -> draft -> confirm`

over:

- `blank template -> ask user to fill`

## Mandatory Build Order

Always follow this order unless the user explicitly overrides it:

0. PRD Intake / Input Extraction
1. Boundary / Intent + Minimum Acceptance
2. State
3. Memory / Data
4. Effects / Actions
5. API / Persistence
6. Route / Screen Contract
7. Risk / Trust / NFR
8. Env / Integration
9. Verification Matrix
10. Traceability
11. Audit / Diff

Read `workflow.md` before using this skill.

## Execution Rules

1. First identify the current stage.
2. First identify the scope level:
   - `app-level`
   - `feature-level`
3. Only ask for or generate the templates required by that stage and scope level.
4. Before implementation, confirm that required artifacts for the current stage are filled.
5. If a later-stage topic appears too early, acknowledge it but defer detailed definition until its stage.
6. If code already exists, distinguish between:
   - `spec-first`: creating rules before implementation
   - `reverse-spec`: extracting the current behavior into a spec
   - `hybrid`: part existing, part planned forward
7. Always state which mode is active.

## Scope Levels

The workflow has two levels:

- `app-level`: product-wide boundary, naming, platform path, top-level user flow
- `feature-level`: one concrete feature, protocol, screen cluster, or data contract

The assistant should usually:

1. confirm `app-level Stage 0`
2. confirm `app-level Stage 1`
3. then open the highest-priority `feature-level Stage 0/1`

Do not jump straight into low-level feature specs if the app-level boundary is still unstable.

## Hard Gates

Do not begin business-logic implementation before these are confirmed:

- Boundary / Intent
- State
- Memory / Data
- Effects / Actions
- Minimum Acceptance

Do not begin real backend or persistence integration before these are confirmed:

- API / Persistence
- Risk / Trust / NFR

Do not begin real deployment or environment setup before these are confirmed:

- Env / Integration
- Verification Matrix

Do not hand off a complex feature as "ready" before these are confirmed:

- Traceability

## Downstream Closure

This skill does not own visual concretization.

Its default closure is:

1. confirm protocol stages through the last stage actually needed for UI work
2. freeze the route/screen contract and major interaction rules
3. hand the work to `protocol-ui-fastlane`
4. after UI is generated or implemented, return here for:
   - `Stage 9` Verification / Traceability alignment when needed
   - `Stage 10` Audit / Diff after real implementation exists

Default boundary:

- `protocol-driven-build` owns product logic, data, actions, route, risk, env, and acceptance logic
- `protocol-ui-fastlane` owns UI concretization, builder handoff, and fast review

Do not let `protocol-driven-build` drift into visual exploration just to compensate for missing UI work.

## Human-Friendly Requirement

Each template should have both:

- a human-readable view: charts, tables, examples, plain-language prompts
- a machine view: stable IDs, exact fields, allowed values, hard rules, forbidden transitions

## State Representation Rule

State should be communicated visually first.

For Stage 1, the default output order is:

1. main state diagram
2. main flowchart
3. forbidden transition diagram
4. scenario flowcharts
5. derived verification tables

Do not lead with tables when a state diagram or flowchart would be clearer.

## Output Style

Default to concise, structured Chinese for user-facing templates.

When generating protocol specs, prefer:

- state diagrams
- main flowcharts
- forbidden transition diagrams
- scenario flowcharts
- memory cards
- payload postcards
- effect tables
- verification matrices
- traceability maps

## Files

Use these files as the default staged assets:

- `workflow.md`
- `templates/00-prd-intake.md`
- `templates/00-boundary-intent.md`
- `templates/01-state.md`
- `templates/02-memory-data.md`
- `templates/03-effects-actions.md`
- `templates/04-api-persistence.md`
- `templates/05-route-screen.md`
- `templates/06-risk-trust-nfr.md`
- `templates/07-env-integration.md`
- `templates/08-verification-matrix.md`
- `templates/09-traceability.md`
- `templates/10-audit-diff.md`

## Kapi Example

For a concrete reverse-spec example, use a project-local sample that ships with your own repository.
