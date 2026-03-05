# Debugging & Incident Response

AI can accelerate debugging, but only if you provide evidence:
- logs
- reproduction steps
- failure conditions
- recent changes

---

## Debugging workflow

1) Restate the bug in one sentence  
2) Reproduce (or define how to validate without reproduction)  
3) Scope blast radius (who/what is impacted)  
4) Identify root cause (evidence-driven)  
5) Propose minimal fix options  
6) Implement fix + regression test  
7) Verify  
8) Document learnings  

---

## Incident response mindset

For critical issues:
- prioritize containment
- communicate clearly
- avoid risky refactors
- create a post-incident prevention plan

---

## Output discipline

A bugfix is not complete until:
- the root cause is explained
- the fix is minimal and safe
- regression tests exist
- verification steps are documented