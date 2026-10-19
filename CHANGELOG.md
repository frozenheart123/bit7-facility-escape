# Changelog

## 1.0.1 (2026-10-19)

Fixes from testing every level with the live Claude agent on claude.ai.

- LV6: the whiteboard now reads “VAULT CODE / 6043” (Claude read “VAULT 6043” as the vault's name), and the decorative terminal that looked readable in the screenshot is gone
- LV7: power cells now report “indicator amber”, matching DOC-14, so a careful agent can verify the precondition. The planner puts its evidence in the hand-off, and the executor trusts evidence the planner cites
- LV9: the agent is told whether memory holds notes from earlier shifts, so shift 2 checks memory instead of redoing shift 1. The terminal note now has a date and an author
- LV10: when nothing leaks with every guardrail rule off, the guardrail check says that was the model's choice, not a control
- “1 note” instead of “1 notes”

## 1.0.0 (2026-10-13)

First public release.

- 12 levels: tool use, RAG and hallucination, planning, embeddings and chunking, prompt injection and human approval, multimodal, multi-agent, tool design, memory, guardrails and PII, workflow vs agent, vector databases
- Live flow diagram, speech bubbles and pictograms (picture-first learning)
- Knowledge explorer: keyword vs vector search, 2D vector map, chunk size and top-k controls
- API view with the equivalent Messages API request and the tool-use loop
- Evals: repeated runs with success rate, tokens and time
- Codex: 20 illustrated concept cards with quizzes
- Knowledge check: 16 scenario questions with levels and a shareable result
- System check: 30 automated checks, also runnable via `#selftest`
- In-game player guide
- English and Simplified Chinese
