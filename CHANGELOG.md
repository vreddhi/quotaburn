# QuotaBurn changelog

## 2026-10-19 (Monday price re-verify)

### Confirmed price / data changes
- **Claude Fable 5.1** cache-read: previously unset → **$0.25 / 1M tokens** ([claude.com/pricing](https://claude.com/pricing)).
- **Claude Haiku 5.5** cache-read (prompts ≤100K): previously unset → **$0.125 / 1M tokens** ([claude.com/pricing](https://claude.com/pricing)).
- **Claude Opus 5.5** cache-read **$0.20** confirmed; removed “confirm” caveat.
- **OpenAI Codex / ChatGPT Pro 200**: noted that grandfathered higher allowance ends **2026-10-29**; price stays $200/mo ([help.openai.com/en/articles/9793128](https://help.openai.com/en/articles/9793128)).
- **Windsurf** `source` URL updated to `https://devin.ai/blog/windsurf-pricing-plans` (windsurf.com blog redirects there). Plan prices unchanged: Free $0 / Pro $20 / Teams $40 seat / Max $200.

### Re-verified, no price change
- Tools: Claude Code, Cursor, OpenAI Codex, GitHub Copilot, Devin, Gemini CLI (seat prices still unverified).
- Models: all OpenAI, Gemini, and xAI rows in `src/data.json` (Gemini 4 Argon still doubles 2026-12-01; Gemini 3.8 Flash doubles 2027-01-01; GPT-5.6 Sol promo ≥ 2026-11-21).
- Claude Max 20x exact list price still **unverified** (page still says “From $100”).

### New page
- `/chatgpt-pro-200-grandfathering/` — what happens when Pro 200 grandfathering ends Oct 29, 2026.

### Fetch notes
- WebFetch returned 404 for `https://windsurf.com/blog/windsurf-pricing-plans` and `https://devin.ai/blog/windsurf-pricing-plans`; curl followed the redirect and confirmed 200 + prices.
- `https://devin.ai/pricing` returned 404 via WebFetch; plan prices confirmed via `https://docs.devin.ai/admin/billing/self-serve`.
