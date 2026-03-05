# Architecture-First Development

AI accelerates implementation, but it cannot replace architectural judgment.

This framework treats architecture as the primary constraint that shapes tasks, prompts, and reviews.

---

## Architecture principles

### 1) Boundaries first
Always clarify:
- what belongs in UI/presentation
- what belongs in application/services
- what belongs in domain logic
- what belongs in data access
- what belongs in infrastructure

### 2) Keep modules explicit
Prefer clean modules with strict ownership, even inside a single codebase.

### 3) Optimize for evolution
Use structure that can evolve:
- from POC/MVP → production
- from modular monolith → microservices (when needed)

---

## Modular monolith

For POC/MVP phases, a **modular monolith** is often ideal:
- faster iteration
- lower operational overhead
- easier debugging
- keeps complexity contained

However, it must be built with:
- strict module boundaries
- clear interfaces/contracts
- minimal coupling

This makes it feasible to extract services later when:
- scale demands it
- teams grow
- independent deployability becomes necessary

---

## When to evolve to microservices

Move toward microservices when you see:
- heavy independent scaling needs
- teams blocked by deploy coupling
- clear domain boundaries with stable contracts
- operational maturity to handle distributed systems

---

## Architecture checklist

- boundaries respected?
- no cross-layer shortcuts?
- data access isolated?
- external dependencies behind adapters/clients?
- observability built-in?
- security checks enforced where needed?