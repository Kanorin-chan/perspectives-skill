# Perspectives — Claude Code Skill

> **Need another pair of eyes on it?** Get a whole room of them.

See what you can't see from where you're standing. You bring a design, a product, a plan, a decision, a piece of code. Perspectives casts a small council of **specific, detailed people** who would actually meet that thing in the real world, lets them clash, and tells you the one question you were avoiding. It works for anything: products, visual design, business, game design, life decisions, code.

## Why it's different

Most "multiple perspectives" prompts give you five polite paragraphs that all agree. This skill is built to stop that:

- **Understanding before opinions.** It asks what it doesn't know first — your situation, backstory, hard facts — instead of guessing.
- **Detailed people, not job titles.** Not "a budget user", but *"Mira, 34, night-shift nurse who resents all three of her streaming subscriptions."* Detail is where the insight comes from.
- **Collision over consensus.** If every persona agrees, the cast was wrong and it re-casts.
- **The Unaskable.** Every run ends with one question you haven't asked and might not want to hear.
- **It takes a position.** No "it depends." You get a recommendation.

## How a run flows

```
GATHER → CONFIRM → T1 Reveal → (T2 Analyze) → (T3 Prove)
```

1. **Gather** — 1-3 questions about what it doesn't know. Skipped if you already said it.
2. **Confirm** — one message: its read of your situation, the **mode**, and 2-4 **angles** to choose from. You answer once.
3. **T1 Reveal** — 2-4 personas, a few lines each. The clash, the unaskable, a stance. A 30-second read.
4. **T2 Analyze** — only if you ask, or T1 hits something it can't resolve by opinion. Deeper positions, assumptions, red lines, a framework if it helps (Pre-Mortem, Six Hats, Red Team…), light research, and a decision map.
5. **T3 Prove** — only if you ask. Subagents check the real thing: read code, screenshot the UI, run tests, search the web. Always shows you the cost and the tools first and waits for "go".

### Modes

| Mode | You're asking | You get |
|------|--------------|---------|
| **Evaluate** | "Is this good?" | Tensions and blind spots |
| **Generate** | "What could this be?" | Ideas born from the clash |
| **Discover** | "What am I missing?" | Hidden problems and assumptions |
| **Stress-test** | "Will this survive?" | Failure modes and breaking points |

---

## Examples

Shortened T1 outputs. A real run gathers context first. These show the shape of what comes back.

### 1. A product — moving an app to a subscription

> **You:** perspectives on switching my habit-tracker app from a $4.99 one-time purchase to $2.99/month. 40k users, mostly paid once years ago.

**Confirm:** *You need recurring revenue to keep building, and you're afraid of a backlash from people who already paid. Mode: stress-test. Angles: existing buyers · new users · the app-store review page.*

**Cast**

- **Daniel, 41, bought it in 2019, still opens it every morning.** Tells friends about it. Clashes with Priya over whether loyalty is owed.
  > "I paid. You're now charging me rent on something I already own?" → *Leaves a one-star review the day the paywall appears, then quietly keeps using the old version.*
- **Priya, 26, finds the app today from a TikTok.** Has never heard of the one-time price. Clashes with Daniel.
  > "$2.99 is less than a coffee. Is there a free trial?" → *Subscribes if onboarding shows value in under a minute. Never reads reviews older than a month.*
- **The review page, six months from now** *(temporal)*. Clashes with you.
  > "Rating fell from 4.8 to 3.9 in two weeks. All of it from long-time users." → *New users like Priya see 3.9 and never install.*

**The Clash:** Your revenue comes from Priya, but Daniel controls the rating Priya sees first.
**The Unaskable:** *If your oldest users are your marketing, are you about to fire your marketing department?*
**Stance:** Lifetime access for everyone who bought before today. Subscription for new users only. The goodwill is worth more than Daniel's $2.99.

### 2. A design — a café rebrand

> **You:** perspectives on the new logo and menu for my family's café. Going from a hand-painted sign to a clean minimal black-and-white look.

**Confirm:** *Your parents' café is 20 years old; you want it to attract younger customers without losing the regulars. Mode: evaluate. Angles: regulars · passers-by · the street at night.*

**Cast**

- **Auntie Rosa, 67, has had the same kopi at the same table every morning for 15 years.** Clashes with Jun.
  > "Where is the old sign? It looks like a phone shop now. Did someone buy the place?" → *Asks the staff if the owners changed. Comes back, but tells everyone it's "not the same".*
- **Jun, 23, walks past with earbuds in, choosing between three cafés on Google Maps.** Clashes with Rosa.
  > "Finally looks like somewhere I'd post." → *Judges it entirely by the Maps photo. Has never seen the old sign.*
- **The street at 7pm** *(surprise)*. Clashes with the black-and-white palette.
  > "Black on a dark shopfront, under one yellow streetlight." → *The new sign disappears after dark. The old hand-painted one was lit and colorful.*

**The Clash:** Jun wants it to look new; Rosa needs it to look like the same place.
**The Unaskable:** *Is the problem actually the logo, or that young people don't know you exist?*
**Stance:** Keep one element of the old sign (the hand-lettered name) inside the new system, and test the sign at night before printing anything.

### 3. A life decision — taking a remote job

