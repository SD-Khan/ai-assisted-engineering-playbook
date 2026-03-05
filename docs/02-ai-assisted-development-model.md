# AI-Assisted Development Model

This framework is **tool-agnostic**, but assumes you may use a combination of:
- IDE agents (e.g., Cursor)
- reasoning models (e.g., Claude)
- code-generation models (e.g., OpenAI)
- governance enforcement tools (e.g., Antigravity)

The key is not the tool — it’s the **operating model**.

---

## Tool Roles (conceptual)

### IDE Agent
Best for:
- navigating codebases
- implementing small tasks
- local refactors
- writing tests quickly

### Reasoning Model
Best for:
- PRD breakdown
- architecture tradeoffs
- edge case exploration
- review critique

### Code Generation Model
Best for:
- scaffolding
- boilerplate and repetitive code
- structured outputs (when constrained)

### Governance Agent
Best for:
- enforcing constraints
- preventing drift
- consistency checks across the repo/process

---

## Tooling Matrix (Practical Use)

| Workflow Step | Best Tool Type | Notes |
|---|---|---|
| Planning (PRD → stories/tasks) | Reasoning model | Strong decomposition, constraints, acceptance criteria |
| Implementation (small tasks) | IDE agent + code model | Fast edits, scaffolding, tests |
| Reviews & consistency | Governance agent | Enforces rules, prevents drift, checks boundaries |
| Debugging | IDE agent + reasoning model | Use logs + reproduction; validate fixes with tests |
| Documentation | Reasoning model | Structured technical writing and clarity |

**Important:** tools assist execution; architecture and correctness remain human-owned.

---

## Golden Rules

1) **AI output is untrusted until reviewed**  
2) **Architecture decisions are human-led**  
3) **Small tasks reduce hallucination and improve quality**  
4) **All changes require verification** (tests + manual steps)  
5) **No secrets or sensitive data in prompts**  