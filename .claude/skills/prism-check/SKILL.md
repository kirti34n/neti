---
name: prism-check
description: Challenge a conclusion before committing to it. Generates Pre-Mortem, Alt Hypothesis, Falsification, and Blind Spot challenges.
argument-hint: <conclusion to challenge>
---

# Prism Check — Challenge a Conclusion

Stress-test a conclusion using 4 research-backed strategies before committing to it.

## When to use

- User wants to challenge or stress-test a conclusion
- User says "check this", "challenge this", "is this right", "prism check"
- User is about to commit to a technical decision based on AI advice
- User has a claim or assumption they want tested

## How to run

**Path 1 — CLI available:** Run `prism json --check "$ARGUMENTS"`, parse JSON, present results.

**Path 2 — No CLI:** Generate all 4 challenges below natively.

### Generate 4 Challenges

Apply ALL of these to the conclusion:

**Pre-Mortem** — It is 18 months from now. This approach was pursued and FAILED. The failure was predictable in hindsight. Write the post-mortem: the specific failure mode, the early warning signs that were rationalized away, the moment the team should have pivoted. Be brutally concrete — "the API rate limits hit at 10K users and there was no fallback" not "scalability was an issue."

**Alt Hypothesis** — Name 3 genuinely different explanations or approaches. Not variations on a theme — structurally different mechanisms. For each: (a) the core insight that makes it work, (b) one scenario where it outperforms the conclusion, (c) the test that distinguishes them.

**Falsification** — Design the exact test that would DISPROVE this. Name the specific metric, threshold, and scenario. "If X does not achieve Y under condition Z within timeframe W, this approach is wrong." If no test can disprove it, explain why that's a red flag.

**Blind Spot** — Identify exactly ONE hidden assumption that changes the entire framing. Not a minor detail — a structural blind spot that, once seen, makes the conclusion look naive. Explain the mechanism that keeps people from seeing it.

### Present

For each challenge:
1. **Strategy name** in bold
2. The full challenge (4-8 sentences minimum — commit fully, no hedging)

End with: *"Does the original conclusion still hold?"*

## Important

Do NOT soften or balance challenges. The entire point is to stress-test. Each challenge should make the user uncomfortable with the conclusion — that's the signal it's working.
