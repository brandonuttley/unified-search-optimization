# unified-search-optimization

A Claude Skill that treats SEO, AEO (answer engine optimization), and GEO (generative engine optimization) as one discipline with three retrieval patterns. It gives Claude a five-layer framework, four comparison matrices (tactics, technical requirements, schema, metrics), an eleven-step content structuring guide with a pre-publish checklist, and an evidence register that separates Google-confirmed guidance from industry studies and inference.

Current as of **September 29, 2026**. It reflects Google's May 15, 2026 generative-AI guidance, the May 7, 2026 end of FAQ rich results, and 2026 citation studies from Ahrefs, CXL, Profound, and others.

## What it does

- **Strategy:** builds a plan backward from a day-90 citation-share goal, classifying every gap by layer (Access → Structure → Authority → Presence → Selection).
- **Structure new content:** enforces answer-first placement, 40–75 word passages, query-shaped headings, real HTML tables with prose summaries, visible FAQs, author credentials, and honest dates.
- **Audit existing pages:** runs a fifteen-line pre-publish checklist and reports pass/fail with fixes ordered by layer.
- **Schema and technical decisions:** post-May-2026 status of fourteen schema types; crawler, rendering, and index requirements per engine; a robots.txt starting point.
- **Measurement:** a no-paid-tools measurement stack and a fixed-prompt-panel method for tracking share of AI voice.

Every recommendation carries an evidence label: **[G]** Google-confirmed, **[I]** industry-reported, **[P]** pattern-based inference, **[S]** from an adjacent playbook.

## Structure

```
unified-search-optimization/
├── SKILL.md                              # workflow, modes, framework, conventions
├── README.md
├── references/
│   ├── tactic-matrix.md                  # 20 tactics × 6 surfaces + 90-day rollout
│   ├── technical-requirements.md         # Access layer per engine; robots.txt starter; audit sequence
│   ├── schema-matrix.md                  # 14 schema types, post-May-2026 status, minimal JSON-LD
│   ├── metrics-matrix.md                 # what to measure, where, 2026 benchmarks
│   ├── content-structuring-guide.md      # 11 steps + pre-publish checklist
│   └── evidence-register.md             # every source, dated and labeled
├── assets/
│   └── page-template.md                  # fill-in page skeleton
└── evals/
    └── evals.json                        # test prompts
```

## Install

**Claude.ai / Claude Desktop:** zip the folder (or use the `.skill` file from Releases) and add it under Settings → Capabilities → Skills.

**Claude Code:** copy the folder into `.claude/skills/` in your project or `~/.claude/skills/` for all projects.

## Keep it current

The evidence register lists every figure with its date. Re-verify anything older than six months before treating it as current. The fastest-moving items: which AI bots exist and their names, Google's generative-AI documentation, and per-engine citation-share studies.

## Example prompts

- "Audit this page and tell me why Perplexity cites our competitor instead of us."
- "Outline a page on [topic] that works for Google, AI Overviews, voice, and ChatGPT."
- "Our agency says we need FAQ schema and llms.txt for AI search. Is that right?"
- "Set up AI-citation tracking with Search Console, Bing Webmaster Tools, and GA4 only."

## Author

Brandon Uttley — PMP, marketing operations and coordination architecture, FINRA-compliant content workflows.
