# QuotaBurn changelog

## 2026-10-27 (new model + copy fix)

### Confirmed price / data changes
- **GPT-6.1 Terra** added (released 2026-10-26): **$1 in / $0.05 cached / $5 out** per 1M tokens, standard, ≤272K input tokens ([platform.openai.com/docs/pricing](https://platform.openai.com/docs/pricing), fetched 2026-10-27; matches [openai.com/index/introducing-gpt-6-1-terra](https://openai.com/index/introducing-gpt-6-1-terra/)). Batch is $0.50 / $0.025 / $2.50.
- **/codex-vs-claude-code-cost/** FAQ: removed the stale "Sonnet 5.5 has no cache price listed" claim. Claude Sonnet 5.5 cache read is $0.10, the same as GPT-6.1 Sol, so the two have identical list prices ($2 / $0.10 / $10; claude.com/pricing re-checked 2026-10-27).

## 2026-10-26 (Monday price re-verify)

### Confirmed price / data changes
- **Claude Haiku 5.5** (prompts ≤100K tokens) corrected: was $0.50 in / $2.50 out / $0.125 cache read → **$0.10 in / $0.50 out / $0.01 cache read** per 1M tokens. The old row mixed the >100K input/output prices with the ≤100K cache-write price. Added the >100K tier as `over_threshold`: **$0.50 / $2.50 / $0.05 cache read** ([claude.com/pricing](https://claude.com/pricing), page HTML read 2026-10-26).
- **Claude Sonnet 5.5** cache read: previously unset → **$0.10 / 1M tokens** (cache write $2.50) ([claude.com/pricing](https://claude.com/pricing)).
- **GitHub Copilot** Free limits text: removed "50 chat requests" (no longer on the page); the page now says Free gets 2,000 completions/month plus limited chat and agent usage ([github.com/features/copilot/plans](https://github.com/features/copilot/plans)).

### Re-verified, no price change
- Tools: Claude Code (Max 20x price still **unverified**, page still says "From $100"), Cursor, OpenAI Codex, GitHub Copilot, Windsurf/Devin Desktop, Devin, Gemini CLI (Code Assist seat prices still unverified; 1,500/2,000 requests per user per day confirmed).
- Models: Fable 5.1, Opus 5.5, legacy Opus 5, legacy Sonnet 4.6; all OpenAI rows; all Gemini rows; all xAI rows.
- Watch items: ChatGPT Pro 200 grandfathering still ends **2026-10-29**, price stays $200 ([help.openai.com/en/articles/9793128](https://help.openai.com/en/articles/9793128)). Gemini 4 Argon is still $2/$10 through Nov 30 and $4/$20 from **2026-12-01** (cache $0.10 → $0.20). Gemini 3.8 Flash doubles 2027-01-01. GPT-5.6 Sol promo pricing still "at least through November 21, 2026" (platform.openai.com and learn.chatgpt.com).

### New page
- `/claude-api-pricing/`: Claude API pricing for Fable 5.1, Opus 5.5, Sonnet 5.5 and Haiku 5.5, plus the Haiku 100K-token threshold, legacy models and a monthly cost example (all from data.json).

### Fetch notes
- WebFetch's markdown of claude.com/pricing dropped the Read/Write labels on Haiku/Sonnet. I used curl on the raw HTML to confirm each label.
- Devin sources and Google quotas were confirmed with curl (200).

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
