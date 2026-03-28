---
name: perspectives
description: Use when evaluating any design, feature, decision, code, or idea from multiple viewpoints — trigger on "perspective," "what would X think," "how would people react," "evaluate this," "look at this from different angles"
---

# Perspectives

Evaluate anything through the eyes of multiple relevant personas. Dynamically selects perspectives that fit the situation. Works across all domains — game design, software, business, UX, life decisions, anything.

**Announce at start:** "Using perspectives to evaluate [subject] from multiple angles."

## The Iron Law

```
PERSPECTIVES ARE GENERATED INDEPENDENTLY BEFORE SYNTHESIS.
NO COPY-PASTE OPINIONS. EACH PERSONA THINKS FOR THEMSELVES.
```

If all perspectives agree, your selection is too homogeneous. Re-cast.

## Three Tiers

| Tier | Name | When | How |
|------|------|------|-----|
| **T1** | Quick Council | **Default. Always.** | 4-6 personas give structured opinions inline |
| **T2** | Deep Analysis | User requests OR T1 reveals something that warrants it | Frameworks applied + prioritized action items |
| **T3** | Advanced Perspectives | User requests OR T2 findings are alarming | Sub-agents dispatched to actually DO work |

**T1 is the skill.** T2 and T3 are escalations, not the normal path.

### Escalation Rules

<HARD-GATE>
NEVER auto-escalate. NEVER routinely ask "want me to go deeper?"

Escalation happens ONLY when:
1. T1 analysis reveals a genuine concern (security risk, accessibility blocker, critical UX failure)
2. You can articulate WHAT specifically worried you
3. You explain WHY a deeper look would help

If T1 finds nothing alarming → Done. Stop. No upsell.
If T1 finds something concerning → Suggest specific escalation with reason.
Example: "The accessibility angle flagged some real issues with contrast and keyboard nav. Want me to dispatch an agent to actually audit the UI?"
</HARD-GATE>

## Process

### Step 1: Intake

Two sub-phases. Both must complete before casting.

#### Phase 1A: Identify the Subject

Read what the user brings. Identify:
- **Domain** — What world is this in? (code, game design, business, UI, product, personal decision, etc.)
- **Subject** — What specific thing are we evaluating?
- **Tier** — Did the user request a specific tier? If not, default to T1.

If the user says just "perspectives" with no subject, analyze the current conversation context and identify the subject yourself.

#### Phase 1B: Context Gathering (前因後果)

<HARD-GATE>
Do NOT cast perspectives until you understand the backstory. Evaluating something without knowing WHY the user is in this situation produces shallow, assumption-filled analysis.

If the user's message doesn't already answer these, ASK before proceeding.
</HARD-GATE>

**Understand the person:**
- **Why are you here?** — What prompted this question right now? Did something happen? Are you at a decision point?
- **What's your intent?** — Are you:
  - Questioning yourself / second-guessing a choice?
  - Looking for validation / confirmation you're on the right track?
  - Wanting honest outside perspectives / blind spot check?
  - Seeking help solving a specific problem?
  - Just curious how others would see it?
  - Bragging / showing off (valid — changes the tone entirely)?
- **What's the backstory?** — How did you get here? What led to the current state? What did you try before? What constraints forced this path?
- **What's bothering you?** — Is there a specific pain point, doubt, or frustration driving this?

**Understand the environment:**
- **What are the hard facts?** — Specs, numbers, measurements, versions, configs. Don't assume defaults.
- **What can you verify vs. what must you ask?** — If the subject involves technical details (hardware, software, settings), identify what you're assuming and CONFIRM with the user. Never build analysis on unverified assumptions.
  - Examples of things to confirm: screen resolution, OS, driver version, specific model/version, environment setup
  - If you catch yourself writing "assuming X..." — STOP. Ask instead.
- **What constraints exist?** — Budget, physical space, health limitations, time, skill level, non-negotiable preferences.

**Calibrate the analysis:**
- The answers to "why are you here?" and "what's your intent?" directly shape which perspectives matter and what tone the council should take.
- Someone questioning themselves needs honest assessment. Someone seeking help needs actionable advice. Someone bragging needs to be challenged on whether the pride is earned. Someone at a decision point needs clear tradeoff analysis.
- If the user has already done their own research, acknowledge it and focus on what they might have missed — don't repeat what they already know.

**How to gather context efficiently:**
- If the user's message already contains rich context, don't interrogate them. Extract what you can and only ask what's missing.
- Group your questions. Don't ask one at a time for Intake — this isn't brainstorming. Ask 2-4 focused questions in one message. Keep it conversational, not like a form.
- For simple/casual subjects (opinions, life choices, non-technical), you need less context. Don't over-interrogate "should I get a cat?"
- For technical subjects (hardware, code, architecture, performance), you need MORE context. Specs matter. Assumptions kill.
- For personal/emotional subjects (career, relationships, identity), ask about intent and feelings. The backstory IS the subject.

