# Prism Development Instructions

## Common Pitfalls
- The file is large (~2500 lines). Use Grep to find the section you need. Don't read the whole file unless necessary.
- Provider functions have similar signatures but different HTTP client patterns. Read the target provider AND one working provider before modifying.
- `_call_llm()` is the gateway to all LLM calls. Changes here affect every provider.
- History files are append-only JSON. Don't assume you can modify past entries.

## Testing Checklist
- After any change to prism.py, run: `python -m pytest test_prism.py -v`
- If adding a new provider: mock `_call_llm` in tests, don't require real API keys.
- If changing CLI behavior: test both `prism "question"` and `prism check "conclusion"` paths.
- If changing config: test cascade order (project → global → default).

## Style
- Keep functions under 40 lines. If longer, extract a helper within the same section.
- Group related constants together near the top.
- Use # ==== SECTION NAME ==== markers to delimit major sections.
