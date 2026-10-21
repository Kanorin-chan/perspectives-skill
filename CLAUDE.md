# perspectives-skill

Public Claude Code skill: multi-persona evaluation (gather → confirm → T1 Reveal / T2 Analyze / T3 Prove).

## Read first — all of it, before editing

1. `SKILL.md` — the flow and every gate
2. `persona-engine.md` — casting rules (mandatory, referenced from SKILL.md)
3. `agents/*.md` — T3 protocols; skim the "Your Assignment" and gate sections of each
4. `README.md` — the public face; must match SKILL.md

## Invariants

- Main file is `SKILL.md` (uppercase). Case-sensitive systems won't load `skill.md`.
- Tier names are **Reveal / Analyze / Prove** everywhere. Grep for old names (Quick Council, Deep Analysis, Advanced) after edits.
- `agents/*.md` are prompt templates, not registered subagents. SKILL.md's Dispatch step pastes the file + an Assignment block. A field added to an agent's "Your Assignment" needs nothing else; a new Assignment-block field must be handled in every agent that uses it.
- Tool access is never hard-coded to one MCP. Ladder: already loaded → installed → temporary (`npx -y` / `uvx` / `pipx run`, only if approved at the cost gate) → fallback with lowered confidence.
- No personal data. This repo is public.

## Testing a change

End-to-end: a fresh `claude -p --session-id <uuid>` in a scratch folder with a toy subject, then `--resume <uuid>` per turn, playing the user. Check: ≤3 gather questions, one Confirm message (understanding + mode + angles), the Unaskable, a stance, T3 tool resolution shown in the cost gate, agents that cite real evidence.

## Install location

Users clone into `~/.claude/skills/perspectives`. Keep the repo root installable as-is.
