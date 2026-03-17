# UX Anti-Patterns Reference

Common design failure modes, their root causes, and how to fix them.

---

## Persona Anti-Patterns

### The Demographic Ghost
**What it looks like**: "Our user is a 28-35 year old professional who uses smartphones."
**Why it fails**: Demographics don't predict behavior. A 30-year-old accountant and a 30-year-old artist have the same demographics but radically different mental models and goals.
**Fix**: Replace demographics with behavioral characteristics, goals, and frustrations. Demographics can add context but shouldn't define the persona.

### The Aspirational User
**What it looks like**: A persona with no frustrations, abundant time, and perfect technical literacy.
**Why it fails**: Aspirational users don't exist. Designing for them produces products that work great in demos and fail in real conditions.
**Fix**: Pressure-test personas. Ask: "What would make this person give up?" If the answer is "nothing," the persona is fictional.

### The Elastic User
**What it looks like**: Design decisions justified by "the user wants X" where "the user" silently shifts to whoever supports the current argument.
**Why it fails**: Without a named, specific persona, anyone can claim to speak for users. Decisions become political, not design-based.
**Fix**: Name the persona. Any claim about what "users want" must specify which persona.

### Persona Proliferation
**What it looks like**: A product trying to serve 8 different personas equally.
**Why it fails**: When you design for everyone, you design for no one. Trade-offs become impossible to make.
**Fix**: Identify a primary persona and secondary personas. Primary persona drives all design decisions. Secondary personas should not be harmed by those decisions, but they don't drive them.

---

## Goal/JTBD Anti-Patterns

### Task-Level Design
**What it looks like**: Feature specs written as task lists: "User can upload a file. User can rename a file. User can delete a file."
**Why it fails**: Tasks without goals produce feature sets with no coherent experience. Users complete tasks but don't achieve goals.
**Fix**: Frame features in terms of end goals: "User can manage files so they can find and share the right version without email confusion."

### The Feature Fallacy
**What it looks like**: "Users asked for X, so we built X."
**Why it fails**: Users describe solutions, not needs. Henry Ford's apocryphal quote applies: they'd have asked for faster horses.
**Fix**: When a user requests a feature, ask "What are you trying to accomplish?" three times. Get to the underlying JTBD before designing the solution.

### Ignoring the Emotional Job
**What it looks like**: A product that is functionally correct but creates anxiety, confusion, or embarrassment.
**Why it fails**: Users don't separate functional and emotional experience. "It works but I hate using it" is product failure.
**Fix**: Explicitly name the emotional job in the JTBD statement. Design deliberately for it.

---

## Flow Anti-Patterns

### The Registration Wall
**What it looks like**: Requiring account creation before the user can experience any product value.
**Why it fails**: Users can't evaluate whether the product deserves their trust before being asked to commit to it.
**Fix**: Delay registration until the user has experienced value, or until it's genuinely required. Consider guest modes, trial flows, or showing a preview of the value before the gate.

### Premature Data Collection
**What it looks like**: Onboarding flows that ask users to configure everything before they can use the product.
**Why it fails**: Users don't know what they want to configure until they've used the product. Front-loading configuration increases drop-off and produces poor initial settings.
**Fix**: Apply progressive disclosure. Collect what's required to start. Prompt for additional configuration in context, when the user encounters a decision that requires it.

### The Dead End
**What it looks like**: A screen or state with no clear next action.
**Why it fails**: Users don't know what to do next. Anxiety increases. They leave.
**Fix**: Every screen must have a primary next action that moves the user toward their goal. Even "empty states" should suggest a next step.

### Confirmation Theater
**What it looks like**: "Are you sure you want to do X? [Cancel] [OK]"
**Why it fails**: Confirmation dialogs are ignored after the first encounter. They add friction without preventing errors.
**Fix**: Use confirmation dialogs only for truly irreversible, high-consequence actions. For reversible actions, allow undo instead. For destructive actions, require the user to type a confirmation string (used for high-stakes cases) or build in a grace period.

### Wizard Imprisonment
**What it looks like**: Multi-step flows with no way to go back, skip, or exit.
**Why it fails**: Users encounter a step they can't complete (missing information, unexpected question) and abandon the entire flow.
**Fix**: Allow back navigation. Save progress. Make optional steps skippable. Always show where the user is in the sequence.

---

## Screen Design Anti-Patterns

### Implementation Bleeding
**What it looks like**: UI labels and navigation that reflect database structure, API names, or engineering terminology.
**Why it fails**: Users don't think in implementation terms. "Entity management" means nothing to a user trying to manage their clients.
**Fix**: Use user language exclusively. Run a quick test: could a non-technical person in your target audience understand every label without a tooltip?

### Color-Only Communication
**What it looks like**: Status indicators that rely exclusively on red/green color coding.
**Why it fails**: 8% of men have color vision deficiency. Color also fails in print, grayscale screenshots, and low-quality displays.
**Fix**: Always pair color with a secondary indicator: icon, label, or pattern.

### Mystery Meat Navigation
**What it looks like**: Icon-only navigation with no labels.
**Why it fails**: Icons are not universally understood. The same icon means different things in different cultural contexts.
**Fix**: Label all navigation. If space is constrained, use icons with labels on hover/focus, or use a bottom nav with labels on mobile.

### The False Bottom
**What it looks like**: A long page where important content exists below a visually complete-looking section.
**Why it fails**: Users assume they've seen everything when the page looks finished. Critical content below the fold goes unread.
**Fix**: Use visual cues (cut-off content, scroll indicators) to signal there's more. Put critical actions and information above visual breaks.

### Verbose Error Messages That Don't Help
**What it looks like**: "An error has occurred. Please try again later."
**Why it fails**: Users don't know what went wrong, what they should do, or whether their data was saved.
**Fix**: Error messages should (1) explain what happened in plain language, (2) tell the user what to do next, and (3) preserve any data the user entered.

### The Disabled Mystery Button
**What it looks like**: A greyed-out primary action with no explanation of why it's disabled.
**Why it fails**: Users don't know what prerequisite they're missing. They're stuck with no path forward.
**Fix**: Either explain why the action is disabled (tooltip, inline note), or keep it enabled and surface the validation error when they try to use it.

---

## Information Architecture Anti-Patterns

### Org Chart Navigation
**What it looks like**: A product's navigation structure mirrors the company's org chart (Sales / Marketing / Operations / Finance).
**Why it fails**: Users think in terms of their tasks and goals, not the company's internal structure.
**Fix**: Design navigation from a user task perspective. Card sorting and tree testing are the standard methods for validating IA.

### Inconsistent Terminology
**What it looks like**: The same concept called "Project" in one part of the app and "Workspace" in another.
**Why it fails**: Users develop an unstable mental model. They're never sure if "Project" and "Workspace" are the same thing or different.
**Fix**: Maintain a terminology glossary. Every feature, object, and action should have one canonical name used consistently throughout the entire product.
