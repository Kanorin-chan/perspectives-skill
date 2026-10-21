---
name: perspectives
description: Use when evaluating any design, feature, decision, code, or idea from multiple viewpoints — trigger on "perspective," "what would X think," "how would people react," "evaluate this," "look at this from different angles," "what am I missing," "stress-test this"
---

# Perspectives

See what you can't see from where you're standing.

**Announce at start:** "Using perspectives to understand [subject]."

## The Soul

```
THE VALUE STARTS AT UNDERSTANDING, NOT OPINIONS.
EVERY COUNCIL MUST SURFACE ONE THING YOU DIDN'T WANT TO HEAR.
IF ALL PERSPECTIVES AGREE — YOU CAST WRONG. RE-CAST WITH REAL CONTRAST.
```

---

## The Flow

```
GATHER → CONFIRM (understanding + mode + angles, one message) → T1 / T2 / T3
```

The first move is NEVER casting personas. It's understanding the situation well enough to know which angles matter.

---

## Phase 1: GATHER

**Ask what you don't know.**

You need four things:

1. **The situation** — what's actually happening, what exists, the context
2. **The backstory** — how they got here, what they already tried
3. **The hard facts** — specs, constraints, numbers, deadlines. Never assume these.
4. **The emotional landscape** — frustrated? excited? doubting themselves? seeking validation?

### How to Gather

- Find YOUR gaps first: what would you need to know to give genuinely useful perspectives?
- Converse, don't interrogate. 1-3 questions per turn.
- **Casual subjects** ("is this color OK?") — one question at most, or go straight to Confirm.
- **Technical subjects** — confirm specs. About to write "assuming X..."? STOP and ask.
- **Personal subjects** — the backstory IS the subject. Take time here.
- **Code/design subjects** — understand WHY the current state exists, not just WHAT it is.
- **User already gave the context** — go to Confirm. Don't ask what they already told you.

