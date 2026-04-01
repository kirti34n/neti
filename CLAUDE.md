# Prism Project Instructions

## Architecture
- Single file: `prism.py`. Everything lives here. Do not split into modules.
- Zero external dependencies. stdlib only. This is a hard rule.
- ~2500 lines. Read the relevant section before changing anything.

## Key Concepts
- Prism generates divergent perspectives on questions using 6 LLM providers (Ollama, Gemini, OpenAI, Anthropic, MiniMax, DeepSeek)
- Measures cognitive shift: how much a user's thinking changes after seeing perspectives
- Has two modes: `explore` (full flow) and `check` (challenge a conclusion)
- Also a Claude Code skill via `.claude/skills/prism/SKILL.md`

## Code Patterns
- Provider logic uses a registry pattern (`PROVIDERS` dict with `generate` callables)
- Config cascades: project `.prism.json` → global `~/.config/prism/config.json` → auto-detect
- All LLM calls go through `_call_llm()` with provider-specific adapters
- History stored as JSON in `~/.config/prism/history/`
- Measurement uses cosine similarity on word vectors (no ML deps)

## Testing
- Tests in `test_prism.py`. Run: `python -m pytest test_prism.py -v`
- Test without API keys by mocking `_call_llm`

## When Modifying
- Keep the single-file constraint. If it feels too big, refactor within the file.
- Match existing code style: compact, minimal comments, no docstrings on private funcs.
- Don't add type hints to existing functions unless you're already modifying them.
- The setup/install commands modify external config files — test those paths carefully.