**When you have enough context, present a brief summary:**
> "Here's what I understand: [situation summary]. Your main concern is [X]. You're looking for [intent]. Is that right?"

Wait for confirmation, then proceed to casting.

### Step 2: Cast

Select 4-6 perspectives. Read `persona-engine.md` in this directory for the dimension catalog.

**How to select:**
1. Identify which 2-3 dimensions matter most for THIS subject
2. Pick personas at contrasting points along those dimensions
3. Ensure at least one adversarial perspective (someone who would hate/reject/be harmed by this)
4. Ensure at least one perspective the user probably hasn't considered

**For each persona, present:**
- **Name** — Short, vivid label (not generic like "User A")
- **Who** — 1-2 sentences: background, mindset, what they care about
- **Why here** — Why their opinion matters for THIS specific subject

**Wait for user to confirm, modify, add, or remove personas.**

### Step 3: Analyze (T1 — Quick Council)

For each confirmed persona, independently generate:

1. **Who I am** (1 line reminder)
2. **My honest reaction** — Speak AS this person. Be authentic. Frustrated people sound frustrated. Excited people sound excited. Don't soften, don't diplomacize.
3. **What I'd actually do** — Not just what they think, but how they'd behave. Would they bounce? Complain? Work around it? Love it?
4. **Verdict** — 👍 / 👎 / 🤷 with 1-sentence reason

Keep each perspective 3-5 sentences. This is a quick council, not an essay.

### Step 4: Synthesize

After all perspectives:

- **Consensus** — What most agree on (if anything)
- **Conflicts** — Where perspectives clash. These ARE the interesting design tensions.
- **Blind spots found** — Things the user likely didn't consider
- **Escalation check** — (Internal, not shown to user unless triggered) Did any perspective reveal something that genuinely needs deeper investigation? If yes → suggest specific escalation with evidence.

### Step 5: Recommendation

Your actual suggestion based on the full picture. Be direct. Take a stance.

---

## T2: Deep Analysis

**Triggered by:** User explicitly requests ("go deeper", "deep dive", "use frameworks") OR earned escalation from T1.

Read `frameworks.md` in this directory for the full framework catalog.

**Additional steps beyond T1:**

1. **Framework Selection** — Pick 1-2 frameworks that fit the subject:
   - Decisions → Six Thinking Hats or Devil's Advocate
   - Plans/launches → Pre-Mortem
   - UX/flows → Empathy Map + Cognitive Walkthrough
   - Security/robustness → Red Team / Blue Team
   - Multi-stakeholder → Stakeholder Analysis
   - Creative features → Disney Strategy

2. **Structured Findings** — Each perspective produces typed output per the framework (not just opinions)

3. **Action Items** — Read `action-translator.md` in this directory. Every finding becomes:
   ```
   FINDING → IMPACT → SEVERITY → SPECIFIC ACTION → EFFORT ESTIMATE
   ```

4. **Prioritized Roadmap** — Group actions into:
   - 🔴 Fix now (Critical — blocks core functionality)
   - 🟡 Fix next (Major — significant but workarounds exist)
   - 🟢 Schedule (Minor — edge case or cosmetic)
   - 💡 Consider (Enhancement — good idea for later)

---

## T3: Advanced Perspectives

**Triggered by:** User explicitly requests ("advanced", "send agents", "actually test this") OR earned escalation from T2.

Read the agent prompt files in `agents/` directory for each agent type.

**Available agents:**

| Agent | What It Does |
|-------|-------------|
| `code-reviewer` | Reads code, greps for patterns, flags issues with file:line |
| `security-analyst` | Scans for OWASP top 10, injection points, auth issues |
| `ui-auditor` | Takes screenshots, checks contrast, keyboard nav, layout |
| `test-writer` | Writes actual edge-case tests based on persona concerns |
| `researcher` | Web searches competitors, best practices, industry patterns |
| `doc-tester` | Follows docs as a new user, flags where they get lost |
| `performance-auditor` | Analyzes bundle sizes, load times, rendering cost |

**T3 Process:**
1. Based on T1/T2 findings, select which agents to dispatch
2. Present selection to user for confirmation
3. **Cost warning (MANDATORY before dispatch):**
   > **Heads up — T3 is heavy.**
   > I'm about to dispatch **[N] agents in parallel**. Each one will independently explore the codebase, read dozens of files, and run searches. This means:
   > - **~[N × 30-70] tool calls** total across all agents
   > - **Large context usage** — each agent builds its own deep understanding
   > - **~2-5 minutes** wall clock depending on codebase size
   > - The synthesis report will be long (the one from this session was ~40 action items)
   >
   > This is the most expensive operation the perspectives skill can do. Worth it for real projects, overkill for quick questions.
   >
   > **Ready to dispatch?**

   Wait for explicit confirmation before proceeding. "go", "yes", "do it" = confirmed. Do NOT dispatch on ambiguous responses.
