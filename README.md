# ux-prototype — A Lean UX Skill for Claude

[![Download .skill](https://img.shields.io/badge/Download-.skill-blue?style=for-the-badge&logo=github)](https://github.com/timeril/ux-prototype-skill/releases/download/v1.0.0/ux-prototype.skill)

A Claude skill that grounds every prototype, flow, and screen design in rigorous user-centered design theory — powered by Lean UX principles and augmented by AI-specific capabilities that go beyond what a traditional human-paced UX process can do.

---

## What It Does

When triggered, this skill prevents the most common design failure: jumping to screens before understanding who is using the product, why, and with what mental model.

It runs a structured Lean UX process that produces **opinionated, standardized artifacts** at every stage — from initial domain discovery through to a testable design hypothesis. It also applies AI-specific capabilities that compress weeks of traditional process into a single session.

---

## AI-Augmented Capabilities

This skill does things a human UX process typically can't:

| Capability | What it means in practice |
|---|---|
| **Parallel persona synthesis** | Generate 2-3 user archetypes simultaneously and surface tensions between them before any screen is drawn |
| **Competing hypothesis generation** | Produce multiple design approaches for the same JTBD and immediately critique each one |
| **Flow stress testing** | Simulate how first-time users, power users, and interrupted users experience every step of a flow |
| **Assumption archaeology** | Run an existing design backwards to infer what hidden beliefs it depends on — then challenge them |
| **Language audit** | Sweep every user-facing string for system language, terminology inconsistency, and clarity failures |
| **Anti-pattern sweep** | Automatically check all flows and screens against a comprehensive anti-pattern catalog before finalizing |
| **Devil's advocate mode** | Argue against its own output after every artifact to surface counter-arguments proactively |

---

## Trigger Phrases

The skill activates on any of these (and similar):

- "help me design an app"
- "sketch out how this feature would work"
- "what screens would this need"
- "map out the flow"
- "prototype this idea"
- "how should users accomplish X"
- "what would this look like"

It also triggers proactively if a user jumps straight to screen design without having established personas or goals.

---

## Process Overview

### Step 0 — Domain Context Discovery
Before anything else, Claude asks a focused set of questions about the product, the users, the stage of design, and existing research. Answers calibrate everything that follows.

### Step 1 — Lean UX Foundation
Three required outputs, each in a standardized format:

**Proto-Persona Card** — a behaviorally-grounded user archetype, explicitly labeled as an assumption (⚠️) if not research-backed. Includes end goal, experience goal, current behavior, frustrations, mental model, context of use, and validation questions.

**JTBD Statement** — Jobs-to-be-Done framing of the core user need, covering functional, emotional, and social jobs.

**Assumption Map** — all design-critical beliefs ranked by risk, with a validation method for each.

### Step 2 — Conceptual Model Statement
A plain-language description of what a new user should believe about how the product works after their first 60 seconds with it. Governs every navigation label, empty state, and onboarding decision.

### Step 3 — Flow Design
Flows are preceded by scenario narratives (plain language, written from the persona's perspective). Each step is annotated with why it exists, what could go wrong, and which assumption it tests. A persona stress test is run against every flow.

### Step 4 — Screen Design Standards
Each key screen is annotated with persona + micro-goal, primary action, cognitive load audit, copy rationale, and an anti-pattern check.

### Step 5 — Design Hypothesis
Every session ends with a testable hypothesis in a standard format — what we believe, what we'll see if we're right, what we'll see if we're wrong, and the minimum fidelity needed to test it.

---

## Artifact Formats

All outputs follow strict templates documented in `SKILL.md`. Key formats:

```
┌─────────────────────────────────────────────────┐
│ PROTO-PERSONA                    [assumption ⚠️] │
│ Name + Role / Their world / End goal /           │
│ Experience goal / Current behavior /             │
│ Frustrations / Mental model / Context of use /   │
│ Validate with                                    │
└─────────────────────────────────────────────────┘
```

```
JTBD STATEMENT
When [situation], I want to [motivation],
So I can [functional outcome] — and feel [emotional outcome].
```

```
ASSUMPTION MAP
Belief | Risk | How to Test
```

```
DESIGN HYPOTHESIS
We believe [decision] will achieve [outcome] for [persona]
because [assumption].
We'll know we're right when: [signal]
We'll know we're wrong when: [signal]
Riskiest assumption: / Minimum fidelity needed:
```

---

## Theoretical Foundations

The skill draws on:

- **Lean UX** (Gothelf & Seiden) — assumption-hypothesis-test loop, proto-personas, minimum viable prototypes
- **Goal-Directed Design** (Alan Cooper, *About Face*) — persona methodology, implementation vs. mental model distinction, excise vs. core tasks
- **The Design of Everyday Things** (Don Norman) — mental models, gulf of execution/evaluation, seven stages of action
- **Jobs-to-be-Done** (Christensen / Ulwick / Klement) — functional, emotional, and social job framing
- **Cognitive Load Theory** — intrinsic, extraneous, and germane load; chunking; progressive disclosure
- **Fitts's Law / Hick's Law** — motor constraints and decision fatigue in UI
- **WCAG 2.1 AA** — accessibility as a design constraint from the start

Full theory reference: [`references/theory-foundations.md`](references/theory-foundations.md)

Anti-pattern catalog: [`references/anti-patterns.md`](references/anti-patterns.md)

---

## File Structure

```
ux-prototype-skill/
├── SKILL.md                        # Main skill instructions
├── README.md                       # This file
└── references/
    ├── theory-foundations.md       # Lean UX, Norman, Cooper, JTBD, etc.
    └── anti-patterns.md            # UX anti-patterns with diagnosis & fixes
```

---

## Installation

Download the `.skill` file from [Releases](../../releases) and install it in Claude's skill settings, or clone this repo and load the skill folder directly.

---

## Contributing

Contributions welcome — especially:
- Additional anti-patterns with real-world examples
- Domain-specific theory extensions (voice UI, data-heavy tools, onboarding flows, etc.)
- Improved artifact templates based on real usage

Open an issue or PR.

---

## License

MIT
