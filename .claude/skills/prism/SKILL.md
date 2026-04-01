---
name: prism
description: Generate divergent perspectives on a question using research-backed cognitive strategies. Reveals how AI shapes your thinking.
argument-hint: <question or topic>
---

# Prism — Divergent Perspectives

Generate structurally different perspectives using 10 research-backed cognitive strategies.

## When to use

- User asks for perspectives, different angles, challenges thinking, says "prism"
- User is making a decision or evaluating approaches
- User wants to stress-test a technical approach

## How to run

**Path 1 — CLI available:** Run `prism json "$ARGUMENTS"`, parse the JSON output. It includes divergence scores and tracking. Present using the format in Step 4.

**Path 2 — No CLI:** Generate natively using the steps below.

### Step 1: Default Answer

Give the most practical, specific answer to the question. 3-4 sentences. Name specific technologies, approaches, or steps — not vague principles.

### Step 2: Generate 3 Perspectives

Pick 3 strategies from the table below. Each MUST follow its structural constraint exactly. Do NOT hedge or qualify — commit fully to the perspective.

| Strategy | Constraint |
|----------|-----------|
| Devil's Advocate | Argue AGAINST the common position. No hedging. Real failure examples. |
| Pre-Mortem | 18 months from now, this failed. Write the post-mortem. Specific failure modes. |
| Falsification | Design the exact test that would disprove this. Metric, threshold, timeframe. |
| Blind Spot | ONE hidden assumption that changes the entire framing. The mechanism that hides it. |
| Alt Hypothesis | 3 structurally different explanations. Core insight, scenario where it wins, distinguishing test. |
| First Principles | List 2-3 "everyone knows" assumptions. Show where each breaks. Rebuild without them. |
| Inversion | Answer the exact opposite question in detail. What does the inversion reveal? |
| Systems | Only 2nd/3rd order effects. Follow causal chains 3 steps. Name feedback loops. |
| Stakeholder | Who gets harmed? Tell the story from their perspective. Make the friction concrete. |
| Adjacent Field | Pick a specific field that solved an analogous problem. Map their technique onto this. |

### Step 3: Rank by Divergence

Order perspectives by how different each is from the default. Most divergent first.

### Step 4: Present

**Default Answer**
[the default — 3-4 sentences]

---

**Divergent Perspectives**

**1. [Strategy Name]**
[Full perspective text — 4-8 sentences minimum]

**2. [Strategy Name]**
[Full perspective text]

**3. [Strategy Name]**
[Full perspective text]

---

*Do any of these shift how you're thinking about this?*

## Important

Do NOT paraphrase, shorten, or editorialize perspectives. The value is in the specifics, examples, and concrete details. Each perspective should commit fully to its position — no "on the other hand" hedging. If a perspective names specific technologies, failure modes, or examples, keep them all.
