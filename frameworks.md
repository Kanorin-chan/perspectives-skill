# Analysis Frameworks

These frameworks add structure to perspective analysis. Used in T2 (Deep Analysis) and T3 (Advanced Perspectives). Each framework produces a specific type of output — pick the one that matches what the subject needs.

## Framework Selection Guide

| If the subject is... | Use... | Because... |
|---------------------|--------|------------|
| A decision between options | **Six Thinking Hats** | Separates facts, feelings, risks, benefits, alternatives |
| A plan or launch about to happen | **Pre-Mortem** | Surfaces failure modes before they happen |
| Something that needs to be robust/secure | **Red Team / Blue Team** | Adversarial testing finds what optimistic review misses |
| A user experience or flow | **Empathy Map** + **Cognitive Walkthrough** | Captures what users think vs. do, and step-by-step friction |
| Something affecting many groups differently | **Stakeholder Analysis** | Weights perspectives by power and interest |
| A consensus that feels too easy | **Devil's Advocate** | Strongest possible case against, to stress-test conviction |
| A creative feature or new idea | **Disney Strategy** | Dream → Reality-check → Critique cycle |

You can combine frameworks. Example: Run a Pre-Mortem, then use Red Team to probe the scariest failure modes.

---

## Six Thinking Hats

**Best for:** Decisions, evaluations, any subject that needs balanced analysis.

Run each "hat" sequentially. Each produces a different output type:

| Hat | Focus | Output |
|-----|-------|--------|
| ⚪ **White** | Facts only | What data do we have? What's missing? What do we know for certain? |
| 🔴 **Red** | Feelings | Gut reactions. First impressions. What feels right/wrong? No justification needed. |
| ⚫ **Black** | Risks | What could go wrong? What are the dangers? Where are the weaknesses? |
| 🟡 **Yellow** | Benefits | What's good about this? What's the best-case outcome? Why might it work? |
| 🟢 **Green** | Alternatives | What else could we do? Creative options. "What if..." |
| 🔵 **Blue** | Process | What did we learn? What's the next step? What decision do we make? |

**Rules:**
- Run hats in order. Don't mix.
- Each hat gets its own section. Don't blend optimism into the risk section.
- White Hat must be genuinely factual — no opinions disguised as facts.
- Red Hat gets to be irrational. That's the point.
- Black Hat must be specific, not vague doom ("it might fail" → HOW would it fail?).

---

## Pre-Mortem

**Best for:** Plans, launches, major changes, anything about to ship.

**The framing trick:** "It is 6 months from now. This has failed spectacularly. Why?"

**Process:**
1. State the premise: "Imagine [the subject] has been live for 6 months and it's been a disaster."
2. For each persona, independently generate: "What went wrong from my perspective?"
3. Each persona identifies 2-3 specific failure modes they'd experience
4. Collect all failure modes
5. De-duplicate and group by theme
6. For each failure mode: assess likelihood (High/Medium/Low) and impact (Critical/Major/Minor)
7. Generate preventive actions for the top failures

**Output format per persona:**
```
[Persona Name]: "Here's why it failed for me..."
- Failure mode 1: [specific scenario]
- Failure mode 2: [specific scenario]
- What I wish they'd done instead: [preventive action]
```

---

## Red Team / Blue Team

**Best for:** Security, robustness, edge cases, anything that needs to survive adversarial conditions.

**Three roles:**

| Role | Mindset | Output |
|------|---------|--------|
| **Red Team** | "How do I break this?" | Attack vectors, exploit paths, abuse scenarios |
| **Blue Team** | "How do I defend this?" | Detection methods, guards, fallbacks |
| **Purple Team** | "How do we translate this into improvements?" | Prioritized remediation roadmap |

**Process:**
1. Red Team identifies 3-5 attack vectors / abuse scenarios / breaking points
2. Blue Team responds to each: can it be detected? prevented? mitigated?
3. Purple Team synthesizes: what needs to change, in what priority order?

**For non-security subjects,** the Red/Blue framing still works:
- Red Team: "How would a hostile user / bad actor / extreme edge case break this?"
- Blue Team: "How do we handle that gracefully?"
- Purple Team: "What do we actually need to build/change?"

---

## Empathy Map

**Best for:** UX, player experience, customer journey, any user-facing subject.

For each persona, fill four quadrants:

| Quadrant | Content |
|----------|---------|
| **Says** | What they'd literally say out loud. Direct quotes. |
| **Thinks** | Internal thoughts they might not voice. Hidden concerns. |
| **Does** | Observable behavior. What they'd actually do (which may contradict what they say). |
| **Feels** | Emotions. Frustrations, anxieties, excitement, confusion. |

**The gap between Says and Does is where the gold is.** People say "I'd read the documentation" but actually google the error message. People say "I don't care about cosmetics" but spend hours customizing their character.

---

## Cognitive Walkthrough

**Best for:** UI flows, onboarding, tutorials, any step-by-step experience.

Walk through the experience step by step as a specific persona. At each step, answer:

1. **Will they know what to do?** — Is the next action obvious?
2. **Will they see how to do it?** — Is the control visible and recognizable?
3. **Will they understand the feedback?** — After acting, do they know it worked?
4. **Will they want to continue?** — Is there enough motivation to proceed?

If any answer is "no" → that's a friction point. Document it with:
- Which step
- Which question failed
- Why (from this persona's perspective)
- Suggested fix

---

## Stakeholder Analysis

**Best for:** Multi-party decisions, features affecting many different groups.

### Power/Interest Grid

Map each perspective on two axes:

| | High Interest | Low Interest |
|---|---|---|
| **High Power** | **Manage Closely** — Deep engagement, co-creation | **Keep Satisfied** — High-level updates |
| **Low Power** | **Keep Informed** — Regular updates, they care but can't block | **Monitor** — Minimal attention |

**Then for each quadrant:**
- Manage Closely: Full perspective analysis, their concerns drive the design
- Keep Satisfied: Surface-level check, don't let them be surprised
- Keep Informed: Include their perspective but they don't get veto power
- Monitor: Note their existence but don't optimize for them

This framework prevents the mistake of treating all perspectives as equally important.

---

## Devil's Advocate

**Best for:** When consensus feels too easy, when everyone agrees and that's suspicious.

**Rules:**
- Construct the **strongest possible case against** the subject
- Not token objections — genuine, well-reasoned opposition
- Find the best alternative that was rejected and argue for it
- Attack the assumptions, not just the conclusions
- After the devil's case: what survives? What needs to change?

**The test of quality:** Would someone who genuinely disagreed nod along with this argument? If it's a strawman, redo it.

---

## Disney Strategy

**Best for:** Creative features, new ideas, blue-sky thinking.

Three phases, each in a separate mental space:

| Phase | Role | Mindset | Output |
|-------|------|---------|--------|
| 1 | **Dreamer** | No constraints. "What if anything were possible?" | Wild ideas, aspirational vision |
| 2 | **Realist** | Practical. "How would we actually build this?" | Feasibility, resources, timeline, steps |
| 3 | **Critic** | Constructive challenge. "What's wrong with this plan?" | Risks, gaps, missing pieces |

**Critical rule:** The Critic CANNOT speak during the Dreamer phase. The Dreamer CANNOT be constrained by the Realist. Separate the phases completely.

**Cycle:** Critic findings feed back to the Dreamer for creative solutions to the problems found. Repeat until the Critic has no remaining objections that the Realist can't address.
