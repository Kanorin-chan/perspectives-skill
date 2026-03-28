# Action Translator

Every perspective finding can become an action item. This file defines how to translate observations into prioritized, actionable output.

Used in T2 (Deep Analysis) and T3 (Advanced Perspectives). T1 (Quick Council) uses informal recommendations — don't force this structure on a quick council unless the findings genuinely warrant it.

## The Translation Formula

```
FINDING → IMPACT → SEVERITY → ACTION → EFFORT
```

For each finding from the perspective analysis:

| Field | What to write |
|-------|--------------|
| **Finding** | What was observed. Be specific. "Users might get confused" is useless. "The save button is invisible on mobile because it's below the fold" is actionable. |
| **Impact** | Who is affected and how badly. "Affects all mobile users, blocks primary task completion." |
| **Severity** | See severity scale below. |
| **Action** | The specific thing to do. Not "improve this" but "move the save button above the fold" or "add keyboard shortcut for power users." |
| **Effort** | Quick estimate: trivial (minutes), small (hours), medium (days), large (weeks). |

## Severity Scale

| Level | Symbol | Definition | Response |
|-------|--------|-----------|----------|
| **Critical** | 🔴 | Blocks core functionality, causes data loss, creates safety/security risk, or excludes entire user groups | Fix before shipping / Fix immediately |
| **Major** | 🟡 | Significant degradation of experience, workarounds exist but aren't obvious | Fix in current cycle |
| **Minor** | 🟢 | Edge cases, cosmetic issues, slight friction that most users won't notice | Schedule when convenient |
| **Enhancement** | 💡 | Not a problem — an opportunity. Things that would make it better but aren't broken. | Evaluate for roadmap |

## Prioritization

After collecting all findings, sort by:

1. **Critical first** — these are blockers, non-negotiable
2. **Among same severity: frequency wins** — an issue hitting 80% of users beats one hitting 5%
3. **Quick wins surface** — a 🟡 that takes 10 minutes beats a 🟡 that takes 2 weeks
4. **Compound issues escalate** — if three Minor findings all affect the same persona/flow, together they might be Major

## Output Format

### For a few findings (typical T2):

```markdown
## Action Items

🔴 **[Finding title]**
Impact: [who and how]
Action: [specific fix]
Effort: [estimate]

🟡 **[Finding title]**
Impact: [who and how]
Action: [specific fix]
Effort: [estimate]

💡 **[Finding title]**
Idea: [what could be improved]
Effort: [estimate]
```

### For many findings (T3 with multiple agents):

Group by theme or component:

```markdown
## Action Items

### Authentication Flow
🔴 Session tokens stored in localStorage — XSS risk (Security Analyst)
🟡 No "remember me" option — friction for returning users (UX perspective)

### Dashboard UI
🟡 Contrast ratio 2.8:1 on secondary text — fails WCAG AA (UI Auditor)
🟢 Loading spinner has no alt text (UI Auditor)
💡 Add keyboard shortcut for most common action (Power User perspective)
```

## When NOT to Force Actions

- T1 Quick Council: Give natural recommendations, not formatted action items. Only use this format if a finding is serious enough to warrant it.
- Personal decisions: "Should I take this job?" doesn't need a severity scale. Give human advice.
- Exploratory analysis: Sometimes the value is the perspective itself, not a todo list.

The action translator serves the analysis, not the other way around. If the subject doesn't need formatted action items, don't force them.
