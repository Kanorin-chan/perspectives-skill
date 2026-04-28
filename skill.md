---
name: perspectives
description: Use when evaluating any design, feature, decision, code, or idea from multiple viewpoints — trigger on "perspective," "what would X think," "how would people react," "evaluate this," "look at this from different angles"
---

# Perspectives

Evaluate anything through the eyes of multiple relevant personas. Dynamically casts perspectives that fit the situation. Domain-agnostic.

**Announce at start:** "Using perspectives to evaluate [subject] from multiple angles."

## The Iron Law

```
PERSPECTIVES ARE GENERATED INDEPENDENTLY BEFORE SYNTHESIS.
NO COPY-PASTE OPINIONS. EACH PERSONA THINKS FOR THEMSELVES.
IF ALL PERSPECTIVES AGREE, RE-CAST WITH MORE CONTRAST.
```

## Three Tiers

| Tier | Name | When | What |
|------|------|------|-----|
| **T1** | Quick Council | **Default** | 4-6 personas give structured opinions inline |
| **T2** | Deep Analysis | User requests OR T1 surfaces a real concern | Frameworks + prioritized actions |
| **T3** | Execution Tier | User requests OR T2 surfaces a real concern | Sub-agents dispatched with tools — actually DO work |

T3 is **not** "deeper opinions" — it's a fundamentally different operation: real agent dispatch with file I/O, web search, and tool use. Treat it as such.

### Escalation Rule

<HARD-GATE>
Escalation happens ONLY when the current tier surfaced a specific, articulable concern. State WHAT worried you and WHY going deeper would help.

If the current tier finds nothing alarming → Done. Stop. No upsell.
Never routinely ask "want me to go deeper?"
</HARD-GATE>

## Process

### Step 1: Intake

#### Phase 1A: Identify the Subject

- **Domain** — code, game design, business, UI, product, personal decision, etc.
- **Subject** — what specific thing are we evaluating?
- **Tier** — user-requested, else default T1.

If the user says just "perspectives" with no subject, infer it from conversation context.

#### Phase 1B: Calibration

<HARD-GATE>
Do NOT cast perspectives without knowing WHY the user is asking.
</HARD-GATE>

Match depth to subject:

- **Casual subjects** ("should I get a cat?", "is this color OK?") — skip Phase 1B. Trust the user. The intake gate exists to prevent shallow analysis on serious questions, not to interrogate small ones.
- **Most subjects** — ONE calibration question is enough:
  > "Quick check before I cast — are you [questioning a choice / seeking validation / blind-spot checking / just curious]? Anything I should know about constraints (budget, audience, hard requirements)?"
- **Technical subjects** (hardware, code, performance) — confirm hard facts before assuming defaults. If you catch yourself writing "assuming X..." — STOP. Ask.
- **Personal/emotional subjects** — the backstory IS the subject. Ask about intent and feelings.

### Step 2: Cast

Select 4-6 perspectives. See `persona-engine.md` for the dimension catalog and selection rules.

For each persona present:
- **Name** — short, vivid label (not "User A")
- **Who** — 1-2 sentences: background, mindset, what they care about
- **Why here** — why their opinion matters for THIS subject

At least one adversarial perspective. At least one the user probably hasn't considered.

Wait for user to confirm, modify, or swap personas.

### Step 3: Analyze (T1)

For each persona, independently generate:

1. **Who I am** (1 line)
2. **Honest reaction** — speak AS this person. Authentic > diplomatic. Don't soften.
3. **What I'd actually do** — behavior, not just opinion. Bounce? Complain? Workaround? Love it?
4. **Verdict** — 👍 / 👎 / 🤷 with a one-sentence reason

3-5 sentences per persona. This is a quick council, not an essay.

### Step 4: Synthesize

- **Consensus** — what most agree on (if anything)
- **Conflicts** — where perspectives clash. These ARE the interesting design tensions.
- **Blind spots** — what the user likely didn't consider

### Step 5: Recommendation

Direct stance based on the full picture. Take a position.

---

## T2: Deep Analysis

Triggered by explicit request OR earned escalation from T1.

See `frameworks.md` for the framework catalog.

**Additional steps:**

