# UX Theory Foundations

A reference for deeper grounding when designing or critiquing prototypes.

---

## Lean UX — Gothelf & Seiden

### Core Principle
Lean UX shifts the unit of value from deliverables to outcomes. The goal is not a beautiful wireframe — it is a validated learning about user behavior. Artifacts exist only insofar as they help test assumptions.

### The Lean UX Loop
1. **Declare assumptions** — what must be true for this design to succeed?
2. **Form a hypothesis** — if we build X for persona Y, we'll see outcome Z
3. **Build the minimum artifact** to test the hypothesis (lowest fidelity that will generate signal)
4. **Run it with real users**
5. **Learn** — was the hypothesis confirmed, refuted, or inconclusive?
6. **Decide** — pivot, persevere, or abandon

### Proto-Personas
When research doesn't exist, Lean UX uses proto-personas — explicit, labeled assumptions about who the user is. The critical discipline: they must be *labeled as assumptions*, not treated as facts. An unlabeled proto-persona is a fiction dressed up as research.

### Assumption Mapping
Before design begins, surface all implicit beliefs the design depends on. Rank by risk: (how wrong we could be) × (how bad it would be if we're wrong). The riskiest assumptions determine what gets prototyped first.

### Minimum Viable Prototype vs. MVP
- **Minimum viable prototype**: Lowest fidelity artifact that will generate signal on a specific assumption. Does not need to be shippable.
- **MVP**: Minimum shippable product for market learning.
These are not the same thing. Most assumption tests don't require shipping code.

---

## Don Norman — Mental Models & The Design of Everyday Things

### The Three Models
- **Designer's model**: The designer's conception of how the system works
- **System image**: Everything the product communicates — UI, documentation, error messages, marketing
- **User's mental model**: What the user believes about how the system works

The critical insight: designers can't communicate directly with users. They can only shape the system image. Good design makes the system image accurate enough that users develop a mental model close to the designer's model.

### Gulf of Execution / Gulf of Evaluation
- **Gulf of Execution**: The gap between what the user wants to do and what actions are available
- **Gulf of Evaluation**: The gap between the system's state and how easy it is to perceive and interpret that state

UX design is largely about closing both gulfs.

### Seven Stages of Action (Norman)
1. Form a goal
2. Form an intention
3. Specify an action
4. Execute the action
5. Perceive the state of the world
6. Interpret the perception
7. Evaluate the outcome

Every screen should be analyzable through this lens: where does the user get stuck?

---

## Alan Cooper — Goal-Directed Design

### Implementation Model vs. Mental Model
The most damaging UX mistake: exposing the implementation model (how the software is built) to the user. Users shouldn't have to understand file systems, database IDs, or session states.

Design should reflect the user's mental model of the task domain, not the engineer's model of the system.

### Personas
Cooper's personas are behavioral archetypes synthesized from research — not demographic profiles. A good persona:
- Has a name and a specific professional/personal context
- Has explicit goals at multiple levels (life, end, experience)
- Has frustrations that drive them away from current solutions
- Has a mental model of the problem domain (which may be wrong)
- Is specific enough that design decisions can be tested against it: "Would Maria actually do this?"

### The Elastic User Problem
When designers say "the user," they unconsciously shift who they mean to suit whatever argument they're making. Named personas prevent this. "Would Maria do this?" is a testable question. "Would the user do this?" is not.

### Excise vs. Core Tasks
- **Core tasks**: Actions that directly serve the user's goal
- **Excise tasks**: Actions required by the system that don't serve the goal (filling in required fields that exist for system reasons, confirming actions the system could infer)

Good design minimizes excise. Every form field, confirmation step, and navigation hop should be questioned: who is this for?

---

## Jobs-to-be-Done (Christensen / Ulwick / Klement)

### Core Insight
People don't buy products — they hire them to make progress in a specific circumstance. The "job" is the unit of analysis, not the user or the product.

### The JTBD Statement
> "When [situation], I want to [motivation / desired progress], so I can [expected outcome / benefit]."

### Functional vs. Emotional vs. Social Jobs
- **Functional job**: The practical task to accomplish
- **Emotional job**: How they want to feel (or not feel) while doing it
- **Social job**: How they want to be perceived by others

Great products address all three. Most products only design for the functional job and wonder why adoption is hard.

### JTBD vs. Personas — Complementary, Not Competing
- Personas tell you *who* is hiring your product and what their context is
- JTBD tells you *why* they're hiring it and what competing solutions they're firing
- Together they produce sharper, more defensible design decisions

---

## Information Architecture — Rosenfeld, Morville & Arango

### The Three Circles
- **Users** — their needs, information-seeking behaviors, experience
- **Content** — what exists, what's needed, how it's structured
- **Context** — business goals, constraints, culture, technology

Good IA sits at the intersection of all three.

### Wayfinding
Users navigating a product need:
- To know where they are
- To know what's around them
- To know how to get back

Navigation that fails any of these three creates anxiety and abandonment.

---

## Fitts's Law & Motor Constraints

**Fitts's Law**: Time to acquire a target is a function of distance and size. Bigger targets closer to the starting position are faster to hit.

Practical implications:
- Primary CTAs should be large
- Destructive actions (delete, cancel) should be physically separated from primary actions
- Mobile targets should be minimum 44x44pt (Apple HIG) / 48x48dp (Material)
- Contextual menus and tooltips placed near where the cursor/finger already is reduce acquisition time

---

## Hick's Law

Time to make a decision increases logarithmically with the number of choices.

Practical implications:
- Navigation menus with 7+ items create measurable decision fatigue
- Onboarding flows that front-load all configuration choices cause drop-off
- Progressive disclosure — reveal complexity only when needed — is a Hick's Law application

---

## Cognitive Load Theory

Working memory has a limited capacity (roughly 4±1 items, per more recent research). When design exceeds this capacity, errors increase and users abandon tasks.

Types of cognitive load:
- **Intrinsic**: The inherent complexity of the task itself (can't be designed away, but can be chunked)
- **Extraneous**: Load imposed by poor design — confusing labels, unnecessary steps, visual noise
- **Germane**: Load that builds useful mental models — the only kind worth paying for

UX design's job: eliminate extraneous load, minimize intrinsic load through chunking and scaffolding, preserve germane load.

---

## Accessibility as Design Constraint

Accessibility requirements are design opportunities:
- High contrast ratios (4.5:1 for text) improve readability for everyone, not just low-vision users
- Clear focus states help keyboard users and users in bright sunlight
- Not relying solely on color means the design works in grayscale, for colorblind users, and in low-quality print
- Screen reader-compatible hierarchy produces cleaner semantic structure that benefits SEO and parsability

WCAG 2.1 AA is the baseline. Design for it from the start, not as a retrofit.
