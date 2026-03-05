# Task-Driven Engineering

AI works best when the work is decomposed into small, explicit tasks.

Large tasks create:
- unclear prompts
- messy output
- review fatigue
- higher bug risk

---

## What a good task looks like

A task is “good” when it includes:
- goal and scope
- acceptance criteria
- architecture boundary notes
- test plan
- verification steps
- rollback notes (if risky)

---

## Task decomposition rules

1) Prefer tasks that can be completed in one reviewable change  
2) One task should map to one deliverable unit (commit/PR)  
3) Tasks should be independently verifiable  
4) Dependencies must be explicit  
5) Each task should reduce uncertainty

---

## Execution loop

**Task → Prompt → Implement → Review → Test → Verify → Log → Next task**

Logging matters:
- prompts evolve
- mistakes become learnings
- the system improves over time