1. **Framework Selection** — pick 1-2 that fit:
   - Decisions → Six Thinking Hats / Devil's Advocate
   - Plans/launches → Pre-Mortem
   - UX/flows → Empathy Map + Cognitive Walkthrough
   - Security/robustness → Red/Blue Team
   - Multi-stakeholder → Stakeholder Analysis
   - Creative features → Disney Strategy

2. **Structured findings** — typed output per the framework, not free opinions.

3. **Action items** — see `action-translator.md`. Every finding becomes:
   `FINDING → IMPACT → SEVERITY → SPECIFIC ACTION → EFFORT`

4. **Prioritized roadmap:**
   - 🔴 Fix now (Critical)
   - 🟡 Fix next (Major, workarounds exist)
   - 🟢 Schedule (Minor)
   - 💡 Consider (Enhancement)

---

## T3: Execution Tier

Triggered by explicit request OR earned escalation from T2.

See `agents/` for each agent's prompt and protocol.

| Agent | What It Does |
|-------|-------------|
| `code-reviewer` | Reads code, greps patterns, flags issues with file:line |
| `security-analyst` | OWASP top 10, injection, auth issues |
| `ui-auditor` | Screenshots, contrast, keyboard nav, layout |
| `test-writer` | Edge-case tests informed by persona concerns |
| `researcher` | Web searches competitors, best practices |
| `doc-tester` | Follows docs as a new user, flags confusion |
| `performance-auditor` | Bundle sizes, load times, rendering cost |

### T3 Cost Gate

<HARD-GATE>
Before dispatching, the user MUST see the cost warning and explicitly confirm. Never dispatch on ambiguous responses.

> **Heads up — T3 is heavy.**
> About to dispatch **[N] agents in parallel**. Each independently explores the codebase and runs searches. This means:
> - **~[N × 30-70] tool calls** total
> - **Large context usage** — each agent builds its own deep understanding
> - **~2-5 minutes** wall clock
> - Long synthesis report
>
> The most expensive operation in this skill. Worth it for real projects, overkill for quick questions.
>
> **Ready to dispatch?**

"go", "yes", "do it" = confirmed. Anything else → stop and clarify.
</HARD-GATE>

### Dispatch

1. Select agents based on T1/T2 findings.
2. Present selection for user confirmation.
3. Show the cost warning above.
4. On confirmation, dispatch in parallel via the Agent tool.
5. Each agent gets constructed context inline — never tell them "read the conversation."
6. Each agent reports back: Findings, Severity, Recommended Actions.
7. Synthesize across all agents — patterns, conflicts, compound issues.
8. Optionally execute fixes if user approves.

---

## Rules

- **Dynamic casting** — every subject gets fresh personas. No reuse without rethinking.
- **Authentic voice** — frustrated people sound frustrated. A 70-year-old sounds different from a 15-year-old. Don't homogenize.
- **Concise by default** — T1 is 3-5 sentences per persona.
- **User controls depth** — they can stop, escalate, or add personas at any tier.
- **No domain lock** — works for code, UI, game design, business, personal choices, writing, architecture.

## Anti-Patterns

### Intake

| Thought | Reality |
|---------|---------|
| "I know enough to start casting" | Did you confirm hard facts? Did you ask why they're here? If not, you're guessing. |
| "Assuming standard/default specs..." | STOP. Ask. Wrong assumptions invalidate the whole council. |
| "The subject is straightforward, no backstory needed" | WHY they're asking changes WHO matters. |
| "Asking too many questions will annoy the user" | One focused calibration question is fine. Wrong assumptions annoy more. |
| "I'll over-interrogate to be safe" | For "should I get a cat," skip Phase 1B. Match depth to subject. |

### Analysis

| Thought | Reality |
|---------|---------|
| "All perspectives agree, we're done" | Homogeneous agreement = bad casting. Re-cast with more contrast. |
| "Let me soften this perspective's criticism" | Authentic > diplomatic. |
| "I'll skip the adversarial perspective" | The adversary finds the blind spots. Never skip. |
| "Let me suggest T2 just in case" | No upsell without articulated cause. |
| "This persona wouldn't have strong feelings" | Then pick a better persona. Everyone on the council should care. |
| "I'll reuse the personas from last time" | Every subject gets fresh casting. |

## Integration

- **Chains well with:** `superpowers:brainstorming` (during design phase), `superpowers:writing-plans` (review a plan before execution), `superpowers:test-driven-development` (T3 test-writer agent).
- **After perspectives:** user decides next step. Don't auto-chain.
