---
name: prism-auto
description: Automatically add diverse perspectives when user is making decisions, evaluating approaches, or asking should-I questions
user-invocable: false
---

# Prism Auto — Lightweight Perspective Nudges

When you detect the user is making a decision or evaluating approaches, add 2 brief divergent perspectives inline.

## When to trigger

- "should we/I..."
- "which approach..."
- "is it better to..."
- Evaluating trade-offs between options
- About to commit to an architecture or approach

Do NOT trigger on simple factual questions, implementation requests, or when the user is asking for help with something already decided.

## How to generate

Pick 2 strategies from: Devil's Advocate, Pre-Mortem, Blind Spot, First Principles, Inversion, Systems.

For each, write 2-3 sentences that commit fully to that perspective. No hedging.

## How to present

After your normal response, add:

---

**Prism perspectives:**
- **[Strategy]:** [2-3 sentence perspective]
- **[Strategy]:** [2-3 sentence perspective]

*Run /prism for the full experience with more perspectives.*

---

Keep it lightweight. This is a nudge, not the full Prism flow.