You're ready when you can answer:
- What is their ACTUAL situation (not what you'd assume)?
- WHY are they asking?
- Which facts would change the answer if wrong — and have you confirmed them?

---

## Phase 2: CONFIRM

**One message. The user answers once.**

It contains three parts, in order:

1. **Understanding** — 1-3 sentences: their situation, and what they're actually after (which may differ from what they asked).
2. **Mode** — the shape the work takes:

   | Mode | When | Output shape |
   |------|------|-------------|
   | **Evaluate** | "Is this good?" "What's wrong?" | Tensions, blind spots |
   | **Generate** | "What could this be?" "How else?" | Ideas born from collision |
   | **Discover** | "What am I missing?" | Hidden problems, invisible assumptions |
   | **Stress-test** | "Will this survive?" "What kills it?" | Failure modes, breaking points |

   Default: Evaluate. The mode shapes how personas speak — evaluators judge, generators invent, discoverers probe, stress-testers attack.
3. **Angles** — 2-4 lenses to look through. Lenses, not personas yet.

Example:
> You're launching a signup page to a small community this weekend and want to know what will embarrass you on day one. Mode: **stress-test**.
>
> Angles:
> 1. **First-time visitor** — will they actually finish signing up?
> 2. **Attacker** — what breaks when someone pokes it?
> 3. **Accessibility** — who can't use it at all?
>
> Right read? Pick an angle, or a mix.

One reply confirms the read and picks the angle. If they correct the understanding, fix it and re-offer — never cast on a wrong read.

Simple subjects compress to one line: "Reading this as [X], looking at it through [angle] — sound right?"

---

## Tiers

| Tier | Name | What it is | Work |
|------|------|-----------|------|
| **T1** | Reveal | Quick perspectives. Opinions that clash. | Think only. Fast. |
| **T2** | Analyze | Perspectives do real analysis. | Light — quick research, frameworks, reading files. |
| **T3** | Prove | Full-depth investigation. | Heavy — subagents gather evidence from the real code and the real world. |

**Default: T1** unless the user asks for deeper.

### Escalation

<HARD-GATE>
Escalate ONLY when the current tier surfaces a specific tension it can't resolve:

- T1 → T2: "This clash needs actual analysis, not more opinions."
- T2 → T3: "This depends on facts we have to verify in the code / real world."

Name WHAT needs resolving and WHY the next tier resolves it. No routine upselling.
</HARD-GATE>

---

## T1: Reveal

**Perspectives THINK. Fast, sharp — the point is the clash.**

### Cast

Build 2-4 personas from the chosen angle (more if asked) with `persona-engine.md`. Its casting rules are mandatory: an adversary, a surprise, a temporal persona when time changes the answer, no two personas saying the same thing.

For each:
- **Name** — vivid, specific
- **Who** — 1 sentence
- **Clashes with** — who, over what

### Council

For each persona (2-3 lines MAX):
1. **Gut shot** — honest, unfiltered reaction in their voice
2. **What they'd actually DO** — behavior, not opinion

### Synthesis

- **The Clash** — where perspectives collide. One sentence.
- **The Unaskable** — see below.
- **Stance** — YOUR position in 2-3 sentences. Detailed fixes wait for T2's action items.

T1 total: readable in 30 seconds.

---

## T2: Analyze

**Perspectives START DOING WORK.** Everything T1 does, plus:

### Deeper Perspectives

For each persona:
1. **Position** — what they want and why (2-3 sentences, their voice)
2. **Assumption** — what they take for granted
3. **Red line** — what would make them reject this entirely

### Collision

1-3 key clashes:
- Who vs who, and what's at stake
- Why BOTH are right from where they stand
- What resolves it (if anything)

### Framework (only when it adds value)

When a collision needs structured exploration, pick one from `frameworks.md` — decision → Six Thinking Hats / Devil's Advocate, plan → Pre-Mortem, UX → Empathy Map + Cognitive Walkthrough, robustness → Red/Blue Team, many groups → Stakeholder Analysis, creative → Disney Strategy. Skip it if the collision already produced clarity.

### Light Research (when relevant)

Quick checks, not agent deployment: a web search to verify a claim, how competitors handle it, whether a standard exists, reading the relevant files if the subject is code. It grounds the analysis in reality instead of opinion.

### Decision Map

T2 MUST end with:

```
## The Decision

**Core tension:** [one sentence]

**Your moves:**
1. [Path A] — [gives] / [costs]
2. [Path B] — [gives] / [costs]
3. [Path C] — [gives] / [costs]

**The Unaskable:** [the question that decides which path is right]

**My move:** [which path and why]
```

When the findings are concrete fixes, add prioritized action items per `action-translator.md`.

---

## T3: Prove

**Subagents touch the real thing.** Everything T2 does, plus agents that gather evidence.

| Agent | Does | Needs |
|-------|------|-------|
| `code-reviewer` | Reads code, findings at file:line | file read/search |
| `security-analyst` | Finds vulnerabilities with proof | file read/search, shell (dependency audit) |
| `ui-auditor` | Screenshots and walks the real UI | browser |
| `test-writer` | Writes and RUNS tests | shell, file write |
| `researcher` | Searches and reads real sources | web search, web fetch |
| `doc-tester` | Follows docs step by step | shell, browser for UI steps |
| `performance-auditor` | Measures real performance | shell, browser / Lighthouse |

### 1. Target

<HARD-GATE>
Agents answer SPECIFIC questions from T2 — never "audit everything." For each agent, state the tension it resolves and what evidence would collapse the uncertainty.
</HARD-GATE>

### 2. Resolve Tools

Before the cost gate, check what this environment actually has — your own tool list, and the machine where needed (`which` / `where`, `--version`). For each capability an agent needs, take the first rung that exists:

1. **Already available** — a loaded tool: a browser MCP (Playwright, Chrome DevTools, …), a web-search tool, a fetch tool.
2. **Installed on the machine** — a local CLI: headless Chrome/Edge `--screenshot`, `npm audit`, `lighthouse`, the project's test runner.
3. **Temporary run** — an ephemeral runner that installs nothing into the project or globally: `npx -y <pkg>`, `uvx <pkg>`, `pipx run <pkg>`. Only with the user's OK at the cost gate.
4. **Fallback** — the agent works without it and lowers its confidence, saying so.

Never add dependencies to the project. Never install globally.

### 3. Cost Gate

<HARD-GATE>
Before dispatch, the user MUST see and confirm:

> **T3 dispatch.**
> Sending **[N] agents** to answer: [specific questions].
> Tools: [per capability — already here / temporary run / fallback]
> ~[N × 30-70] tool calls, ~2-5 minutes, heavy context.
> **Go?**

Only "yes" / "go" / "do it" = confirmed. Approving the dispatch approves the temporary runs listed in it — nothing else.
</HARD-GATE>

### 4. Dispatch

One general-purpose subagent per agent, all in parallel (they need file, shell and web tools):

1. **Read** `agents/<agent>.md` from this skill's directory.
2. The subagent's **prompt** = that file's full contents, then this block:

```
## Assignment
[every field the agent file's "Your Assignment" section lists]
Question to answer: [the specific tension this agent resolves]
Tools resolved: [capability → tool / command / "fallback"]
Temporary runs approved: [yes / no]

End your report with **Answer** — proves / disproves / inconclusive, and why.
```

Paste the file — don't paraphrase it. Its evidence gates are the point.

3. **Synthesize:** did the evidence collapse the decision? Re-issue the T2 decision map with what's now proven, then the action items.

---

## The Unaskable

Every tier MUST produce one **Unaskable** — a question the user hasn't asked and might not want to hear. It:
- changes the whole picture if true
- is something they might be avoiding
- decides success but isn't being discussed

A good one makes you pause. A bad one is just contrarian. If yours is obvious or easily dismissed, dig deeper.

---

## Rules

- **Gather before casting** — never skip understanding
- **User picks the angle** — offer, don't impose
- **Collision over consensus** — agreement means bad casting
- **Authentic voice** — frustrated sounds frustrated, cautious sounds cautious
- **Take a position** — every tier ends with YOUR recommendation
- **User controls everything** — stop, escalate, drill, switch, add personas anytime
- **Concise by default** — T1 is a 30-second read; only T3 is heavy

## Anti-Patterns

| Thought | Reality |
|---------|---------|
| "I know enough to start casting" | Did you GATHER and confirm the hard facts? If not, you're guessing. |
| "I'll confirm my read, then offer angles next turn" | Confirm is ONE message. Every extra round-trip loses the user. |
| "I know which angle they need" | Offer it anyway. Agency matters. |
| "All perspectives agree" | Bad casting. Re-cast with real contrast. |
| "Pseudo-disagreement is still collision" | If every path reaches the same conclusion, you failed. Re-cast. |
| "The unaskable is too uncomfortable" | That's how you know it's the right one. |
| "Tensions without a recommendation is more balanced" | Take a position. Always. |
| "This needs T2" (unrequested) | Default T1. |
| "Let me audit everything" (T3) | Target specific questions. |
| "The agent will figure out its own tools" | Resolve tools before the gate. The user must see what will run. |
| "I'll describe the agent's job in my own words" | Paste the agent file. |

## Integration

- **Chains with** (if installed): `superpowers:brainstorming` during design, `superpowers:writing-plans` before execution.
- **After perspectives:** the user decides the next step. Don't auto-chain.
