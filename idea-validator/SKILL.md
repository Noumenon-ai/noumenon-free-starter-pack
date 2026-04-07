---
name: idea-validator
description: Use when the user wants to validate a startup, app, SaaS, marketplace, creator, or product idea and says "validate my idea," "is this a good startup idea," "stress test this," "should I build this," "critique my idea," "tear apart this idea," or "is there a real business here."
---

# Idea Validator

## Output Format

```text
IDEA VALIDATION REPORT
--------------------------------------------------
Idea:                 [one-line description]
Target customer:      [ICP]
Problem statement:    [pain in one sentence]

SIX-DIMENSION SCORE
Problem Clarity:      [1-5]
Market Size:          [1-5]
Willingness to Pay:   [1-5]
Competition Density:  [1-5]
Founder-Market Fit:   [1-5]
Distribution Path:    [1-5]
Total:                [0-30]
Score band:           [KILL / ITERATE / BUILD / MOVE FAST]

SCORE READ
Strongest dimension:  [dimension]
Weakest dimension:    [dimension]

DEVIL'S ADVOCATE
1. [hard argument against the idea]
2. [hard argument against the idea]
3. [hard argument against the idea]

RISKIEST ASSUMPTION
Assumption:           [single make-or-break belief]
Test under 2 weeks:   [specific action]
Budget cap:           [$0-$100]
Pass signal:          [numeric threshold]
Fail signal:          [numeric threshold]

VERDICT
[KILL / PIVOT / VALIDATE FIRST / BUILD]
Rationale: [direct explanation]
```

## Scoring Rubric

```text
SCORING SCALE
1 = weak / unclear / unattractive
3 = workable but unproven
5 = strong and clearly evidenced

DIMENSIONS
Problem Clarity       1 vague or nice-to-have
                      3 recurring pain with partial urgency
                      5 sharp, frequent, expensive pain

Market Size           1 tiny or shrinking niche
                      3 viable niche with room for a small business
                      5 large or expanding market with many reachable buyers

Willingness to Pay    1 users expect free
                      3 some segment will pay if ROI is clear
                      5 clear budget owner and painful status quo

Competition Density   1 crowded with entrenched winners
                      3 mixed market, some whitespace
                      5 fragmented or underserved market

Founder-Market Fit    1 no insight, access, or credibility
                      3 some relevant exposure
                      5 deep lived pain, network, or proven edge

Distribution Path     1 no credible go-to-market path
                      3 one plausible but unproven channel
                      5 repeatable low-cost path to customers
```

## Thresholds

```text
THRESHOLDS
< 15      = KILL
15 - 22   = ITERATE
23 - 28   = BUILD
29 - 30   = MOVE FAST

VERDICT MAPPING
KILL       -> verdict usually KILL
ITERATE    -> verdict usually PIVOT or VALIDATE FIRST
BUILD      -> verdict usually BUILD
MOVE FAST  -> verdict BUILD with urgency
```

## RULES

- Score each dimension from 1 to 5 with real justification, not optimism.
- Treat `Competition Density` as favorable only when the market is fragmented or underserved; crowded red oceans score low.
- Always give the three strongest arguments against the idea with no softening.
- Name exactly one riskiest assumption, not a list.
- The test plan must be executable in under 2 weeks for under $100.
- Use numeric pass and fail signals whenever possible.
- If the idea is missing an ICP or business model, infer cautiously and say the inference explicitly.
- Do not recommend building when `Willingness to Pay` or `Distribution Path` scores 1 unless the user is intentionally building a hobby project.
- `VALIDATE FIRST` is the default verdict when the score lands in `ITERATE` and the core assumption can be tested cheaply.

## EXAMPLE TRIGGER PHRASES

- "validate my idea: AI scheduling for plumbers"
- "is this a good startup idea?"
- "stress test this marketplace concept"
- "should I build this SaaS for agencies?"
- "critique my idea with no sugarcoating"
- "tear apart this app concept"
- "is there a real business here or not?"

## Analysis Sequence

```text
1. State the idea, ICP, and pain in one line each.
2. Score all six dimensions.
3. Sum the score and label the score band.
4. Write the 3 strongest arguments against the idea.
5. Identify the single riskiest assumption.
6. Design the cheapest credible test under 2 weeks / under $100.
7. Output the verdict: KILL, PIVOT, VALIDATE FIRST, or BUILD.
```

This skill is part of the NOUMENON Indie Founder Pack — gumroad.com/noumenon-ai
