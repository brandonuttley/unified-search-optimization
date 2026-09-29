# Technical requirements matrix — the Access layer

A miss here removes the page from consideration regardless of content quality. Audit these before touching structure.

| Requirement | Google (classic, AI Overviews, AI Mode, Gemini) | Bing-powered (ChatGPT search, Copilot) | Perplexity | Claude (Brave) and voice assistants |
|---|---|---|---|---|
| Index membership [G] | Google index; site enabled for generative AI features in Search Console; page snippet-eligible. | Bing index. Submit to Bing Webmaster Tools; use IndexNow for fast (re)indexing. [I] | Perplexity's own index plus partner indexes; PerplexityBot must reach the page. [I] | Brave index for Claude. Voice: Google or Bing index plus Knowledge Graph. [I] |
| Crawler access (robots.txt) [I] | Googlebot feeds Search and AI Overviews. Google-Extended governs Gemini apps and model training, not AI Overviews. | Bingbot for the index. OpenAI: OAI-SearchBot (search results), ChatGPT-User (live fetches), GPTBot (training). Block GPTBot alone if you want citation without training. | PerplexityBot (index) and Perplexity-User (live fetch). Several reports say Perplexity has not consistently honored robots.txt; verify in server logs. | ClaudeBot (index), Claude-SearchBot, Claude-User (live fetch). Voice: Googlebot / Bingbot. |
| JavaScript rendering [G] | Googlebot renders JS; follow JavaScript SEO best practices. Content blocked from rendering is invisible. | Assume no JS execution. Server-render facts, prices, specs, tables. [I] | Assume no JS execution. [I] | Assume no JS execution. [I] |
| Snippet eligibility [G] | nosnippet, data-nosnippet, or max-snippet:0 removes content from AI features. Use data-nosnippet selectively, never on the answer block. | Bing honors the same robots meta directives. [I] | Not documented; treat as equivalent. [P] | Not documented; treat as equivalent. [P] |
| Page experience and speed [G] | Core Web Vitals and mobile display are part of core systems. | Copilot reportedly weights sub-2-second loads. [I] | Not documented. [P] | Not documented; fast, simple HTML is the safe default. [P] |
| Semantic HTML [G] | Not required for ranking; recommended because it helps screen readers and browser agents read the accessibility tree. | Helps extraction: real `<table>`, `<th>`, `<ol>`, `<h2>`. [I] | Same. [I] | Same; voice assistants and agents read the accessibility tree. [P] |
| Canonical and duplicate control [G] | Reduce duplicates; canonical must point at the version you want cited. | Bing follows canonical. | Duplicate versions dilute which URL gets cited. [P] | Same. [P] |
| Sitemaps and change signals [G] | XML sitemap with accurate lastmod. | IndexNow pings on every publish or update. [I] | Sitemap discovery; publishing velocity reportedly helps. [S] | Sitemap discovery. [P] |
| Paywalled or gated content [G] | Use paywalled-content structured data (isAccessibleForFree, hasPart) so Google can index; content behind forms is not indexed. | Gated content is invisible; keep the most citable version open. [I] | Public PDFs reportedly favored; gated ones invisible. [S] | Invisible if gated. [P] |
| Byline and dates [G] | Visible byline date plus datePublished / dateModified in Article schema; do not fake dateModified. | Freshness is a strong ChatGPT signal; keep the visible date honest. [I] | Time-decay reranking reportedly rewards recent content. [I] | Same. [P] |
| llms.txt [G] | Ignored by Google Search. Harmless to keep. | OpenAI uses it for its own agent SDK docs; no evidence it affects ChatGPT search. [I] | Reported to be read occasionally; 97% of files receive zero traffic. [I] | Anthropic recommends it for agent-readable docs. A developer-docs decision, not a search decision. [I] |
| Local and commerce feeds [G] | Google Business Profile and Merchant Center feeds surface in AI responses. | Bing Places; Microsoft Merchant Center. [I] | Reads on-page Product/Offer data and third-party reviews. [P] | Same. [P] |
| Agent readiness (emerging) [G] | Browser agents read screenshots, DOM, and accessibility tree; Universal Commerce Protocol emerging. Lighthouse 13.3 added an "Agentic Browsing" audit (May 2026). | OpenAI Agentic Commerce Protocol for checkout. [I] | Not applicable yet. | Anthropic "Writing for Agents" guidance applies. |

## robots.txt starting point

```
# Search-time crawlers — allow if you want to be cited
User-agent: Googlebot
User-agent: Bingbot
User-agent: OAI-SearchBot
User-agent: ChatGPT-User
User-agent: PerplexityBot
User-agent: Perplexity-User
User-agent: ClaudeBot
User-agent: Claude-SearchBot
User-agent: Claude-User
Allow: /

# Training-only crawlers — a separate policy decision
# User-agent: GPTBot
# User-agent: Google-Extended
# User-agent: CCBot
# Disallow: /
```

Bot names change. Verify against each vendor's current crawler documentation before publishing, and confirm behavior in server logs rather than trusting the file alone.

## Access audit sequence

1. `site:` search on Google and Bing for the URL; search the brand and key terms on search.brave.com.
2. Fetch the page with JavaScript disabled; confirm the answer block, tables, prices, and specs are present.
3. Check robots.txt and any WAF/CDN bot rules against the list above.
4. Inspect robots meta and X-Robots-Tag for nosnippet, max-snippet, noindex.
5. Confirm canonical, sitemap inclusion, and lastmod accuracy.
6. Validate JSON-LD and confirm every value matches visible text.
7. Confirm Search Console shows the site included in generative AI features; confirm Bing Webmaster Tools verification and IndexNow key.
