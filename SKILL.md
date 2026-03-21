---
name: ux-prototype
description: >
  Use for any digital product design work — screens, flows, wireframes, or user journeys. Triggers on: "design an app", "sketch this feature", "map out the flow", "what screens would this need", "prototype this idea", or "how should users do X". Runs a Lean UX process: surfaces domain context first, then produces opinionated artifacts (proto-persona card, JTBD statement, assumption map, conceptual model, scenario narratives, flow stress tests, design hypothesis). Uses AI to generate parallel hypotheses, stress-test flows against persona variants, audit language, and sweep for anti-patterns. Always invoke before any screen or flow work. If the user skips straight to UI without personas or goals, pull the process upstream.
---

# UX Prototype Skill

## What Makes This Different

Traditional UX process is bottlenecked by human bandwidth: one researcher, one set of interviews, one round of synthesis at a time. AI changes the calculus. This skill uses Claude's capabilities to do things a human-paced process can't:

- **Synthesize multiple user archetypes in parallel** and surface tensions between them before a single screen is drawn
- **Generate competing design hypotheses** for the same JTBD and critique each one immediately
- **Stress-test assumptions** by simulating how different persona types would react to a proposed flow
- **Compress the assumption-to-artifact cycle** — move from raw context to validated design hypothesis in one session rather than weeks
- **Act as a persistent design critic** who has read every relevant anti-pattern and will flag them without social awkwardness
- **Generate complete state inventories** for every screen — empty, loading, error, partial, read-only, overflow, first-time — including states the designer hasn't thought to ask about

The philosophy is Lean UX: small bets, explicit assumptions, fast learning cycles. We're not trying to build the perfect design upfront. We're trying to build the *right* first thing to put in front of real users as fast as possible.

---

## Step 0: Domain Context Discovery

**Before anything else**, Claude must ask the invoker a focused set of questions to understand the design context. Do not skip or assume answers. Do not proceed to artifacts until you have enough to make them meaningful.

Ask these questions conversationally — not as a form dump. Group them naturally. Wait for responses before continuing.

### Required Context Questions

**About the product and problem:**
- What is the product trying to do, in one sentence?
- What problem does it solve, and for whom?
- Is this a new product, a new feature on an existing product, or a redesign?

**About the users:**
- Do you have any existing user research — interviews, surveys, analytics, support tickets? If so, what were the most surprising or recurring themes?
- Who is the *primary* user? Describe them in behavioral terms, not demographic ones — what are they trying to accomplish, and what's getting in the way today?
- Are there secondary users or stakeholders whose needs matter but who aren't the primary focus?

**About the stage and constraints:**
- Where are you in the process — exploring the problem space, designing a specific feature, or reviewing/improving something that already exists?
- What's the platform and form factor? (Web, mobile, native app, embedded tool, etc.)
- Are there existing design patterns, a component library, or brand guidelines to respect?
- What does success look like — what's the one thing a user should be able to do easily that they can't today?

**About what you already have:**
- Do you have existing personas, user stories, or a PRD?
- Is there a prototype or design already in progress, or are we starting from scratch?

Claude should use the answers to calibrate the entire process. Sparse user research → more assumption-surfacing. Existing designs → more critique mode. Early exploration → more hypothesis generation.

---

## Step 1: Build the Lean UX Foundation

Lean UX is built on declared assumptions, not hidden ones. Before artifacts, make beliefs explicit so they can be tested.

### 1A. Proto-Persona Card (Required Output)

If no research exists, build a proto-persona from the context provided. A proto-persona is an explicit assumption about who the user is — not a researched fact. It must be labeled as such.

**Output format — always produce this as a structured card:**

