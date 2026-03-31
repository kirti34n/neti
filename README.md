# Prism

**Think different. Not different answers. Different angles.**

One question through multiple lenses. Measures how your thinking shifts. Works with any LLM.

Most AI tools give you one answer and agree with everything you say. Prism splits your question through structurally different perspectives — devil's advocate, blind spots, first principles, edge cases, security audit — and measures whether seeing those perspectives actually changes how you think.

## Why

- AI models are [sycophantic](https://news.stanford.edu/stories/2026/03/ai-advice-sycophantic-models-research) — they agree with you 49% more than humans do
- AI assistance [harms subsequent unassisted thinking](https://news.harvard.edu/gazette/story/2025/11/is-ai-dulling-our-minds/) (MIT, Harvard studies)
- AI [homogenizes](https://designobserver.com/suddenly-everyones-life-got-a-lot-more-similar-ai-isnt-just-imitating-creativity-its-homogenizing-thinking/) collective output
- No tool exists that challenges your thinking instead of validating it

## Install

```bash
pip install sentence-transformers  # for measuring thinking shifts
git clone https://github.com/YOUR_USERNAME/prism.git && cd prism

# Configure your LLM (pick one):
export OPENAI_API_KEY=sk-...        # OpenAI
export ANTHROPIC_API_KEY=sk-...     # Claude
export GOOGLE_API_KEY=...           # Gemini
# OR just have Ollama running       # Local (auto-detected)

python3 prism.py think
```

Works with **any LLM**: OpenAI, Claude, Gemini, Ollama (local), OpenRouter, or any OpenAI-compatible endpoint.

## Usage

```bash
# General thinking — before/after measurement
prism.py explore "Should I quit my job?"

# Coding perspectives — edge cases, security, simplify, scale, review
prism.py code "JWT auth API with refresh tokens"

# What's on your mind?
prism.py think

# Just show perspectives (no measurement)
prism.py quick "Is microservices the right architecture?"

# See how your thinking is changing over time
prism.py insights

# Recent sessions
prism.py history

# Configuration
prism.py config                    # show current
prism.py config provider openai    # switch provider
prism.py config model gpt-4o      # switch model

# MCP server (for Claude Code, Codex, Cursor, etc.)
prism.py serve
```

## How It Works

### The Explore Loop

```
1. You answer first (before seeing anything)
2. Prism generates perspectives through your LLM:
   - Default answer (the control)
   - 4 structural perspectives (selected from 16 strategies)
3. Picks the 3 most DIVERGENT from default (by embedding distance)
4. Shows you: default + divergent perspectives
5. You answer again
6. Measures: how far you shifted, toward which perspective, independence score
7. You rate which perspective was most useful (optional, one keystroke)
```

### 16 Perspective Strategies

Not role-playing ("pretend you're a contrarian"). **Structural constraints** that force genuinely different output shapes:

**Thinking:**
| Strategy | What it forces |
|---|---|
| Devil's Advocate | Argue AGAINST the common position. No hedging. |
| Blind Spot | Name exactly ONE thing everyone misses. |
| First Principles | List assumptions, negate each, rebuild. |
| Temporal | Answer from 50 years ago, today, 50 years from now. |
| Stakeholder | Write ONLY from who gets hurt. |
| Systems | Only second and third-order effects. |
| Constraint Removal | Remove the biggest constraint. What changes? |
| Emotional | No analysis. Only fears, hopes, anxieties. |
| Inversion | Answer the exact opposite question. |

**Coding:**
| Strategy | What it forces |
|---|---|
| Edge Cases | 3-5 most dangerous failure modes in production. |
| Security | Specific vulnerability classes (OWASP). Attack surface. |
| Simplify | 50% simpler solution. Fewer files, fewer abstractions. |
| Scale | What breaks at 10x, 100x, 1000x? |
| Code Review | Senior engineer PR review. What will cause pain later. |
| Alt Stack | Same problem, completely different technology. |

The system learns which strategies challenge YOU most and weights toward those over time.

## Measurement

After each session, Prism measures:

- **Shift**: How far your thinking moved (cosine distance of before/after embeddings)
- **Direction**: Toward a perspective? Toward the default? Or independent territory?
- **Independence**: How far you are from any AI-generated response

Over time (`prism insights`):
- **Convergence tracking**: Are you becoming more like the AI default? (The sycophancy detector)
- **Strategy ranking**: Which perspectives actually shift your thinking?
- **Topic patterns**: Where do you shift most? Where are you rigid?

## Integration with Coding Tools

### MCP Server (Claude Code, Codex, Cursor, Cline)

```bash
# Start MCP server
pip install fastmcp
python3 prism.py serve

# Register with Claude Code
claude mcp add prism -- python3 /path/to/prism.py serve

# Register with Codex
# Add to ~/.codex/config.toml
```

### Machine-Readable Output (for hooks/scripts)

```bash
# JSON output for integration
python3 prism.py json "your question"
python3 prism.py json "your code task" --code
```

## How It Actually Helps (Research)

| Mechanism | Research | How Prism implements it |
|---|---|---|
| Self-explanation | Chi et al. 1989 (d > 0.8) | You MUST state your view before seeing AI |
| Guided reflection | Lew & Schmidt 2011 | Specific structural perspectives, not open-ended |
| Friction prevents dependency | Bastani et al. 2024 (n=1000+) | Think first, THEN see AI |
| Anti-sycophancy | Stanford 2026 | Perspectives selected for MAX divergence |
| Metacognitive monitoring | Flavell 1979 | Shift measurement makes patterns visible |

## Configuration

```bash
prism.py config provider ollama          # Ollama (local, default)
prism.py config provider openai          # OpenAI
prism.py config provider anthropic       # Claude
prism.py config provider gemini          # Gemini
prism.py config provider openrouter      # OpenRouter
prism.py config provider custom          # Any OpenAI-compatible
prism.py config model gpt-4o-mini        # Set model
prism.py config endpoint http://host:1234/v1  # Custom endpoint
prism.py config temperature 0.9          # Higher = more diverse
prism.py config num_perspectives 5       # More perspectives per run
```

## Philosophy

Born from [SPARK](https://github.com/YOUR_USERNAME/spark) — 18 versions of testing computational creativity tools. Every version proved: the machinery doesn't matter. What matters is putting a human in front of genuinely different perspectives and measuring what happens.

Prism is the experiment that 18 versions avoided: **does seeing where AI can think differently change how YOU think?**

## License

MIT
