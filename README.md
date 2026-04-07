# NOUMENON Free Starter Pack

> **5 professional Claude Code skills. Free forever. MIT license.**

![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)
![Skills](https://img.shields.io/badge/Skills-5-blue.svg)
![Claude Code](https://img.shields.io/badge/Claude_Code-Compatible-orange.svg)
![SKILL.md](https://img.shields.io/badge/Standard-SKILL.md-purple.svg)

No email capture. No waitlist. No upsell in this repo. Just free, professional-grade Claude skills.

---

## What's inside

| Skill | What it does |
|---|---|
| [`risk-calculator`](#risk-calculator) | Position sizing with real math — share count, R targets, risk flags |
| [`debug-detective`](#debug-detective) | 5-phase bug investigation with ranked hypotheses |
| [`idea-validator`](#idea-validator) | 6-dimension startup scoring with devil's advocate and verdict |
| [`terms-decoder`](#terms-decoder) | ToS and privacy policies → plain English with risk ratings |
| [`hook-writer`](#hook-writer) | 10 hooks across 5 formulas, scored and ranked per platform |

Skills activate automatically based on context. No slash commands. Just talk to Claude normally.

---

## Install

**Claude Code — 30 seconds:**

```bash
git clone https://github.com/noumenon-ai/noumenon-free-starter-pack
cp -r noumenon-free-starter-pack/* ~/.claude/skills/
```

Restart Claude Code. Done.

**Per-project install:**

```bash
cp -r noumenon-free-starter-pack/* .claude/skills/
```

**Claude.ai:**

Open any skill's `SKILL.md` → copy contents → paste into Project Instructions.

---

## Skills

### risk-calculator

Sizes positions using real formulas. Give it your account, entry, and stop — it outputs exact share count, dollar risk, and R targets. Flags oversized positions, stops too tight, and concentration risk.

```
You: "$20k account, 1% risk, entry $142, stop $136"

POSITION SIZING
────────────────────────────
Account:        $20,000
Dollar risk:    $200 (1%)
Stop distance:  $6.00 (4.2%)
Position:       33 shares · $4,686
────────────────────────────
Target +1R:     $148  →  +$198
Target +2R:     $154  →  +$396
Target +3R:     $160  →  +$594
────────────────────────────
Status: ✓ SAFE — within normal parameters
```

**Triggers:** "size this trade," "how many shares," "what's my risk," "position sizing for," "calculate my stop"

---

### debug-detective

Runs a structured 5-phase investigation on any bug or error. Ranks hypotheses by confidence, outputs a fix — not just guesses.

```
You: "TypeError: Cannot read properties of undefined reading 'map'"

INVESTIGATION
────────────────────────────
Phase 1 — Reproduce:   ✓ Confirmed in dev env
Phase 2 — Isolate:     UserList.tsx line 34
Phase 3 — Hypothesize:
  1. data undefined on first render    91%
  2. API returns null instead of []     8%
  3. Race condition in useEffect        1%
────────────────────────────
Root cause: async fetch resolves after render
Fix:        data?.map(...) or initialise data = []
```

**Triggers:** "help me debug," "why is this failing," "I have a bug," "analyze this error," "stack trace"

---

### idea-validator

Scores startup ideas across 6 dimensions, names the riskiest assumption, generates 3 arguments against it, and gives a binary verdict.

```
You: "Validate: Airbnb for parking spaces"

IDEA VALIDATION
────────────────────────────
Problem clarity:      ████████░░  4/5
Market size:          ████████░░  4/5
Willingness to pay:   ████████░░  4/5
Competition density:  ██████░░░░  3/5
Founder-market fit:   ██████░░░░  3/5
Distribution path:    ██████░░░░  3/5
────────────────────────────
Score: 21/30  →  VALIDATE FIRST

Riskiest assumption:
  Will hosts list vs just using their driveway?

Test in under 2 weeks for under $100:
  Send 20 cold DMs to homeowners near stadiums.
  3+ yes = supply side exists. Build it.

Devil's advocate:
  1. Uber/Google Maps already owns this space
  2. Liability risk on private property
  3. Low frequency = hard to build habit
```

**Triggers:** "validate my idea," "should I build this," "stress test this," "is this a good startup idea"

---

### terms-decoder

Translates ToS, Privacy Policies, and contracts into plain English. Rates each section by risk level and tells you exactly what you're agreeing to.

```
You: "Decode: [paste any ToS section]"

TERMS DECODER
────────────────────────────
Section 4.2 — Content License

Plain English:
  By posting, you give this company a permanent,
  worldwide, royalty-free license to use, copy,
  modify, and distribute your content — including
  in ads — even after you delete your account.

Risk: ⚠ CONCERNING

Why: License survives account deletion. They can
     use your content in advertising without notice
     or payment.

Action: Check privacy settings for opt-out.
        Avoid posting original creative work here.
────────────────────────────
```

**Triggers:** "decode these terms," "what does this privacy policy mean," "translate this contract," "is this ToS normal," "what am I agreeing to"

---

### hook-writer

Generates 10 hooks for any topic across 5 proven formulas. Scores each on specificity, curiosity, and relevance. Platform-specific guidance for Twitter/X, LinkedIn, YouTube, email, and blog.

```
You: "Hooks for a post about why most people fail at saving money"

HOOK GENERATOR
────────────────────────────
1. [SPECIFIC #]   83% of people who set savings goals
                  quit within 60 days. Here's why.      14/15

2. [CONTRARIAN]   Budgeting apps are why you're
                  still broke.                          13/15

3. [CURIOSITY]    The savings advice that works has
                  nothing to do with money.             13/15

4. [PAIN]         You know exactly what to do.
                  You just don't do it. Here's why.     12/15

5. [STORY]        I saved $0 for 3 years despite
                  earning more every year.              12/15
────────────────────────────
Best pick: #1 for LinkedIn/X — specificity wins
```

**Triggers:** "write hooks for," "opening line for," "make this attention-grabbing," "hook for my video," "subject line for"

---

## Compatibility

| Tool | Install path | Status |
|---|---|---|
| Claude Code CLI | `~/.claude/skills/` | ✅ Native |
| Claude.ai Projects | Project Instructions | ✅ Paste SKILL.md |
| Codex CLI | `~/.codex/skills/` | ✅ Native |
| Cursor | `.cursor/skills/` | ✅ Compatible |
| Any SKILL.md tool | Varies | ✅ Open standard |

---

## Build your own skill

```markdown
---
name: my-skill
description: When to trigger and what it does. Be specific —
             Claude undertriggers skills, so list every phrase
             and context that should activate it.
---

# My Skill

## Output format
[ASCII template Claude fills in]

## Rules
- Rule 1
- Rule 2

## Example trigger phrases
- "phrase 1"
- "phrase 2"
```

Drop it in `~/.claude/skills/my-skill/SKILL.md` and restart Claude Code.

---

## Full packs

These 5 skills are samples from larger topic-specific packs — 10 skills each:

| Pack | What's inside |
|---|---|
| Trading Skills Pack | Market scanner, squeeze detector, trade journal, earnings analyzer + 6 more |
| Developer Productivity Pack | Code reviewer, architecture advisor, tech debt auditor, PR writer + 6 more |
| Indie Founder Pack | MVP scoper, pricing strategist, launch planner, investor pitch + 6 more |
| Legal & Privacy Pack | Contract reviewer, GDPR checker, NDA generator, threat model + 6 more |
| Content & Marketing Pack | Email sequences, SEO optimizer, ad copywriter, offer builder + 6 more |

→ **[View all packs on Gumroad](https://noumenon6.gumroad.com/)**

---

## Contributing

PRs welcome. The bar:
- Structured ASCII output templates (not just prose)
- RULES section with 5+ rules
- EXAMPLE TRIGGER PHRASES with 5+
- Self-contained, no dependencies on other skills
- Under 500 lines

Open an issue first for new categories.

---

## License

MIT — use freely, modify freely, distribute freely.

---

<div align="center">

Built with [NOUMENON](https://github.com/noumenon-ai) — multi-agent AI build system

[@noumenon.ai](https://instagram.com/noumenon.ai) · [Gumroad](https://noumenon6.gumroad.com/)

⭐ Star this repo if it's useful — helps others find it

</div>
