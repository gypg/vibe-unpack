# Optimization Plan for vibe-unpack (Prioritized)

**Date**: 2026-07-31  
**Current Structure** (after cleanup):
- `vibe-unpack/` → Development subject (core)
- `docs/` → Project-level documentation
- `references/` → External reference projects (7 complete clones)
- `archive/` → Discarded / old content

---

## Priority Order (Highest First)

### Tier 1 — Highest Impact (Do These First)

1. **Strengthen the Output Contract** (in SKILL.md)
   - Make final delivery much stricter and more minimal (inspired by khazix `leader`).
   - Add explicit "Assumptions & Default Decisions" section.
   - Define exactly what the "next agent" should receive and ignore.

2. **Add Defensive / Anti-Rot Mechanisms**
   - Borrow khazix's "five ways to die" idea.
   - Add checks for empty language, unverifiable success criteria, hidden scope, unrealistic maintenance.

3. **Improve Questioning Discipline & Flow**
   - Limit questions per round.
   - Add "empty language detection" as an explicit step.
   - Prioritize constraints and concrete pain moments higher.

4. **Clarify Positioning vs Existing Tools** (README + SKILL.md)
   - Explicitly state how we differ from khazix `leader`, vibe-hub, rnskill, etc.

### Tier 2 — Valuable Polish (Do After Tier 1)

5. Improve the `demand-spec.md` template (stronger human-first sections + new assumptions section).
6. Add a short "Next Agent Quick Guide" block that can be copied.
7. Update project READMEs to reflect new structure and positioning.

### Tier 3 — Later / Nice to Have

- Tooling for Mermaid generation
- Rot-detection checklist that can be run later
- More example cases

---

## Recommended Execution Order (What I Will Do Now)

1. **First**: Revise `vibe-unpack/SKILL.md` — focus on Output Contract + Defensive mechanisms + Questioning discipline (Tier 1 items 1-3).
2. **Second**: Update the `demand-spec.md` template inside the code (add Assumptions section + better top guidance).
3. **Third**: Improve the main READMEs for clarity on positioning.
4. Stop when the core "unpack + output" quality is noticeably stronger. We can iterate later.

---

This is the plan. I will start executing from the top.
