# Persona Engine — Dimension Catalog

This file defines the dimensions from which perspectives are constructed. Don't pick from a fixed list — build personas by combining relevant dimensions for the specific subject being evaluated.

## How to Build a Persona

1. **Identify the 2-3 most relevant dimensions** for the subject
2. **Pick contrasting positions** along those dimensions
3. **Combine** dimensions to create specific, real-feeling people
4. **Name them vividly** — "Budget-conscious retiree learning their first app" not "User Type C"

A persona should feel like someone you could meet. The more specific, the more useful their perspective.

---

## Dimension Catalog

### Age / Life Stage

| Position | Mental Model | Tech Relationship | Key Concerns |
|----------|-------------|-------------------|--------------|
| **Child (6-12)** | Concrete thinking, short attention span, learns by doing | Intuitive with touch/visual, struggles with text-heavy UI | Fun, immediate feedback, safety, parental approval |
| **Teen (13-17)** | Identity-forming, peer-influenced, skeptical of authority | Native digital, social-first, values aesthetics and speed | Social status, self-expression, privacy from parents, trends |
| **Young Adult (18-25)** | Exploring, optimistic, time-rich cash-poor | Power user, multi-device, expects modern patterns | Value for money, peer validation, career relevance |
| **Working Adult (26-45)** | Pragmatic, efficiency-focused, time-poor | Competent but impatient with friction | Reliability, time savings, professional utility, family juggling |
| **Middle-aged (46-60)** | Experienced, cautious about change, values trust | Capable but prefers familiar patterns | Stability, clear value proposition, customer support quality |
| **Elder (60+)** | Wisdom, patience, fixed income concerns | Varies wildly — some tech-savvy, many struggle with small text/complex nav | Accessibility, simplicity, trust, not feeling patronized |

### Technical Expertise

| Level | Behavior Pattern | Tolerance |
|-------|-----------------|-----------|
| **Never touched tech** | Needs hand-holding for every step, fears breaking things | Zero tolerance for jargon or ambiguity |
| **Casual user** | Uses apps daily but doesn't understand how they work | Low tolerance for unexpected behavior |
| **Intermediate** | Can troubleshoot basics, reads error messages | Moderate — appreciates shortcuts but needs discoverability |
| **Power user** | Customizes everything, knows keyboard shortcuts, reads changelogs | Low tolerance for dumbed-down interfaces, wants control |
| **Developer** | Reads source code, thinks in systems, values API quality | Zero tolerance for magic/abstraction that can't be overridden |
| **Domain expert** | Deep specialized knowledge, strong opinions about correctness | Zero tolerance for domain inaccuracies, values precision |

### Accessibility (Persona Spectrum: Permanent → Temporary → Situational)

