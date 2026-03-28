# Perspectives — Claude Code Skill

Evaluate anything through the eyes of multiple relevant personas. Dynamically generates perspectives that fit your specific situation — works across all domains: software, game design, business, UX, life decisions, anything.

## What It Does

You describe something you're building, deciding, or evaluating. The skill:

1. **Gathers context** (backstory, intent, hard facts) before making assumptions
2. **Casts 4-6 personas** tailored to your subject — not from a fixed list, but built from 8 dimensional axes (age, expertise, accessibility, economic, role, thinking style, motivation, culture)
3. **Each persona speaks independently** with authentic voice — frustrated people sound frustrated, excited people sound excited
4. **Synthesizes** consensus, conflicts, and blind spots you didn't consider

## Three Tiers

| Tier | Name | What Happens |
|------|------|-------------|
| **T1** | Quick Council | 4-6 personas give structured opinions inline. Fast, default, usually enough. |
| **T2** | Deep Analysis | Structured frameworks applied (Six Hats, Pre-Mortem, Red Team, etc.) + prioritized action items with effort estimates. |
| **T3** | Advanced | Sub-agents dispatched to actually DO work — code review, security scan, UI audit, performance analysis, competitive research, doc testing. Each agent reads your actual codebase and reports back with file:line references. |

T1 is the skill. T2 and T3 are escalations that only happen when you ask or when T1 finds something genuinely concerning.

## Installation

Copy the entire folder to your Claude Code skills directory:

```bash
# Clone the repo
git clone https://github.com/Kanorin-chan/perspectives-skill.git

# Copy to Claude Code skills
cp -r perspectives-skill ~/.claude/skills/perspectives
```

Or manually copy the files into `~/.claude/skills/perspectives/`.

### File Structure

```
perspectives/
  skill.md                  # Main skill — tiers, process, gates, anti-patterns
  persona-engine.md         # 8-dimension catalog for building personas
  frameworks.md             # 8 analysis frameworks (Six Hats, Pre-Mortem, Red Team, etc.)
  action-translator.md      # Finding -> Action translation with severity scale
  agents/
    code-reviewer.md        # Reviews code from a persona's lens
    security-analyst.md     # OWASP scanning, adversarial thinking
    ui-auditor.md           # Accessibility + usability audit
    test-writer.md          # Writes tests based on persona concerns
    researcher.md           # Web research for competitors/best practices
    doc-tester.md           # Follows docs as a new user
    performance-auditor.md  # Evaluates perf under constraints
```

## Usage

Just say "perspectives" or "evaluate this from different angles" in Claude Code. The skill triggers automatically.

```
You: perspectives on my login page redesign
     -> Intake: gathers context, confirms what you're evaluating
     -> Cast: proposes 4-6 personas, waits for your approval
     -> Analyze: each persona gives their honest take
     -> Synthesize: consensus, conflicts, blind spots
     -> Recommend: direct stance on what to do

You: go deeper
     -> T2: frameworks applied, prioritized action items

You: test it / send agents
     -> T3: sub-agents dispatched to audit code, security, UX, performance, etc.
```

## Key Design Principles

- **No fixed persona lists** — every subject gets custom-built perspectives from dimensional axes
- **Enforced disagreement** — if all perspectives agree, the cast is too homogeneous
- **Authentic voice** — each persona speaks as themselves, not as Claude being polite
- **No upsell** — T2/T3 only suggested when T1 finds something genuinely concerning
- **Context before casting** — the skill gathers backstory and intent before proposing perspectives, to avoid shallow assumption-filled analysis

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI, desktop app, or IDE extension
- For T3 agents: enough context window for parallel sub-agent dispatch (works best with high-context models)

## License

MIT