```
┌─────────────────────────────────────────────────┐
│ PROTO-PERSONA                    [assumption ⚠️] │
│                                                  │
│ Name + Role: [Name], [specific role/context]     │
│                                                  │
│ Their world: [2-3 sentences on their day-to-day  │
│ context, pressures, and how this problem fits    │
│ into their work/life]                            │
│                                                  │
│ End goal: [What does success look like for them  │
│ in this domain? Not a task — an outcome.]        │
│                                                  │
│ Experience goal: [How do they want to feel       │
│ while using this product?]                       │
│                                                  │
│ Current behavior: [How do they solve this        │
│ problem today? What are they "firing"?]          │
│                                                  │
│ Frustrations: [What makes the current solution   │
│ feel broken, slow, or embarrassing?]             │
│                                                  │
│ Mental model: [How do they think about this      │
│ problem space? What analogies or metaphors       │
│ do they already use?]                            │
│                                                  │
│ Context of use: [Device, environment, urgency    │
│ level, interruption likelihood]                  │
│                                                  │
│ Validate with: [What questions should be asked   │
│ in a real user interview to confirm or refute    │
│ this persona?]                                   │
└─────────────────────────────────────────────────┘
```

If research exists, upgrade to a **Research-Grounded Persona** — same format, drop the ⚠️, and cite the evidence for each field.

**AI advantage:** Generate 2-3 persona variants in parallel if the problem space is ambiguous, then help the user choose which is primary. Surfacing persona tension early prevents building for a chimera.

### 1B. JTBD Statement (Required Output)

One per core use case. Always in this format:

> **When** [specific triggering situation],
> **I want to** [motivation / desired progress],
> **So I can** [functional outcome] — and feel [emotional outcome].

The emotional outcome is not optional. Products that nail the functional job but fail the emotional one don't get adopted.

**AI advantage:** Generate a functional JTBD and then explicitly surface the emotional and social jobs alongside it. Human designers routinely skip these.

### 1C. Assumption Map (Required Output)

Lean UX runs on explicit assumptions. Before designing, surface the riskiest ones.

**Output format:**

```
ASSUMPTION MAP
──────────────────────────────────────────────────────────
Belief                             | Risk   | How to Test
──────────────────────────────────────────────────────────
[Users will understand X           | High   | [Validation
 without explanation]              |        | method]
──────────────────────────────────────────────────────────
[Users will tolerate Y steps       | Medium | ...
 to complete Z]                    |        |
──────────────────────────────────────────────────────────
[Primary entry point is X]         | High   | ...
──────────────────────────────────────────────────────────
```

