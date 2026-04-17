# Protocol-Driven Build Workflow

This workflow is stage-gated.

The goal is not to fill every document upfront.

The goal is to unlock the next useful constraint only when the project is ready for it.

## Input First

Start from project inputs, not from blank forms.

Priority sources:

1. PRD
2. product or idea docs
3. handoff or developer docs
4. design specs that contain product behavior
5. existing code
6. user clarification only when the above is insufficient

Default interaction pattern:

1. scan sources
2. extract facts
3. produce a draft
4. ask the user to confirm or correct the draft

Do not begin by dumping empty templates if usable project inputs already exist.

## Modes

### Mode A: Spec-First

Use when the feature does not exist yet.

Goal:

- define constraints before coding
- prevent AI from improvising architecture

### Mode B: Reverse-Spec

Use when code already exists.

Goal:

- extract current behavior
- compare current behavior with intended behavior
- identify drift and missing constraints

### Mode C: Hybrid

Use when part of the system exists and part is still being designed.

Goal:

- preserve what is already true
- define what still needs to be built
- prevent drift between old implementation and new scope

## Stage Order

### Stage -1: PRD Intake / Input Extraction

Define:

- source documents
- source confidence
- extracted facts
- open conflicts
- a first normalized draft

Unlock condition:

- at least one project input exists, or the user confirms there is none

Exit gate:

- source files are listed
- extracted facts are separated from assumptions
- conflicting sources are called out explicitly
- a draft is ready for user confirmation

### Level Split

Every run should declare one of these first:

- `app-level`
- `feature-level`

Recommended sequence:

1. `app-level Stage 0`
2. `app-level Stage 1`
3. highest-priority `feature-level Stage 0`
4. highest-priority `feature-level Stage 1`

Do not skip `app-level` when product naming, protocol list, platform path, or scope is still moving.

### Stage 0: Boundary / Intent + Minimum Acceptance

Define:

- what this feature is
- what it is not
- success rule
- failure rule
- minimum acceptable outcome
- must-never-happen outcomes

Unlock condition:

- the user can explain the feature in one sentence

Exit gate:

- in-scope and out-of-scope are separated
- success is testable
- failure is recognizable
- minimum acceptance is explicit
- at least one must-never-happen case is explicit

### Stage 1: State

Define:

- top-level state flow
- events
- transitions
- forbidden transitions
- embedded capabilities
- derived subflows when needed

Unlock condition:

- Stage 0 is confirmed

Exit gate:

- every major user-visible step belongs to a state
- no hidden business flow depends on unnamed booleans
- forbidden transitions are explicit
- every state and event has a stable ID
- the primary representation is a diagram, not a table
- if the system is large, top-level flow is defined before protocol-level subflows

### Stage 2: Memory / Data

Define:

- long-lived records
- field names
- types
- enums
- invariants

Unlock condition:

- State is confirmed

Exit gate:

- persistent data is separated from transient state
- names are stable enough for implementation
- examples and error examples are present
- each entity has a stable ID

### Stage 3: Effects / Actions

Define:

- what each transition triggers
- storage
- navigation
- audio
- haptics
- toast
- analytics

Unlock condition:

- State and Data are confirmed

Exit gate:

- each effect has a trigger point
- no important action is hidden inside arbitrary UI callbacks
- each effect has a stable `ACTION_ID`

### Stage 4: API / Persistence

Define:

- handshake input
- handshake output
- failure output
- invocation timing

Unlock condition:

- Data and Effects are confirmed

Exit gate:

- payload fields match the data spec
- success/failure handling is explicit
- it is clear whether this is local persistence or remote API
- timeout/retry/idempotency/cancel/duplicate semantics are explicit

### Stage 5: Route / Screen Contract

Define:

- entry point
- exit point
- screen ownership
- route transitions

Unlock condition:

- State, Effects, and API are confirmed

Exit gate:

- each route has a reason to exist
- route flow matches state flow
- back/resume/deep-link behavior is explicit or marked N/A

### Stage 6: Risk / Trust / NFR

Define:

- auth and permissions
- data sensitivity and privacy
- abuse or misuse risks
- latency and availability expectations
- observability requirements

Unlock condition:

- API or Route has become concrete

Exit gate:

- security/privacy assumptions are explicit
- non-functional constraints are testable
- missing observability is visible early

### Stage 7: Env / Integration

Define:

- env vars
- base URLs
- platform constraints
- third-party dependencies
- local/test/prod differences

Unlock condition:

- real integration is needed and Risk / Trust / NFR is confirmed

Exit gate:

- runtime dependencies are explicit
- missing config can be detected early

### Stage 8: Verification Matrix

Define:

- end-to-end test cases
- failure-path test cases
- observable debug points
- release blockers

Unlock condition:

- implementation is about to start or is in progress

Exit gate:

- user can tell what “done” means without reading code
- each critical path has at least one test case ID
- each release blocker is explicit

### Stage 9: Traceability

Define:

- how `STATE_ID`, `EVENT_ID`, `ACTION_ID`, `OP_ID`, `ROUTE_ID`, and `TC_ID` link together
- which links are intentionally `N/A`

Unlock condition:

- stages 0 through 8 are materially complete

Exit gate:

- critical flows can be followed across stages without guessing
- inconsistencies are visible mechanically, not just narratively

### Stage 10: Audit / Diff

Define:

- intended behavior
- actual behavior
- gaps
- drift

Use only after some implementation exists.

## UI Handoff Boundary

The default handoff to `protocol-ui-fastlane` happens after the minimum protocol set for UI is stable:

- `Stage 0` Boundary / Intent
- `Stage 1` State
- `Stage 2` Memory / Data
- `Stage 3` Effects / Actions
- `Stage 5` Route / Screen Contract

Recommended stronger handoff:

- `Stage 0-8` confirmed

After the handoff:

1. `protocol-driven-build` pauses visual work
2. `protocol-ui-fastlane` translates the confirmed protocol into UI packs or external-builder handoff assets
3. implementation or external generation happens
4. return here for `Stage 9` Traceability and `Stage 10` Audit / Diff when real implementation exists

## Assistant Behavior

At each stage, the assistant should:

1. Announce the current stage.
2. State the current scope level.
3. Ask only for the minimum required information for that stage.
4. Prefer a draft generated from project sources over a blank template.
5. Summarize the result in normalized form.
6. Explicitly state whether the stage is `confirmed` or `still open`.
7. Preserve stable IDs once introduced. If they change, explain why.

## Default Reminder Pattern

When the user introduces a feature, the assistant should not ask for everything.

The assistant should say, in effect:

- We are at Stage X.
- We are working at app-level or feature-level.
- I only need these fields now.
- Later stages such as API or env will be unlocked after this is confirmed.

## Suggested User Flow

1. Run `00-prd-intake.md`
2. Confirm `app-level 00-boundary-intent.md`
3. Confirm `app-level 01-state.md`
4. Open highest-priority `feature-level 00-boundary-intent.md`
5. Open highest-priority `feature-level 01-state.md`
6. Fill `02-memory-data.md`
7. Fill `03-effects-actions.md`
8. When persistence or backend is real, fill `04-api-persistence.md`
9. When screens and navigation are needed, fill `05-route-screen.md`
10. When auth, privacy, performance, or trust questions become concrete, fill `06-risk-trust-nfr.md`
11. When integration starts, fill `07-env-integration.md`
12. Before delivery, fill `08-verification-matrix.md`
13. Before handoff, fill `09-traceability.md`
14. After implementation, optionally fill `10-audit-diff.md`