> **You:** perspectives on leaving my office job for a fully remote one. Same pay, I'd work from the small flat I share with my partner.

**Confirm:** *The commute is draining you and the remote role looks like freedom, but you're unsure what you'd lose. Mode: discover. Angles: you in a year · your career · the household.*

**Cast**

- **You, day 1 vs day 300** *(temporal)*. Clashes with itself.
  > Day 1: "Two hours a day back. I'll finally go to the gym." Day 300: "I haven't spoken to anyone outside my family in a week." → *The time saved goes to the couch unless something replaces the office's structure.*
- **A hiring manager at your dream company, two years from now.** Clashes with the day-1 you.
  > "Remote is fine. What did you ship, and who can vouch for you?" → *Calls your references. Fewer people know your work when nobody sees you do it.*
- **Sam, your partner, who already works from home — on calls from 9 to 5.** *(surprise)* Clashes with your calendar.
  > "So we both need the quiet room at 10am. Every day?" → *One of you ends up at the kitchen table in headphones, and it starts to feel like a fight about space.*

**The Clash:** Remote gives you time back, but home is already somebody else's office.
**The Unaskable:** *Is it the office you want to leave, or the job itself?*
**Stance:** Take it, on one condition you set on day one — a fixed workspace and hours agreed with Sam, or a co-working day each week.

### 4. Game design — adding a stamina system

> **You:** perspectives on adding stamina to my free mobile puzzle game: 5 plays, refills one every 30 minutes, or pay to refill.

**Confirm:** *The game is free and you need it to earn something; stamina is the common pattern. Mode: stress-test. Angles: the daily player · the whale · the reviewer.*

**Cast**

- **Kenji, 38, plays three levels on the train every morning.** Clashes with the monetization goal.
  > "Five plays is my whole commute. Fine." → *Never hits the wall, never pays. The system costs you nothing and earns nothing from him.*
- **Lena, 19, binges 40 levels on a Sunday.** Your most engaged player. Clashes with Kenji.
  > "I'm on a streak and it tells me to wait three hours?" → *Pays once, feels cheated, uninstalls by the third wall.*
- **A YouTuber reviewing "puzzle games that respect your time"** *(surprise)*.
  > "Energy system. Next." → *Your best marketing channel puts you on the skip list in one sentence.*

**The Clash:** The players who'd pay are exactly the players stamina punishes.
**The Unaskable:** *Are you monetizing your players, or your best players' patience?*
**Stance:** No stamina. Sell an ad-free unlock and cosmetic themes; keep the binge players binging.

### 5. Code, all the way to T3 — a signup page

> **You:** perspectives on my signup page before I share it with a small Discord.

T1 casts a first-time visitor, a bored teenager poking the form, and a screen-reader user. They clash over whether "it works on my machine" is good enough. T2 runs a Red/Blue team and finds two things it can't settle by opinion: *does the name field execute HTML?* and *can a screen reader even tell what the fields are?*

> **T3 dispatch.**
> Sending **2 agents** to answer: is the name field injectable? can a screen-reader user complete signup?
> Tools: browser — Playwright MCP (already here) · dependency audit — none needed
> ~60-140 tool calls, ~2-5 minutes, heavy context.
> **Go?**

The security agent comes back with a working payload and the file:line. The UI agent comes back with screenshots and every unlabeled input. The decision map is re-issued with what's now proven.

---

## Installation

Clone straight into your Claude Code skills directory:

```bash
git clone https://github.com/Kanorin-chan/perspectives-skill.git ~/.claude/skills/perspectives
```

Windows (PowerShell):

```powershell
git clone https://github.com/Kanorin-chan/perspectives-skill.git "$env:USERPROFILE\.claude\skills\perspectives"
```

Then just talk: *"perspectives on…"*, *"what would players think of…"*, *"stress-test this plan"*, *"what am I missing?"* The skill triggers on its own.

## What T3 uses

T3 agents use whatever your environment already has, and only reach further with your OK:

1. **Already loaded** — a browser MCP (Playwright, Chrome DevTools), a web-search tool, a fetch tool
2. **Installed on your machine** — headless Chrome/Edge, `npm audit`, `lighthouse`, your project's test runner
3. **Temporary run** — `npx -y …` / `uvx …` / `pipx run …`, nothing added to your project or installed globally. Listed in the cost gate before you say "go".
4. **Fallback** — the agent works without it and says its confidence is lower

T1 and T2 need nothing beyond Claude Code.

## Files

```
perspectives/
  SKILL.md                  # The flow: gather, confirm, tiers, gates, rules
  persona-engine.md         # How to build detailed, clashing personas + dimension catalog
  frameworks.md             # Six Hats, Pre-Mortem, Red/Blue Team, Empathy Map, and more
  action-translator.md      # Turning findings into prioritized action items
  agents/                   # T3 agent protocols — pasted into each subagent's prompt
    code-reviewer.md
    security-analyst.md
    ui-auditor.md
    test-writer.md
    researcher.md
    doc-tester.md
    performance-auditor.md
```

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) — CLI, desktop app, or IDE extension
- For T3: a model with room for parallel subagents. A browser MCP and a web-search tool make the UI and research agents much stronger, but neither is required.

## License

MIT
