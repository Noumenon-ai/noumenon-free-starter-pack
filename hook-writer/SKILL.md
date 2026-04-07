---
name: hook-writer
description: Use when the user wants stronger openings for posts, videos, emails, articles, landing pages, or ads and says "write hooks for," "opening line for," "make this attention-grabbing," "hook for my video," "subject line for," "headline ideas," "rewrite this weak opener," or "give me better hooks."
---

# Hook Writer

## Output Format

```text
HOOK GENERATOR
--------------------------------------------------
Topic:                [topic]
Audience:             [audience]
Platform:             [X / LinkedIn / YouTube / Email / Blog]
Goal:                 [click / read / reply / watch / share]

TOP 10 HOOKS
1. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
2. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
3. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
4. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
5. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
6. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
7. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
8. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
9. [FORMULA] [hook text]
   Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15
10. [FORMULA] [hook text]
    Score: Specificity [1-5] + Curiosity [1-5] + Relevance [1-5] = [total]/15

BEST PICK
Hook:                 [best-performing option]
Why:                  [short rationale]

A/B VARIANTS
A. [variant]
B. [variant]
C. [variant]

ANTI-PATTERN CHECK
Weak opener:          [original weak line if provided]
Why weak:             [vague / generic / low stakes / no novelty]
Rewrite:              [stronger line]
```

## Hook Formula Library

```text
PATTERN INTERRUPT
Definition: Break the reader's default expectation fast.
Example: "Stop posting more. Start posting narrower."

BOLD CLAIM
Definition: Make a sharp, defensible claim that invites reaction.
Example: "Most productivity advice makes good people slower."

CURIOSITY GAP
Definition: Reveal a result but withhold the mechanism.
Example: "The email tweak that doubled replies had nothing to do with copy."

CONTRARIAN
Definition: Attack the accepted belief and replace it.
Example: "Consistency is overrated. Precision is what compounds."

SPECIFIC NUMBER
Definition: Use a precise number to signal proof or concreteness.
Example: "7 landing-page edits that lifted conversion by 18%."

PAIN POINT
Definition: Name the frustration the audience already feels.
Example: "You are not lazy. Your workflow is leaking attention."

STORY OPEN
Definition: Start inside a moment with tension or consequence.
Example: "I almost killed the launch 10 minutes before checkout opened."
```

## Platform Notes

```text
PLATFORM FIT
X / TWITTER       Short, punchy, opinionated, first 8 words matter most
LINKEDIN          Strong professional payoff, clear lesson, less slang
YOUTUBE           Promise a payoff or reveal in spoken rhythm
EMAIL SUBJECT     Tight, curiosity-heavy, high clarity, no wasted words
BLOG HEADLINE     Search-friendly clarity plus one clear angle
```

## Platform-Specific Hook Patterns

```text
X / TWITTER
Template: [sharp opinion] + [specific payoff]
Example: "Most remote teams do not need more meetings. They need one better handoff."

LINKEDIN
Template: [professional insight] + [evidence or result]
Example: "We cut onboarding time by 41% after removing one 'best practice.'"

YOUTUBE
Template: [pain or curiosity] + [promised reveal]
Example: "Why smart teams still miss deadlines, and the fix nobody teaches."

EMAIL SUBJECT
Template: [specific result] or [tight curiosity question]
Example: "The 12-minute fix for slower weekly reviews"

BLOG HEADLINE
Template: [keyword/topic] + [clear angle] + [payoff]
Example: "Remote Work Productivity: 7 Workflow Fixes That Reduce Context Switching"
```

## Anti-Patterns

```text
ANTI-PATTERNS
--------------------------------------------------
"Here are some tips..."         -> weak because generic; lead with outcome or tension
"I wanted to share..."          -> weak because self-focused; lead with reader value
"Let's talk about..."           -> weak because low stakes; name the consequence
"In today's world..."           -> weak because empty; replace with a specific claim
"This changed everything..."    -> weak because vague; specify what changed and by how much
```

## RULES

- Generate 10 hooks using at least 5 distinct formulas.
- Default to 2 hooks per formula across 5 formulas unless the user requests a different mix.
- Score every hook with `Specificity + Curiosity + Relevance` out of 15.
- Match the hook to the requested platform; do not write email subjects like YouTube titles.
- Prefer concrete nouns, outcomes, tensions, and numbers over generic adjectives.
- If the user supplies a weak opener, diagnose why it fails and rewrite it.
- Pick one best hook and produce 3 A/B variants of that same angle.
- Avoid clickbait that the body cannot support.
- Keep hooks short enough to survive the platform's first-line truncation when possible.
- When the topic is technical, preserve accuracy; novelty cannot come from false claims.

## EXAMPLE TRIGGER PHRASES

- "write hooks for my post about remote work productivity"
- "opening line for a video about cold outreach"
- "make this attention-grabbing"
- "hook for my video about debugging faster"
- "subject line for an email about churn reduction"
- "rewrite this weak headline"
- "give me 10 better hooks for this topic"

## Generation Procedure

```text
1. Identify topic, audience, platform, and goal.
2. Generate 10 hooks across at least 5 formulas, defaulting to 2 hooks each from 5 formulas.
3. Score each hook out of 15.
4. Rank them and choose the best pick.
5. Create 3 A/B variants from the winning angle.
6. If a weak opener exists, rewrite it in the anti-pattern check.
```

This skill is part of the NOUMENON Content & Marketing Pack — gumroad.com/noumenon-ai
