# Agent Rules for Complex Project

These rules apply to all AI agents involved in the development of the Statuz project.

---

## Rule 1: Evaluate Plans Against the Most Stringent Standards

**Trigger:** Any discussion involving new features or architecture.

**Execution Requirements:**

- Every plan must answer: Is this explicitly requested by the user, or does the agent assume it is needed?
- Every plan must answer: Is this feature creep? Does it exceed the scope defined for the current phase?
- Every plan must answer: If we don’t do this, can the project still proceed?
- Every plan must answer: What is the acceptance criteria for this plan? How will completion be demonstrated?

**Prohibited Actions:**

- Do not assume the user needs a feature.
- Do not add "improvements" without user confirmation.
- Do not expand the architecture without validation.
- Do not use "might need later" as justification.

**Judgment Criteria:**

```text
If the answer is:
- Explicitly requested by user → Proceed
- Defined in AGENTS.md / Roadmap.md → Proceed
- Thought up by the agent → Must ask the user first
- Documented as "won’t do" → Stop immediately
```

---

## Rule 2: Recalibrate Positioning at the End of Every Conversation

**Trigger:** End of each conversation.

**Execution Requirements:**

At the end of each conversation, the agent must output positioning calibration in the following format:

```markdown
## 📍 Positioning Calibration

### Current Status
- Completed: [What was specifically completed]
- In Progress: [What is currently being worked on]
- Pending: [What is clearly the next step]

### Vision vs. Reality
- [Point out the gap between current implementation and the vision, using the harshest language]

### Risks & Blockers
- [List current risks, blockers, and uncertainties]

### Decision Points
- [List issues requiring user decisions; do not make decisions on behalf of the user]

### Next Options
- [List 2–4 optional next directions for the user to choose from]
```

**Prohibited Actions:**

- Do not say "task completed" at the end of a conversation without calibrating.
- Do not assume the next step without asking the user.
- Do not hide risks or gaps.
- Do not make strategic decisions for the user.

---

## Rule 3: Adhere to Project Boundaries

**Must Comply With:**

- P0/P1/P2 priorities defined in AGENTS.md.
- "Things Agents Must Not Do" defined in AGENTS.md.
- Phase goals defined in ROADMAP.md.
- Protocol boundaries defined in SPEC.md.

**Boundary Violations Prohibited:**

- Do not implement P1/P2 features during the P0 phase.
- Do not add an MCP Server (explicitly prohibited in P0).
- Do not add a Web Dashboard (explicitly prohibited in P0).
- Do not add Embeddings (explicitly prohibited in P0).
- Do not change the License (requires explicit user approval).

---

## Rule 4: Code Quality Standards

**Must Do:**

- Read relevant files before modifying code.
- Run build and tests after each change.
- Do not leave unresolved TypeScript errors.
- Do not leave failing tests.

**Prohibited Actions:**

- Do not claim feature completion without testing.
- Do not commit code with a failing build.
- Do not add unnecessary dependencies.
- Do not introduce network calls (prohibited in P0).

---

## Rule 5: Documentation Honesty Principle

**Must Do:**

- Documented features must match the actual code implementation.
- If the code does not implement a feature, the documentation must clearly mark it as "Not Implemented" or "Planned."
- If a feature is incomplete, the documentation must state its limitations.

**Prohibited Actions:**

- Do not claim "supports X feature" in documentation when the code is empty.
- Do not use "coming soon" to hide that work has not started.
- Do not prettify gaps.

---

## Execution Checklist

At the start of each conversation, the agent should self-check:

```text
□ Have I understood the user’s real intent?
□ Have I checked the boundaries in AGENTS.md?
□ Have I evaluated the plan against the most stringent standards?
□ Am I prepared to calibrate positioning at the end?
```

At the end of each conversation, the agent must output positioning calibration.
