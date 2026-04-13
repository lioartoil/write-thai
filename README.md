# write-thai

Thai prose refinement skill for Claude Code. Strips AI writing patterns, makes Thai text sound natural.

> Skill สำหรับปรับแต่งภาษาไทยใน Claude Code ตัดสำนวน AI ออก เขียนให้เหมือนคนไทยเขียน ไม่ใช่ภาษาแปล

## Why

AI-generated Thai text has recognizable patterns: translated-from-English sentence structures, overused formal connectives, paragraph-ending summaries, pronoun over-insertion, and missing casual particles. Native Thai readers notice immediately.

This skill applies research-backed rules to strip those patterns and produce natural Thai prose.

## Install

```bash
npx skills add lioartoil/write-thai -a claude-code -g -y
```

Then invoke with `/write` when editing Thai text.

## What it fixes

| Pattern | Before | After |
|---------|--------|-------|
| Translated structure | มันเป็นสิ่งสำคัญที่จะต้อง | สำคัญคือต้อง |
| Passive overuse | ระบบถูกพัฒนาขึ้นมาเพื่อ | ทีมพัฒนาระบบนี้เพื่อ |
| Paragraph summary | ...จะเห็นได้ว่าระบบนี้ดี | (deleted) |
| Pronoun insertion | ผมคิดว่าผมควรจะลองดู | คิดว่าน่าจะลองดู |
| Formal filler | อย่างแท้จริง | จริงๆ |
| Stiff connective | อย่างไรก็ตาม | แต่ |
| Rhetorical opener | ในยุคปัจจุบันที่ AI... | Claude Code ช่วยให้... |

## Rules overview

1. Preserve semantics first
2. Remove AI patterns (paragraph-ending summaries are #1 tell)
3. Smooth sentences and cut unnecessary connectives
4. Fix spelling/spacing
5. Final read-through (don't touch what's already natural)

Priority: **natural > stylized**. Don't add chat-speak to fake "human" tone.

Full rules: [`skills/write/references/write-th.md`](skills/write/references/write-th.md)

## Research basis

- **Waza write-zh.md methodology** (tw93/Waza) — execution order, anti-overcorrection philosophy
- **TCI-THAIJO translation error taxonomy** — 51% word-choice errors, 40% connective errors in English-Thai translation
- **Pantip native speaker feedback** — "ภาษาแข็งๆ แปลกๆ", "ไม่เนียน", "ภาษาโรบอท"
- **UX localization research** (Medium) — pronoun omission, gender particles, register levels
- **arxiv AI text detection** — universal patterns: low lexical diversity, predictable structures, repetition

Books for deeper study: ทฤษฎีและหลักการแปล (Chula Press), หลักการแปล (SE-ED)

## Contributing

The vocabulary table in `write-th.md` is a research-generated draft. Native speaker PRs are welcome:

- Add words/phrases that scream "AI wrote this" in Thai
- Correct mappings that don't feel right
- Add before/after examples from real AI output

## License

MIT
