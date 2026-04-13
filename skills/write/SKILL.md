---
name: write
description: Invoke when writing or editing Thai prose. Strips AI writing patterns and rewrites to sound natural. Not for code comments, commit messages, or inline docs.
---

# /write Thai

Refine Thai prose by applying the rules in `references/write-th.md`.

## When to use

- Writing or editing Thai text (articles, messages, KS posts, team communication)
- Reviewing AI-generated Thai output before publishing
- Localizing English content into natural Thai

## When NOT to use

- Code comments, commit messages, inline documentation
- English or Chinese prose (use Waza's `/write` instead)
- Translation tasks (this refines Thai output, not translates)

## Workflow

1. Read the Thai text to refine
2. Apply rules from `references/write-th.md` in order:
   - Preserve semantics
   - Remove AI patterns (paragraph-ending summaries first)
   - Smooth sentences
   - Check spelling/spacing
   - Final read-through
3. Output the refined text
4. Do NOT explain the changes unless asked
