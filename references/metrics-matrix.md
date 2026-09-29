# Citation and visibility metrics matrix

Benchmarks are industry-reported [I] unless labeled otherwise and vary widely by vertical. Use them to sanity-check, not as targets.

| Surface | Primary metric | Source | Secondary metrics | 2026 benchmark or datapoint |
|---|---|---|---|---|
| Traditional Google | Clicks, impressions, average position by query and page | Search Console Performance report [G] | Featured-snippet ownership; rich-result impressions | Organic CTR falls ~61% on SERPs showing an AI Overview (1.76% → 0.61%); cited brands earn ~35% more clicks than uncited [I] |
| Google AI Overviews and AI Mode | Impressions and clicks from generative AI features | Search Console Generative AI performance report [G] | Citation rate on a tracked query set (Ahrefs Brand Radar, Semrush AI Toolkit); share of AIO citations vs. competitors | AIO responses average ~13 sources; ~38% of cited URLs rank top-10 (Ahrefs, May 2026); BrightEdge reports 82% AIO trigger rate on B2B tech queries [I] |
| ChatGPT search | Referral sessions and conversions from chatgpt.com | GA4 referrer report; server logs for OAI-SearchBot and ChatGPT-User [I] | AI Citation Frequency (fixed prompt set, weekly); mention sentiment | ChatGPT ~87% of AI referral traffic (Conductor). One Seer single-site case: 15.9% conversion vs. 1.76% organic — undefined conversion event, treat cautiously [I] |
| Perplexity | Referral sessions; citation frequency on tracked prompts | GA4; server logs for PerplexityBot and Perplexity-User; Perplexity's citation links are fully visible [I] | "Ghost citation" rate (cited without brand named in answer text); pages per referred session | ~21.9 citations per answer; ~13 pages per referred session [I] |
| Copilot / Bing | AI Performance report metrics | Bing Webmaster Tools AI Performance report [I] | Bing index coverage; IndexNow acceptance | Cited passages concentrate near page top in Bing's own AI reporting (CXL) [I] |
| Claude | Referral sessions from claude.ai; citation frequency on tracked prompts | GA4; server logs for ClaudeBot, Claude-SearchBot, Claude-User; Brave Search visibility check [I] | Brave Search ranking for key terms | Fewest citations per answer among major engines [I] |
| Voice assistants | No direct report exists | Proxy: featured-snippet ownership; Business Profile discovery metrics; manual tests on Assistant/Gemini, Siri, Alexa [P] | Speakable coverage on eligible pages | No reliable public benchmark [P] |
| Cross-platform | Share of AI voice: your citations ÷ total citations across prompt set and engines | Peec AI, Otterly, ZipTie, LLMrefs, Semrush, Ahrefs Brand Radar — or a DIY weekly prompt run logged in a sheet [S] | Citation sentiment; which URLs get cited; third-party surfaces citing you | Only ~11% of domains cited by more than one engine (Profound); ~88% of AI citations come from pages outside the organic top 10 (5W synthesis) [I] |

## Minimum viable measurement stack (no paid tools)

1. Search Console → Generative AI performance report, weekly export.
2. Bing Webmaster Tools → AI Performance report, weekly export.
3. GA4 → custom segment for referrers containing chatgpt.com, perplexity.ai, claude.ai, copilot.microsoft.com, gemini.google.com.
4. Server logs → daily count of requests by AI user agent (search-time bots and live-fetch bots separately).
5. Prompt panel → 20 fixed prompts run weekly on ChatGPT, Perplexity, and Google (AI Overview and AI Mode). Log: engine, prompt, cited (Y/N), URL cited, competitors cited, sentiment.
6. Report → share of AI voice by engine, month over month; top cited URLs; top competitor URLs.

## Fixed prompt set: how to build it

- 5 definitional ("What is X?")
- 5 evaluative ("Best X for Y", "X vs Y")
- 5 procedural ("How to do X")
- 5 commercial or local ("X pricing", "X near me", "X for [industry]")

Keep the wording fixed for the whole quarter so week-over-week movement means something. Rotate at quarter end and re-baseline.
