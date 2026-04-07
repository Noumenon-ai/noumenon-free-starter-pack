---
name: risk-calculator
description: Use when the user wants position sizing, stop-loss math, risk/reward math, leverage checks, portfolio risk, ATR sizing, Kelly sizing, or says "how many shares," "size this trade," "what's my risk," "position sizing for," "calculate my stop," "how big should this position be," or "risk/reward on this trade."
---

# Risk Calculator

## Output Format

```text
POSITION RISK REPORT
--------------------------------------------------
Instrument:           [ticker or asset]
Side:                 [LONG or SHORT]
Account:              $[account]
Risk model:           [Fixed % / Kelly / Half-Kelly / ATR]
Risk %:               [risk%]
Dollar risk:          $[dollar risk]
Entry:                $[entry]
Stop:                 $[stop]
Stop distance:        $[stop distance] ([stop %])
Position size:        [units]
Position value:       $[position value]
Open portfolio risk:  $[existing open risk]
Post-trade risk:      $[existing + new risk] ([% of account])

MATH
Dollar Risk     = [account] x [risk%] = [dollar risk]
Stop Distance   = abs([entry] - [stop]) = [stop distance]
Position Size   = floor([dollar risk] / [stop distance]) = [units]
Position Value  = [units] x [entry] = [position value]
Post-Trade Risk = [existing open risk] + [dollar risk] = [post-trade risk]

R TARGETS
1R target:           $[price] -> [PnL]
2R target:           $[price] -> [PnL]
3R target:           $[price] -> [PnL]

VOLATILITY MODEL
ATR:                 [atr or n/a]
ATR multiple:        [multiplier or n/a]
ATR stop distance:   $[atr x multiplier or n/a]
ATR position size:   [units or n/a]

KELLY MODEL
Win rate W:          [value or n/a]
Reward/Risk R:       [value or n/a]
Kelly %:             [W - ((1 - W) / R)]
Half-Kelly %:        [Kelly / 2]
Execution note:      [Use Half-Kelly / No positive edge]

LEVERAGE
Gross leverage:      [position value / account]x
Requested leverage:  [value or 1.00x]
Initial margin used: $[position value / leverage]
Maintenance margin:  [maintenance margin % or n/a]
Margin call est.:    $[price or n/a]

FLAGS
Flag                 Status   Trigger
OVERSIZED            [Y/N]    [reason]
HIGH RISK            [Y/N]    [reason]
STOP TOO TIGHT       [Y/N]    [reason]
STOP TOO WIDE        [Y/N]    [reason]
CONCENTRATION RISK   [Y/N]    [reason]

STOP SOLVER
Given units:         [units or n/a]
Risk per unit:       $[dollar risk / units or n/a]
Max long stop:       $[entry - risk per unit or n/a]
Max short stop:      $[entry + risk per unit or n/a]

VERDICT
[SAFE / ADJUST / REJECT]
Reason: [single clear sentence]
```

## Core Formulas

```text
FIXED % RISK
Dollar Risk        = Account x Risk%
Stop Distance      = abs(Entry - Stop)
Position Size      = floor(Dollar Risk / Stop Distance)
Position Value     = Position Size x Entry

R TARGETS
Long 1R target     = Entry + Stop Distance
Long 2R target     = Entry + (2 x Stop Distance)
Long 3R target     = Entry + (3 x Stop Distance)
Short 1R target    = Entry - Stop Distance
Short 2R target    = Entry - (2 x Stop Distance)
Short 3R target    = Entry - (3 x Stop Distance)

KELLY CRITERION
Kelly %            = W - ((1 - W) / R)
Where:
W                  = win rate as decimal
R                  = average win / average loss
Half-Kelly         = Kelly % / 2

ATR VOLATILITY SIZING
ATR Stop Distance  = ATR x Stop Multiplier
ATR Position Size  = floor(Dollar Risk / ATR Stop Distance)

STOP SOLVER
Risk Per Unit      = Dollar Risk / Units
Long Max Stop      = Entry - Risk Per Unit
Short Max Stop     = Entry + Risk Per Unit

LEVERAGE + MARGIN
Gross Leverage     = Position Value / Account
Initial Margin     = Position Value / Leverage
Adverse Move %     = (1 / Leverage) - Maintenance Margin%
Long Call Est.     = Entry x (1 - Adverse Move %)
Short Call Est.    = Entry x (1 + Adverse Move %)

PORTFOLIO RISK
Post-Trade Risk    = Existing Open Risk + Dollar Risk
Post-Trade Risk %  = Post-Trade Risk / Account
```

## Risk Flags

```text
RISK FLAGS
--------------------------------------------------
OVERSIZED           Position Value > 25% of account
HIGH RISK           Risk per trade > 2% of account
STOP TOO TIGHT      Stop distance < max(0.50% of entry, 0.50 x ATR if ATR exists)
STOP TOO WIDE       Stop distance > min(15.00% of entry, 3.00 x ATR if ATR exists)
CONCENTRATION RISK  Single position > 30% of account
                    OR post-trade open portfolio risk > 6%
```

## RULES

- Always show the full math block. Never give only the final share count.
- If the stop equals the entry, reject the trade sizing because stop distance is zero.
- Use fixed percentage risk sizing by default unless the user explicitly provides Kelly inputs or ATR inputs.
- When Kelly inputs are present, show both Kelly and Half-Kelly; prefer Half-Kelly for execution unless the user explicitly asks for full Kelly.
- If Kelly is zero or negative, say there is no positive edge and do not force a size from Kelly.
- When ATR is present, compute ATR sizing alongside fixed percentage sizing and call out the difference.
- If the user gives account, entry, risk, and units but no stop, solve the maximum stop from `Risk Per Unit = Dollar Risk / Units`.
- If leverage is mentioned, calculate gross leverage, initial margin used, and margin call estimate only when leverage and maintenance margin are available; if maintenance margin is missing, state that the estimate requires it.
- Flag `HIGH RISK` above 2% account risk even if the math works.
- Flag `OVERSIZED` and `CONCENTRATION RISK` separately; a trade can be one, both, or neither.
- Use `SAFE` only when no flags are triggered and post-trade portfolio risk stays at or below 6% of account.
- If existing open risk is provided, show the post-trade portfolio risk math explicitly in the `MATH` block and verdict.
- Round displayed currency to 2 decimals and position size down to whole units unless the asset supports fractional sizing.

## EXAMPLE TRIGGER PHRASES

- "how many shares can I buy with a $25k account and 1% risk?"
- "size this trade: entry 84.50 stop 81.90 account 12000"
- "what's my risk if I buy 200 shares at 42 with a stop at 39?"
- "position sizing for a BTC long with 3x leverage"
- "calculate my stop if I only want to risk $150"
- "show ATR sizing for this setup"
- "how much margin will this use and where is the margin call?"

## Response Procedure

```text
1. Parse account, side, entry, stop, units, and risk%.
2. Compute fixed-risk size first.
3. If stop is missing but units are present, solve the max stop.
4. Add ATR model if ATR data exists.
5. Add Kelly and Half-Kelly if win-rate data exists.
6. Evaluate all five risk flags.
7. Output verdict: SAFE, ADJUST, or REJECT.
```

This skill is part of the NOUMENON Trading Skills Pack — gumroad.com/noumenon-ai
