# Optimization Proposal for vibe-unpack

**Date**: 2026-07-31  
**Status**: Draft  
**Based on**: Complete clones of Grok-recommended reference projects (khazix-skills, vibe-hub-skill, rnskill, Vibe-Skills, etc.)

---

## 1. Executive Summary

vibe-unpack is correctly positioned as an **upstream "demand sculptor"** tool: turning a non-technical person's fuzzy feeling/scene/emotion into a clear, constraint-aware, verifiable demand graph and specification.

The reference projects confirm we are **not duplicating existing work** but filling a genuine gap. However, we can significantly improve clarity, actionability, and anti-rot mechanisms by borrowing patterns from the best references (especially khazix's `leader` and vibe-hub's `vibehub`).

**Core recommended direction**:
- Keep the current "fuzzy → structured demand" focus.
- Make outputs much more executable and defensive (borrow heavily from khazix).
- Strengthen the "vague language detection" and boundary declaration style (borrow from rnskill and vibe-hub).
- Improve the final delivery format (extreme minimalism + clear "what the next agent should do").

---

## 2. Key Insights from References (Ranked by Immediate Value)

### 2.1 Highest Value — khazix-skills / leader
- Extremely clear role separation (Leader / Manager / Executor).
- "我替领导拍的板" section — explicitly surface assumptions and decisions the unpacker made.
- "法与情报" distinction (rules that must be followed vs suggestions).
- "防五种死法" (anti-cheat, hallucinated commands, amnesia, tunnel vision, silent failures) — this is gold for making demand output robust.
- Extreme output minimalism: only deliver 3 things at the end.
- Hard constraints (character limits, one-shot delivery).

**Action**: We should add similar defensive mechanisms and a dedicated "Assumptions & Default Decisions" section.

### 2.2 High Value — vibe-hub-skill / vibehub
- "Do the task first, then naturally surface the right terminology."
- Turn vague colloquial description into directly usable professional requirement.
- Very disciplined: at most 1-3 terms, only when they materially affect the next step.

**Action**: Apply similar "clarify while doing" mindset and "max N terms" discipline in our questioning and output.

### 2.3 High Value — rnskill (especially dbs-goal and similar)
- Strong "anti-empty-language" philosophy (维特根斯坦 engine idling detection).
- Family resemblance checklist instead of rigid definitions.
- Very explicit "what makes a good goal" criteria that are checkable.

**Action**: Add lightweight "empty language / rot detection" during unpacking and in the success/failure definitions.

### 2.4 Useful Patterns — Vibe-Skills + others
- Many high-quality SKILL.md frontmatter examples.
- Clear "When to use" descriptions.
- Some existing clarification skills (speckit-clarify) that we can differentiate from.

---

## 3. Prioritized Recommendations

### Tier 1 — High Impact, Should Do Soon

**1. Strengthen Output Contract (Biggest win)**
- Make final delivery much stricter (inspired by khazix).
- Add a prominent "Assumptions & Default Decisions" section in `demand-spec.md`.
- Consider adding a very short "Next Agent Instructions" block at the top of the output.

**2. Add Defensive / Anti-Rot Mechanisms**
- Borrow khazix's "five ways to die" idea.
- Add explicit checks during unpacking for:
  - Empty/vague language ("better", "like Xiaohongshu", "valuable")
  - Unverifiable success criteria
  - Hidden scope creep
  - Unrealistic maintenance assumptions

**3. Improve Questioning Discipline**
- Limit questions per round (khazix does ≤5).
- Prioritize: Constraints > Concrete pain moments > Success/Failure definitions > Assumptions.
- Add "empty language detection" as an explicit step before asking.

**4. Clarify Positioning vs Existing Work**
- Explicitly document in README + SKILL.md how we differ from:
  - khazix `leader` (we are more upstream)
  - Existing clarification skills (we are more for completely fuzzy non-technical input)
- This prevents future confusion and helps users understand when to use us.

### Tier 2 — Valuable Polish

**5. Output Format Improvements**
- Make `demand-spec.md` template have stronger "human first" sections at the top.
- Consider producing a very short "one-pager" summary in addition to the full spec (for the human).

**6. Better Role Framing Inside SKILL.md**
- Explicitly state that we are acting as "Demand Manager" — the next agent(s) will treat our output as frozen truth.

**7. Leverage Good Examples from References**
- Study rnskill's clear "can/cannot/quality standard" language.
- Study how khazix keeps language extremely concrete and low-jargon for the human.

### Tier 3 — Nice to Have Later

- Automated generation of Mermaid from the graph (or better templates).
- Add a lightweight "rot detection" checklist that can be run later on existing specs.
- Create a "vibe-unpack vs khazix-leader" comparison note for users.

---

## 4. Suggested Immediate Next Actions (My Proposed Priority)

1. **Rewrite key parts of SKILL.md** (Output contract + defensive mechanisms + questioning discipline).
2. **Update `demand-spec.md` template** with the new "Assumptions & Default Decisions" section + stronger top-level guidance.
3. **Improve root README + vibe-unpack/README.md** to clearly state positioning and new structure.
4. **Create a small "Anti-Rot Checklist"** (can live in design/ or as part of SKILL.md).
5. Clean up and document the current folder structure (this document itself helps).

---

## 5. What We Should *Not* Do (For Now)

- Do not start copying execution patterns from rnskill or Vibe-Skills (those are downstream).
- Do not try to become a full "goal writing" tool like khazix leader (we stay upstream).
- Avoid over-engineering visualization or tooling until the core logic and output quality is stronger.

---

**Next step recommendation**: Start with item 1 and 2 above (SKILL.md + demand-spec template). These two changes will have the highest immediate impact on the quality of what vibe-unpack produces.

Would you like me to start drafting the updated sections for SKILL.md and the new demand-spec template now?