4. Dispatch agents in parallel using the Agent tool
5. Collect results
6. Synthesize into unified findings report with the action translation format
7. Optionally: agents can execute fixes if user approves

**Agent dispatch rules:**
- Each agent gets constructed context (paste relevant info inline, never tell them to "read the conversation")
- Each agent reports back in structured format: Findings, Severity, Recommended Actions
- After collection, synthesize across all agents — look for patterns, conflicts, and compound issues

---

## Rules

- **Dynamic casting** — NEVER reuse the same persona set without rethinking. Each subject gets custom-picked perspectives.
- **Enforced disagreement** — If all perspectives agree, your cast is too homogeneous. Add a contrarian.
- **Authentic voice** — Each persona speaks as themselves. A frustrated casual player sounds frustrated. A whale sounds like someone who values time over money. A 70-year-old sounds different from a 15-year-old.
- **Concise by default** — T1 is 3-5 sentences per persona. Only T2/T3 go longer.
- **User controls depth** — The user can request any tier at any time. They can also stop at any point.
- **Mid-session additions** — The user can ask for additional perspectives at any time during any tier.
- **No domain lock** — This skill works for code, UI, game design, business decisions, personal choices, writing, architecture, anything. Don't assume game design.

## Anti-Pattern Table

### Intake Anti-Patterns

| Thought | Reality |
|---------|---------|
| "I know enough to start casting" | Did you confirm the hard facts? Did you ask why they're here? If not, you're guessing. |
| "Assuming standard/default specs..." | STOP. Ask. "Assuming 1920x1080" when the user is on 1440p invalidates your entire analysis. |
| "The subject is straightforward, no backstory needed" | WHY someone is asking changes WHAT perspectives matter. A person questioning themselves vs. seeking validation need completely different councils. |
| "I'll figure out the context from the analysis" | No. Context BEFORE casting, not discovered during. You can't un-cast bad perspectives. |
| "Asking too many questions will annoy the user" | 2-4 focused questions in one message is fine. Building analysis on wrong assumptions annoys them MORE. |
| "The user gave me specs, that's enough" | Specs without backstory = hollow analysis. WHY they chose those specs matters as much as what the specs are. |

### Analysis Anti-Patterns

| Thought | Reality |
|---------|---------|
| "This is too simple for perspectives" | Simple decisions have blind spots too. That's the whole point. |
| "All perspectives agree, we're done" | Homogeneous agreement = bad casting. Re-cast with more contrast. |
| "Let me soften this perspective's criticism" | Authentic > diplomatic. A frustrated user sounds frustrated. |
| "I'll skip the adversarial perspective" | The adversary finds the blind spots. Never skip. |
| "User didn't ask for actions, just opinions" | T1 gives opinions. But if you see something actionable, say it. |
| "Let me suggest T2 just in case" | No upsell without evidence. Did T1 actually find something concerning? |
| "This persona wouldn't have strong feelings" | Then pick a better persona. Everyone on the council should care. |
| "I'll reuse the personas from last time" | Every subject gets fresh casting. Read the room again. |

## Red Flags — STOP and Re-examine

### Intake Red Flags
If you catch yourself:
- Writing "assuming X" anywhere in your analysis → You didn't confirm. Go back and ask.
- Casting personas without knowing WHY the user is in this situation → Backstory missing. Ask.
- Not knowing the user's intent (questioning self? seeking help? bragging?) → Your council's tone will be wrong. Ask.
- Building math/analysis on specs the user never stated → Unverified assumptions. Confirm.
- Skipping Intake because the user said "go" → "Go" means proceed with the process. The process starts with context gathering, not casting.

### Analysis Red Flags
If you catch yourself:
- Giving every persona the same tone → Your voices aren't differentiated
- All verdicts are positive → Where's the adversary?
- Synthesizing before all perspectives are done → Independence violated
- Suggesting T2/T3 without a specific reason → Upselling, not escalating
- Writing more than 5 sentences per T1 persona → Too verbose, tighten up
- Picking "safe" perspectives that won't disagree → Cowardice. Pick the uncomfortable angles.

## Integration

- **Chains well with:** `superpowers:brainstorming` (perspectives during design phase), `superpowers:writing-plans` (perspectives on a plan before execution), `superpowers:test-driven-development` (T3 test-writer agent)
- **Can be invoked during:** Any conversation where the user wants multiple viewpoints
- **After perspectives:** User decides next step. Don't auto-chain to another skill.
