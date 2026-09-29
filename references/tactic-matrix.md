# Master tactic matrix (September 2026)

Rating scale: **Core** = documented or repeatedly observed as a primary driver · **High** = strong support · **Med** = helps in some conditions · **Low** = little evidence of effect · **None** = documented as ignored · **Harmful** = documented negative.

Evidence labels: [G] Google-confirmed · [I] industry-reported · [P] pattern-based inference · [S] from an adjacent skill/playbook. The row label applies unless a cell carries its own.

| Tactic | Traditional Google / Bing | Google AI Overviews & AI Mode | Voice assistants | Perplexity | ChatGPT search | Copilot / Claude |
|---|---|---|---|---|---|---|
| Answer-first placement: direct answer in first 30% of page [I] | High (featured snippets) | Core — 55% of cited passages in first 30% (CXL) | Core [P] | Core | Core (same pattern in Bing AI reporting) | High |
| Self-contained answer passages, 40–75 words [I] | Med | Core | Core [P] | Core | Core (content-answer fit ~55% of citation likelihood, ZipTie) | High |
| Query-shaped H2/H3 headings, clear hierarchy [G] | High | High — Google recommends headings and sections for readers | High [P] | High | High | High |
| One idea per paragraph; explicit entity naming [I] | Med | High — 15+ recognized entities reported 4.8× selection (vendor figure) | Med [P] | High | High | High |
| Real HTML comparison tables for X-vs-Y queries [I] | High (table snippets) | High | Low — cannot be read aloud; add prose summary | High | High | High |
| Statistics with named, dated sources [S] | Med | High | Low | Core (+37–40%, Princeton GEO) | High | Core for Claude (factual density) |
| Named author, credentials, bio page (E-E-A-T) [G] | Core | Core — 96% of AIO citations reported to carry strong E-E-A-T signals [I] | Med | High | High | High |
| Original, non-commodity, first-hand content [G] | Core | Core — Google calls this the largest long-run influence | Med | High | High | High |
| Visible "last updated" date and honest dateModified [I] | Med | High | Med | High (time-decay reranking) | Core (30-day freshness ~3.2×) | Med |
| Domain authority and backlinks [I] | Core | High | Med | Med | High (~40% of citation weight, SE Ranking) | Med |
| Third-party presence: Reddit, Wikipedia, YouTube, LinkedIn, review sites [I] | Med | High — these dominate most-cited domain lists | Low | High (Reddit-concentrated) | Core (Wikipedia ~7.8% of citations) | High (LinkedIn, GitHub for Copilot) |
| Visible FAQ section in natural-language questions [I] | Med | Med | High | High (reported preference; unconfirmed) | Med | Med |
| Schema / structured data (JSON-LD) [G] | High — rich-result eligibility | None required — "no special schema" | Med — Speakable, limited scope | Med — reported, unconfirmed [I] | Low — unconfirmed | Med — Bing parses markup |
| Images and video with descriptive alt text [G] | Med | High — Google recommends; 78% of featured sources reportedly multimodal [I] | Low | Med | Med | Med |
| Topical cluster depth and publishing cadence [S] | High | High | Low | High (velocity reported to matter) | Med | Med |
| Public PDFs of original research [S] | Low | Low | None | High (reported) | Med | Med |
| llms.txt / llms-full.txt [G] | None — Google ignores | None | None | Low — 97% of files get zero traffic (Ahrefs) [I] | Low — OpenAI agent contexts only | Low — Anthropic recommends for agent docs, not search |
| Content "chunking" or AI-specific rewrites [G] | Not needed | Not needed — documented | Not needed | Unverified | Unverified | Unverified |
| Capturing every long-tail keyword variation [G] | Med, declining | Not needed; scaled variants can violate spam policy | Low | Harmful — keyword stuffing −10% (Princeton) | Harmful | Harmful |
| Paid or inauthentic mentions [G] | Harmful | Harmful — documented as ineffective and policy-adjacent | None | Harmful | Harmful | Harmful |

## Tactics that help everywhere (do these first)

1. Answer block (40–75 words) in the top third of the page.
2. Query-shaped headings with no skipped levels.
3. One idea per paragraph; every statistic with value, unit, source, date.
4. Real HTML tables with a prose summary above.
5. Named author with credentials and a bio page; honest dates.
6. At least one non-commodity, first-hand element per page.
7. All AI search bots allowed; content server-rendered; no nosnippet on the body.
8. Authentic third-party presence for the topic (community, video, industry press).

## Surface-specific additions (thin layer on top)

- **Google AI Overviews / AI Mode:** images and video with alt text; Merchant Center and Business Profile for commerce and local; enable generative features in Search Console.
- **ChatGPT search:** freshness (refresh competitive pages monthly); Wikipedia and Bing index presence; plain, direct prose.
- **Perplexity:** visible FAQ; public PDFs of research; steady publishing cadence; PerplexityBot allowed.
- **Copilot:** Bing Webmaster Tools + IndexNow; sub-2-second loads; LinkedIn presence.
- **Claude:** verify Brave Search visibility; maximize factual density and attribution.
- **Voice:** a spoken-register answer sentence under 30 words; Speakable if eligible; LocalBusiness aligned with Business Profile.

## 90-day rollout skeleton (built backward)

Target at day 90: measured citation share on a fixed 20-prompt set across Google AI Overviews, ChatGPT, and Perplexity, with a repeatable weekly measurement.

| Window | Milestone | Work |
|---|---|---|
| Days 61–90 | Citation share measured and rising; second wave live | Refresh next 10 pages; authentic distribution for wave one; compare week-over-week; drop tactics showing no movement |
| Days 31–60 | First 10 priority pages restructured; dashboard running | Apply the structuring guide to the 10 pages with highest impressions for the prompt set; Person/Organization/Article schema site-wide; set up all reports and the weekly prompt run |
| Days 15–30 | Access layer clean; baseline recorded | Fix robots.txt, JS rendering, snippet directives, canonicals, sitemaps, IndexNow; confirm Bing and Brave coverage; run and log the 20-prompt baseline |
| Days 1–14 | Prompt set and page inventory agreed; labeled gap analysis done | Choose 20 prompts by business value; map each to a page or gap; audit against the checklist; classify fixes by layer |
