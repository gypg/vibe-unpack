# Optimization Proposal for vibe-unpack

**Date**: 2026-07-31  
**Based on**: Full analysis of 7 reference projects (khazix-skills, vibe-hub-skill, rnskill, Vibe-Skills, etc.)

---

## 1. Current Status Summary

We have completed a major structural cleanup:
- `vibe-unpack/` is now a clean, independent top-level development subject.
- `docs/`, `references/`, `archive/` are also clean top-level folders.
- All 7 recommended reference projects are fully cloned in `references/`.

The core positioning is correct: **upstream demand sculptor** for completely fuzzy non-technical input.

However, after studying the references, we can make significant improvements in three areas:
1. Output strictness and defensiveness (prevent rot)
2. Questioning discipline and anti-vague-language mechanisms
3. Clear differentiation from existing tools

---

## 2. Key Learnings from References (Prioritized)

### 2.1 Highest Value: khazix-skills (leader)
- Role clarity (Leader / Manager / Executor)
- "我替领导拍的板" section — explicitly list assumptions and decisions made by the unpacker
- "法与情报" distinction
- "防五种死法" (anti-cheat, hallucination, amnesia, tunnel vision, silent failure)
- Extreme minimalism at delivery time (only 3 things)
- Hard constraints on output (character limit, one-shot)

### 2.2 High Value: vibe-hub-skill (vibehub)
- "Complete the task first, then surface terminology"
- Turn colloquial description into directly usable professional requirement
- Very disciplined: max 1-3 terms, only when they matter for the next step

### 2.3 High Value: rnskill (dbs-goal and similar)
- Strong anti-empty-language philosophy
- Family resemblance checklist for "good goal"
- Very explicit "what makes something checkable"

---

## 3. Prioritized Improvement Areas

### Tier 1 (Do First)
- Make final output contract much stricter (only 3 things, no process noise)
- Add explicit "Assumptions & Default Decisions" section
- Add "Demand Rot Prevention" mechanism (empty language, unverifiable criteria, hidden scope, maintenance lies)
- Strengthen questioning discipline (limit per round, detect empty language early)

### Tier 2 (Next)
- Update `demand-spec.md` template with new sections
- Add short "Next Agent Quick Guide" at the top of outputs
- Clarify positioning vs khazix leader / vibe-hub in READMEs

### Tier 3 (Later)
- Tooling (Mermaid generation, rot checker)
- More cases

---

## 4. What We Should NOT Do
- Do not become another execution-layer skill like rnskill or canghe-skills
- Do not copy khazix leader's full "task brief" role (we stay more upstream)
- Do not over-engineer visualization before core logic is solid

---

## 5. Recommended Immediate Actions

1. Revise `vibe-unpack/SKILL.md` (output contract + rot prevention + discipline)
2. Update the `demand-spec.md` template definition
3. Update root README + `vibe-unpack/README.md` for positioning and structure
4. Clean up internal references in docs (paths, structure)

This document is the proposal. Execution happens by updating the actual files in `vibe-unpack/`, `docs/`, and root READMEs.