Risk = (how wrong we could be) × (how bad it would be if we're wrong)

Flag the top 2-3 high-risk assumptions. These are what the prototype needs to test — not demonstrate.

---

## Step 2: Conceptual Model Statement

Before any flows or screens, write the conceptual model in plain language.

This is 3-5 sentences answering: *What should a new user believe about how this product works after their first 60 seconds with it?*

It defines:
- The core metaphor or mental model to establish
- What prior knowledge of the user's the design can leverage
- What's genuinely new that needs to be taught

**Output format:**

```
CONCEPTUAL MODEL
────────────────────────────────────────────────
[Product name] works like [familiar analogy or
metaphor the persona already understands].

The central objects the user works with are:
  [Object 1] — [what it means in user terms]
  [Object 2] — [what it means in user terms]

The primary action is always: [verb phrase].

A user succeeds when they can [outcome] without
ever having to think about [implementation detail
we're hiding from them].
────────────────────────────────────────────────
```

This statement governs every navigation label, empty state, and onboarding decision. When two design options conflict, the conceptual model breaks the tie.

---

## Step 3: Flow Design

### 3A. Scenario Narrative First (Required)

Write the scenario in plain language before any flow diagram. This is not optional.

**Output format:**

```
SCENARIO: [Name]
Persona: [Persona name]
Trigger: [What just happened that causes them to open the product?]
────────────────────────────────────────────────
[2-4 sentence narrative. Present tense. Written
from the persona's perspective. Describes their
goal, their starting state, and what success
feels like — not the UI steps.]
────────────────────────────────────────────────
Happy path outcome: [One sentence]
Failure mode we're designing against: [One sentence]
```

### 3B. Flow Annotation Standard

Every flow step must be annotated with:
- **Why this step exists** (user need it serves)
- **What could go wrong here** (error state or drop-off risk)
- **What assumption is being tested** (link back to assumption map)

Flows without annotations are not complete. Unannotated steps are hidden assumptions.

### 3C. AI-Powered Flow Stress Test

After a flow is drafted, Claude should run a **persona stress test** — simulate how the primary persona, at least one edge-case persona (anxious first-timer, power user, interrupted mid-task), would experience each step.

**Output format:**

```
FLOW STRESS TEST: [Flow name]
────────────────────────────────────────────────────
Persona variant          | Step at risk | Issue
────────────────────────────────────────────────────
First-time user          | Step 3       | Will not
                         |              | understand
                         |              | [label]
────────────────────────────────────────────────────
Power user               | Step 2       | Friction —
                         |              | already knows
                         |              | this info
────────────────────────────────────────────────────
Mobile / interrupted     | Step 4       | Loses progress
                         |              | if app closed
────────────────────────────────────────────────────
```

This replaces the need for a full usability test at the wireframe stage — not perfectly, but enough to catch the worst problems before they get built.

### 3D. Edge Case & State Inventory (Required Output)

Every flow and every key screen must have a complete state inventory before it's considered designed. Undesigned states become developer guesswork and user-facing bugs.

**Run this inventory for every flow and every significant screen:**

#### Flow-Level Edge Cases

```
FLOW EDGE CASES: [Flow name]
────────────────────────────────────────────────────────
Category          | Scenario                | Design response
────────────────────────────────────────────────────────
Entry conditions  | User arrives mid-flow   | [How do we handle?]
                  | from an external link   |
────────────────────────────────────────────────────────
Permissions       | User lacks required     | [Graceful degradation
                  | role/access             | or clear explanation?]
────────────────────────────────────────────────────────
Data state        | Required data is        | [Block? Warn? Default?]
                  | missing or stale        |
────────────────────────────────────────────────────────
Interruption      | User abandons mid-flow  | [Save progress?
                  | and returns later       | Resume prompt?]
────────────────────────────────────────────────────────
Concurrency       | Another user/tab        | [Conflict resolution
                  | modifies same data      | or lock strategy?]
────────────────────────────────────────────────────────
Failure           | Network drops mid-flow  | [Retry? Data loss?
                  |                         | Clear feedback?]
────────────────────────────────────────────────────────
Completion        | User completes flow     | [Confirmation? Next
                  | more than once          | step? Idempotent?]
────────────────────────────────────────────────────────
```

#### Screen-Level State Inventory

Every screen exists in multiple states. All must be explicitly designed — never left to engineering defaults.

```
STATE INVENTORY: [Screen name]
────────────────────────────────────────────────
State             | Trigger                 | Design notes
────────────────────────────────────────────────
Empty             | No data exists yet      | [Not just a blank
                  |                         | screen — what action
                  |                         | does the user take?]
────────────────────────────────────────────────
Loading           | Data is being fetched   | [Skeleton? Spinner?
                  |                         | Optimistic UI?]
────────────────────────────────────────────────
Partial / degraded| Some data loaded,       | [Show what we have?
                  | some failed             | Wait for all?]
────────────────────────────────────────────────
Error             | Request failed          | [Actionable message.
                  |                         | What can they do?]
────────────────────────────────────────────────
Success           | Action completed        | [Confirmation copy.
                  |                         | What happens next?]
────────────────────────────────────────────────
Read-only         | User lacks edit perms   | [Visible but locked?
                  |                         | Hidden entirely?]
────────────────────────────────────────────────
Overflow          | Content exceeds         | [Truncate? Paginate?
                  | display limits          | Scroll? Collapse?]
────────────────────────────────────────────────
First-time / onboarding | User has never    | [Tooltips? Guided
                  | visited this screen     | empty state?]
────────────────────────────────────────────────
```

#### Data Edge Cases

For any screen displaying dynamic content, test the design against:

- **Zero items** — empty list, no results, no history
- **One item** — does the layout still make sense?
- **Maximum items** — 500 results, very long lists
- **Very long strings** — a name with 80 characters, a description with 500
- **Missing optional fields** — what renders when a field is blank?
- **Mixed states** — some items complete, some pending, some errored
- **Stale data** — content that hasn't refreshed and may be out of date

#### Interaction States (Component Level)

For every interactive element, define:

```
INTERACTION STATES: [Component name]
────────────────────────────────────
Default    → what it looks like at rest
Hover      → visual feedback on mouse-over
Focus      → keyboard/accessibility focus indicator
Active     → mid-click or mid-press state
Disabled   → unavailable, and why (tooltip?)
Loading    → async action in progress
Success    → confirmation feedback
Error      → validation or action failure
────────────────────────────────────
```

**AI advantage:** Claude should proactively generate the full state inventory for any screen described, including states the user hasn't thought to ask about. Undocumented states are the most common cause of design-to-development gaps. Surface them all before handoff.

---

## Step 4: Screen Design Standards

### Information Hierarchy Rule
Every screen has one job. State it before designing the screen:
> "On this screen, [persona name] is trying to [micro-goal]. The single most important thing they need is [X]."

Everything on the screen either serves X or should be removed.

### Required Screen Annotations
Each key screen should be annotated with:
1. **Persona + micro-goal** — who, doing what
2. **Primary action** — the one thing we want them to do
3. **Cognitive load audit** — how many decisions or pieces of new information are on this screen?
4. **Copy rationale** — why each label uses the specific words it does (user language, not system language)
5. **Anti-pattern check** — explicitly confirm none of the flagged anti-patterns are present (see `references/anti-patterns.md`)

### Defaults Are Decisions
Every default value, pre-selected option, and empty state is a design decision. Document them. A default that serves the system's convenience rather than the user's most common need is a UX bug.

---

## Step 5: Design Hypothesis Output

In Lean UX, the prototype exists to test a hypothesis. Every design session should end with an explicit hypothesis statement.

**Output format:**

```
DESIGN HYPOTHESIS
────────────────────────────────────────────────
We believe that [this design decision / feature /
flow] will achieve [this outcome] for [this persona]
because [this assumption about their behavior or
mental model].

We'll know we're right when:  [measurable signal]
We'll know we're wrong when:  [measurable signal]

Riskiest assumption being tested: [from assumption map]
Minimum fidelity needed to test it: [lo-fi sketch /
  clickable prototype / live with real data]
────────────────────────────────────────────────
```

This is the artifact that should go into the next user session — not a polished mockup, but a focused test of the riskiest assumption.

---

## Step 6: Prototype Feature Walkthrough (Required Output)

After any prototype, flow, or set of screens is produced, Claude must generate a structured walkthrough of everything that was designed. This serves as a handoff document, a review artifact, and a record of design intent.

The walkthrough is written from the **user's perspective**, not the system's. It describes what the user experiences, not what the UI renders.

**Output format:**

```
PROTOTYPE WALKTHROUGH: [Prototype / Feature name]
Persona: [Who this is designed for]
Core JTBD: [The job this prototype addresses]
────────────────────────────────────────────────

FEATURES INCLUDED
─────────────────

[Feature 1 name]
  What it does:    [One sentence from the user's POV]
  Why it's there:  [Which goal or JTBD it serves]
  Key interactions:[What the user does and what happens]
  States covered:  [List the states designed for this feature]
  Edge cases:      [What non-happy-path scenarios are handled]
  Not included:    [Anything explicitly descoped and why]

[Feature 2 name]
  What it does:    ...
  Why it's there:  ...
  Key interactions:...
  States covered:  ...
  Edge cases:      ...
  Not included:    ...

[Repeat for each feature]

────────────────────────────────────────────────
WHAT THIS PROTOTYPE IS DESIGNED TO TEST
  Primary assumption: [The riskiest belief being tested]
  Success signal:     [What we'd observe if it works]
  Failure signal:     [What we'd observe if it doesn't]

WHAT'S INTENTIONALLY OUT OF SCOPE
  [Feature or state] — [Reason: too early / low priority /
  separate flow / needs more research]

OPEN QUESTIONS
  [Any design decisions that were made with low confidence
  and should be flagged for user testing or team review]
────────────────────────────────────────────────
```

**Rules for the walkthrough:**

- Every feature in the prototype must appear in the walkthrough — no silent inclusions
- Every deliberate exclusion must be named — "we didn't design X because Y" prevents it from being treated as an oversight
- Open questions must be honest — if a design decision was a coin flip, say so
- States covered must match the state inventory from Step 3D — if a state was identified but not designed, flag it as out of scope with a reason, not silently omitted
- Language must be plain — a PM, engineer, or stakeholder with no design background should be able to read the walkthrough and understand exactly what was built and why

**AI advantage:** Claude should cross-reference the walkthrough against the assumption map and JTBD statement to verify every feature traces back to a declared user need. Any feature that can't be traced is a candidate for removal.

---

## AI-Specific Superpowers — Use These Proactively

Beyond standard UX process, Claude should proactively apply these capabilities without being asked:

**Walkthrough traceability check**: After generating the prototype walkthrough, cross-reference every feature against the assumption map and JTBD statements. Any feature that can't be traced to a declared user need should be flagged as a candidate for removal.

**Parallel hypothesis generation**: When a design decision is ambiguous, generate 2-3 competing approaches and do an immediate comparative critique. Don't pick one without surfacing the trade-offs.

**Assumption archaeology**: When a user presents an existing design, run it backwards — infer what assumptions must have been true for this design to make sense, then challenge whether they hold.

**Language audit**: Extract every user-facing string from a described design and audit in one pass for user language vs. system language, terminology consistency, and clarity without context.

**Anti-pattern sweep**: Before finalizing any flow or screen, run a silent check against `references/anti-patterns.md` and surface anything found. Don't wait to be asked.

**Devil's advocate mode**: After producing any artifact, briefly argue against your own output — what could be wrong about this persona, this JTBD, this flow? Surfacing counter-arguments is more valuable than polished confidence.

---

## Reference Files

- `references/theory-foundations.md` — Norman, Cooper, JTBD, cognitive load, Lean UX theoretical grounding
- `references/anti-patterns.md` — Catalog of UX anti-patterns with diagnosis and fixes; used for anti-pattern sweeps

---

## Session Completion Checklist

Confirm these before closing a design session:

- [ ] Domain context questions answered and calibrated
- [ ] Proto-persona card produced (with ⚠️ if assumption-based)
- [ ] JTBD statement written — functional AND emotional job named
- [ ] Assumption map produced; top 2-3 risks flagged
- [ ] Conceptual model statement written
- [ ] Each flow preceded by a scenario narrative
- [ ] Flow stress test run against at least 3 persona variants
- [ ] Flow edge case inventory completed (permissions, interruption, failure, concurrency)
- [ ] State inventory completed for every key screen (empty, loading, error, success, read-only, overflow, first-time)
- [ ] Data edge cases checked (zero, one, max, long strings, missing fields)
- [ ] Interaction states defined for all interactive components
- [ ] Each key screen annotated with persona, micro-goal, primary action, cognitive load
- [ ] Anti-pattern sweep completed
- [ ] Design hypothesis written with testable success/failure signals
- [ ] Riskiest assumption identified and minimum prototype fidelity stated
- [ ] Prototype walkthrough produced — all features documented with rationale, states, edge cases, exclusions, and open questions
