# AI-Assisted Engineering Playbook  
## Agentic Software Engineering Framework

A practical, repeatable operating model for **AI-assisted software engineering** — designed to ship faster **without sacrificing architecture, security, or quality**.

This repository is intentionally **language/framework agnostic**. It focuses on the operating system: **rules → tasks → execution → review → verification → learning loops**.

---

## What this is

This repo documents an **Agentic Software Engineering Framework** I use to build complex systems with AI support while maintaining:

- **Architecture integrity** (boundaries and consistency)
- **Governance** (guardrails to prevent drift)
- **Quality** (tests + review discipline)
- **Traceability** (decision logs and debugging loops)
- **Security & privacy** (safe prompting and redaction)

AI is treated as an acceleration layer — not a replacement for engineering judgment.

---

## Philosophy

AI should **augment engineering**, not replace it.

The goal is to enable **fast iteration with reliable outcomes**, by enforcing:

- structured development workflows  
- architecture-first thinking  
- reuse-first discipline  
- human confirmation gates  
- verification-driven delivery (tests + manual checks)

---

## AI-Assisted Engineering Workflow

![workflow](assets/workflow.png)

A structured loop:

**Rules → Goals → Tasks → Execute (AI-assisted) → Review → Verify → Log → Iterate**

Key ideas:

- **Rules** define architectural constraints and engineering standards.
- **Goals** define outcomes and success criteria.
- **Tasks** break work into small, verifiable units.
- **AI tools** accelerate implementation and analysis.
- **Review + verification** ensure correctness and safety.
- **Logs** capture decisions and learnings to improve the workflow.

---

## Tooling matrix (practical use)

This framework is tool-agnostic, but different tools tend to be best at different steps.

| Workflow Step | Best Tool Type | Examples |
|---|---|---|
| PRD/spec → breakdown (stories/tasks) | Reasoning model | Claude |
| Small task implementation | IDE agent + code model | Cursor + OpenAI |
| Governance and consistency checks | Rules enforcement agent | Antigravity |
| Debugging and root cause analysis | IDE agent + reasoning model | Cursor + Claude |
| Documentation and technical writing | Reasoning model | Claude |

**Important:** tools assist execution; architecture and correctness remain human-owned.

---

## Contents

### Documentation (`docs/`)
- `docs/01-overview.md`
- `docs/02-ai-assisted-development-model.md`
- `docs/03-architecture-first-development.md`
- `docs/04-task-driven-engineering.md`
- `docs/05-code-review-and-quality.md`
- `docs/06-debugging-and-incident-response.md`
- `docs/07-security-and-privacy.md`
- `docs/08-example-sprints.md`

### Prompts (`prompts/`)
**PRD breakdown**
- `prompts/prd-breakdown/prd-to-stories.md`
- `prompts/prd-breakdown/stories-to-tasks.md`

**Implementation**
- `prompts/implementation/implementation-agent.md`
- `prompts/implementation/bugfix-agent.md`

**Governance**
- `prompts/governance/rules-enforcement.md`
- `prompts/governance/architecture-check.md`

### Templates (`templates/`)
- `templates/prompt-template.md`
- `templates/prd-template.md`
- `templates/story-template.md`
- `templates/task-template.md`
- `templates/architecture-review-template.md`
- `templates/pr-review-template.md`
- `templates/incident-template.md`

### Examples (`examples/`)
- `examples/bugfix-walkthrough.md`

---

## How to use this repo

### 1) Start with rules and boundaries
Before using any AI tool, define:
- architecture boundaries
- constraints (security/performance/compliance)
- what is in-scope vs out-of-scope

### 2) Break the work into small tasks
Use:
- `templates/task-template.md`
- `prompts/prd-breakdown/*`

The smaller the task, the better AI performs.

### 3) Execute with AI assistance
Use:
- Cursor for code navigation + implementation
- Claude/OpenAI to generate drafts and alternatives
- Antigravity to enforce rules and consistency

### 4) Review and verify before merge
Use:
- `templates/pr-review-template.md`
- tests + manual verification steps

### 5) Log learnings and improve prompts
Treat prompts and templates as versioned engineering assets.

---

## Who this is for

This playbook is intended for:

- software architects
- staff/principal engineers
- solutions and platform architects
- engineering teams adopting AI-assisted development responsibly

---

## License

MIT