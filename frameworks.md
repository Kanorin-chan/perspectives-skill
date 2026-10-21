# Analysis Frameworks

Frameworks give STRUCTURE to collision. They're T2 tools — use them when the collision reveals something that needs systematic exploration. Skip them when the collision already produced clarity.

## When to Use vs Skip

**Use a framework when:**
- The collision surfaced a tension that's too complex to resolve by feel
- You need to systematically explore a space (not just react)
- Multiple stakeholders need to see structured reasoning

**Skip the framework when:**
- The collision already crystallized the decision
- The subject is simple enough that the collision map IS the answer
- Adding structure would be busy-work, not insight

Frameworks serve the insight. If the insight already arrived, don't force a framework to justify it.

---

## Framework Selection

| If the subject is... | Use... | It gives you... |
|---------------------|--------|-----------------|
| A decision between options | **Six Thinking Hats** | Separated analysis — facts/feelings/risks/alternatives |
| A plan about to ship | **Pre-Mortem** | Failure modes before they happen |
| Something that must survive adversaries | **Red/Blue Team** | Attack vectors + defenses |
| A user experience or flow | **Empathy Map** + **Cognitive Walkthrough** | What users think vs do, step-by-step friction |
| Something affecting many groups | **Stakeholder Analysis** | Weighted perspectives by power/interest |
| A consensus that feels too easy | **Devil's Advocate** | Strongest possible case against |
| A creative idea that needs grounding | **Disney Strategy** | Dream → Reality → Critique cycle |

Combine when needed. Pre-Mortem + Red Team works well for high-stakes launches.

---

## Six Thinking Hats

**Best for:** Decisions, evaluations, balanced analysis.

| Hat | Focus | Output |
|-----|-------|--------|
| ⚪ White | Facts only | What do we know for certain? What's missing? |
| 🔴 Red | Feelings | Gut reactions. No justification needed. |
| ⚫ Black | Risks | What could go wrong? HOW specifically? |
| 🟡 Yellow | Benefits | Best-case outcome. Why might it work? |
| 🟢 Green | Alternatives | What else could we do? |
| 🔵 Blue | Decision | What did we learn? What's the move? |

Rules: Run in order. Don't mix. White must be genuinely factual. Red gets to be irrational. Black must be specific ("HOW would it fail?" not "it might fail").

---

## Pre-Mortem

**Best for:** Plans, launches, anything about to ship.

**The frame:** "It's 6 months from now. This failed spectacularly. Why?"

Process:
1. Each persona independently answers: "What went wrong from MY perspective?"
2. Each identifies 2-3 specific failure modes
3. Collect, de-duplicate, group by theme
4. Assess: likelihood (High/Med/Low) × impact (Critical/Major/Minor)
5. Generate preventive actions for the top failures

Output per persona:
```
[Name]: "Here's why it failed for me..."
- Failure mode 1: [specific scenario]
- Failure mode 2: [specific scenario]
- What I wish they'd done: [preventive action]
```

---

## Red/Blue Team

**Best for:** Security, robustness, anything that needs to survive hostile conditions.

| Role | Mindset | Output |
|------|---------|--------|
| **Red Team** | "How do I break this?" | Attack vectors, exploit paths, abuse scenarios |
| **Blue Team** | "How do I defend?" | Detection, guards, fallbacks |
| **Purple Team** | "How do we fix it?" | Prioritized remediation |

Process:
1. Red: 3-5 attack vectors / ways to break it
2. Blue: For each — can it be detected? prevented? mitigated?
3. Purple: What changes, in what priority?

Works for non-security too — "how would a hostile user / extreme edge case / bad actor break this?"

---

## Empathy Map

**Best for:** UX, player experience, customer journey.

Four quadrants per persona:

| Quadrant | Content |
|----------|---------|
| **Says** | Literal words they'd say out loud |
| **Thinks** | Internal thoughts they won't voice |
| **Does** | Observable behavior (may contradict Says) |
| **Feels** | Emotions — frustration, excitement, confusion |

**The gold is in the gap between Says and Does.** People say "I'd read the docs" but actually google the error. People say "I don't care about cosmetics" but spend hours customizing.

---

## Cognitive Walkthrough

**Best for:** UI flows, onboarding, tutorials, step-by-step experiences.

Walk as a specific persona. At each step:

1. **Will they know what to do?** — Is the next action obvious?
2. **Will they see how to do it?** — Is the control visible?
3. **Will they understand the feedback?** — Do they know it worked?
4. **Will they want to continue?** — Enough motivation to proceed?

Any "no" = friction point. Document: which step, which question failed, why, suggested fix.

---

## Stakeholder Analysis

**Best for:** Multi-party decisions, features affecting many groups differently.

### Power/Interest Grid

| | High Interest | Low Interest |
|---|---|---|
| **High Power** | **Manage Closely** — co-creation | **Keep Satisfied** — high-level updates |
| **Low Power** | **Keep Informed** — they care but can't block | **Monitor** — minimal attention |

Prevents treating all perspectives as equally important. Some voices have more weight — acknowledge it.

---

## Devil's Advocate

**Best for:** When consensus feels too easy. When everyone agrees and that's suspicious.

Rules:
- Build the **strongest possible case against**
- Not token objections — genuine, reasoned opposition
- Find the best rejected alternative and argue for it
- Attack assumptions, not just conclusions

Quality test: Would someone who genuinely disagreed nod along? If it's a strawman, redo it.

---

## Disney Strategy

**Best for:** Creative features, new ideas, blue-sky thinking.

| Phase | Role | Mindset |
|-------|------|---------|
| 1 | **Dreamer** | No constraints. What if anything were possible? |
| 2 | **Realist** | How would we actually build this? |
| 3 | **Critic** | What's wrong with this plan? |

Critical rule: Phases are SEPARATED. Critic cannot speak during Dreamer. Dreamer cannot be constrained by Realist.

Cycle: Critic findings → Dreamer solves the problems creatively → Realist grounds it → Critic checks again. Repeat until Critic has no objections the Realist can't handle.