| Type | Permanent | Temporary | Situational |
|------|-----------|-----------|-------------|
| **Visual** | Blind, low vision, color blind | Post-surgery, eye infection | Screen glare, dark room, tiny screen |
| **Motor** | One arm, limited dexterity, tremor | Broken arm, RSI flare-up | Holding baby, wearing gloves, bumpy bus |
| **Cognitive** | Learning disability, ADHD, autism spectrum | Concussion, medication fog, grief | Stressed, sleep-deprived, multitasking, drunk |
| **Hearing** | Deaf, hard of hearing | Ear infection, tinnitus episode | Noisy bar, open office, library (can't use audio) |
| **Speech** | Non-verbal, severe stutter | Laryngitis, dental work | Accent in foreign country, loud environment |

When selecting an accessibility perspective, specify WHERE on the spectrum. "Motor accessibility" is too vague. "Parent holding a baby trying to use the app one-handed" is a real perspective.

### Economic

| Position | Decision Pattern | Key Question |
|----------|-----------------|--------------|
| **Poverty/survival** | Every cost is a barrier, free tier is the only tier | "Can I use this without paying anything?" |
| **Budget-conscious** | Compares prices, waits for sales, values per-unit cost | "Is this worth the money?" |
| **Value-seeker** | Will pay for quality, but needs to see clear value | "What do I get that justifies the price?" |
| **Comfortable** | Price is a factor but not the primary one | "Is this good? The price seems fair." |
| **Price-insensitive** | Pays for convenience, time savings, best-in-class | "Does this save me time? Is it the best?" |
| **Enterprise buyer** | Budget is allocated, needs justification for procurement | "Can I get approval for this? What's the ROI story?" |

### Role / Relationship to the Subject

| Role | Primary Lens | Key Question |
|------|-------------|--------------|
| **End user / Customer** | "Does this solve my problem?" | Usability, utility, delight |
| **Developer / Builder** | "Can I build and maintain this?" | Technical debt, API quality, docs |
| **Designer** | "Is this coherent and elegant?" | Consistency, flow, aesthetics |
| **Manager / Lead** | "What's the cost, risk, and timeline?" | ROI, team capacity, risk |
| **Support / Helpdesk** | "Will users need help with this?" | Edge cases, error messages, FAQ potential |
| **Marketer / Sales** | "Can I explain and sell this?" | Value proposition, differentiators |
| **Competitor** | "How do I counter or copy this?" | Weaknesses, advantages to steal |
| **Regulator / Legal** | "Does this comply?" | Privacy, data handling, standards |
| **Investor / Stakeholder** | "Is this a good bet?" | Market fit, growth potential, defensibility |
| **New team member** | "Can I understand and contribute?" | Onboarding, docs, code readability |

### Thinking Style

| Style | Approach | Values | Frustrations |
|-------|----------|--------|-------------|
| **Analytical** | Data-driven, evidence-based, methodical | Precision, reproducibility, proof | Vague claims, gut feelings presented as facts |
| **Creative** | Divergent, experimental, aesthetic | Novelty, beauty, possibility | Rigid constraints, "we've always done it this way" |
| **Cautious** | Risk-averse, thorough, worst-case thinker | Safety, predictability, completeness | Moving fast and breaking things, unclear rollback |
| **Bold** | Risk-taking, first-mover, "ship it" mentality | Speed, learning from failure, iteration | Analysis paralysis, perfectionism, slow processes |
| **Process-oriented** | Systematic, documented, repeatable | Scalability, governance, auditability | Cowboy coding, undocumented decisions |
| **People-oriented** | Empathetic, collaborative, inclusive | Team wellbeing, diversity, communication | Decisions made without consulting affected people |

### Motivation (What Drives Them)

| Driver | Behavior | Design Implication |
|--------|----------|-------------------|
| **Achievement** | Wants to complete, master, collect, rank up | Needs progress tracking, milestones, rewards |
| **Exploration** | Wants to discover, understand, find secrets | Needs depth, hidden content, rewarding curiosity |
| **Social** | Wants to connect, share, belong, be seen | Needs sharing, collaboration, community features |
| **Competition** | Wants to win, rank, prove superiority | Needs leaderboards, fair matchmaking, visible skill |
| **Efficiency** | Wants to optimize, automate, minimize waste | Needs shortcuts, batch operations, clear workflows |
| **Self-expression** | Wants to customize, create, be unique | Needs personalization, creation tools, variety |
| **Comfort** | Wants to relax, enjoy, not be stressed | Needs low-pressure experience, forgiving mechanics |

### Cultural Dimensions (use sparingly, when genuinely relevant)

| Dimension | Low End | High End |
|-----------|---------|----------|
| **Power Distance** | Expects equality, questions authority | Accepts hierarchy, defers to authority |
| **Individualism** | Group harmony, collective-first | Individual achievement, self-reliance |
| **Uncertainty Avoidance** | Comfortable with ambiguity, flexible | Needs rules, structure, predictability |
| **Long-term Orientation** | Tradition, quick results | Persistence, future-focused, delayed gratification |

---

## Casting Rules

1. **Pick dimensions that create tension** for this specific subject. If you're evaluating a pricing model, Economic + Role + Motivation matter more than Age.
2. **Minimum one adversarial persona** — someone who would reject, hate, or be harmed by this.
3. **Minimum one surprise persona** — someone the user probably didn't think about.
4. **Maximum overlap: 1 dimension** — No two personas should share more than one dimension position. If you have two "cautious developers," one of them is redundant.
5. **Specificity test** — Can you picture this person? If the persona is too abstract to imagine as a real human, make it more specific.
6. **4-6 personas for T1**, 6-8 for T2, as many as needed for T3 (each maps to an agent).
