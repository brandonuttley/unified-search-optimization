# Structured data and schema matrix (post-May 2026)

**Google's stated position [G]:** structured data isn't required for generative AI search and there is no special schema.org markup to add; keep using it for rich-result eligibility. All markup must match visible page content.

**Counter-evidence to vendor claims [I]:** a December 2024 Search Atlas study reportedly found no correlation between schema coverage and AI citation rates. Several vendors claim FAQPage "strongly boosts" AI citations without published data.

**Safe reading:** implement schema for rich results, entity clarity, and machine parsing by Bing and voice indexers. Do not expect it to move LLM citation on its own.

| Schema type | Google rich-result status (Sept 2026) | AI Overviews / AI Mode | Other LLM engines | Voice | Recommendation |
|---|---|---|---|---|---|
| Article / NewsArticle / BlogPosting | Supported (headline, image, author, dates). [G] | Not required; supplies author and date entities Google already reads from the page. [G] | Bing parses; reported as most important type for content sites after FAQ removal. [I] | Indirect. [P] | Implement on every content page with author (Person), datePublished, dateModified, publisher (Organization). |
| Organization (sameAs, logo, contact) | Supported (knowledge-panel inputs). [G] | Entity identity for brand queries. [P] | Entity disambiguation across engines. [P] | Brand answers. [P] | Implement site-wide once; keep sameAs links to Wikipedia, Wikidata, LinkedIn, Crunchbase current. |
| Person + ProfilePage (authors) | ProfilePage supported. [G] | E-E-A-T entity; author expertise heavily weighted. [G] | Author credentials reportedly influence citation. [I] | Indirect. | Implement for every named author: jobTitle, affiliation, sameAs to LinkedIn and publications. |
| Product / Offer / Review / AggregateRating | Supported (merchant listings, product and review snippets). [G] | Commerce answers pull from Merchant Center plus on-page product data. [G] | Comparison answers extract price, specs, ratings. [I] | Product questions. | Implement for every product; keep price and availability server-rendered and identical to markup. |
| LocalBusiness | Supported. [G] | Local answers pull Business Profile plus page data. [G] | "Best X near me" answers reportedly read it. [I] | Core for local voice queries. [P] | Implement and align every field with Google Business Profile and Bing Places. |
| BreadcrumbList | Supported. [G] | Site-structure clarity. | Indirect. | None. | Implement site-wide. |
| FAQPage | Rich results ended May 7, 2026. Markup still valid; leaving it in place causes no problems. [G] | Not required; no special treatment documented. [G] | Bing, Perplexity, and RAG crawlers reportedly parse Q&A markup; effect on citation unconfirmed. [I] | Voice systems reportedly read Answer.text as a script; unconfirmed. [I] | Keep visible FAQ content because it answers real questions. Keep existing markup. Do not add new FAQ markup expecting a Google SERP effect. |
| HowTo | Retired on all Google surfaces since Sept 2023. [G] | None. | Some parsers may read step structure; unconfirmed. [I] | None. | Optional. A visible `<ol>` with verb-first steps is what gets extracted. |
| QAPage / DiscussionForumPosting | Supported for user-generated Q&A and forums. [G] | Forum and discussion content heavily cited by AI Overviews. [I] | Reddit-style content heavily cited by Perplexity. [I] | Indirect. | Implement if hosting a community or Q&A section. |
| Speakable | Supported; limited to news publishers, US English, beta. [G] | Indirect. | None documented. | Marks 2–3 passages suitable to read aloud on Google Assistant. [G] | Implement if eligible; mark the answer block and one summary paragraph only. |
| VideoObject | Supported; key moments via hasPart Clip. [G] | Google recommends video; AI features surface it. [G] | YouTube among most-cited domains. [I] | None. | Implement for every embedded video; host on YouTube in parallel. |
| Dataset | Supported (Dataset Search). [G] | Original data is "non-commodity" content. [G] | Original statistics among the strongest reported citation drivers. [S] | None. | Implement for original research; publish the data table on-page, not only in PDF. |
| WebPage with about / mentions | No rich result. | Entity linking; unproven. [P] | Unproven. [P] | None. | Optional. Fine if generated automatically; do not hand-build. |
| Paywalled content (isAccessibleForFree, hasPart) | Supported and required for paywalled pages to index correctly. [G] | Needed for eligibility. | Other engines cannot read paywalled text regardless. | None. | Implement wherever content sits behind a paywall. |

## Minimum viable JSON-LD for a content page

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Exact visible H1",
  "datePublished": "2026-09-01",
  "dateModified": "2026-09-29",
  "author": {
    "@type": "Person",
    "name": "Author Name",
    "jobTitle": "Role, Organization",
    "url": "https://example.com/authors/author-name",
    "sameAs": ["https://www.linkedin.com/in/author-name"]
  },
  "publisher": {
    "@type": "Organization",
    "name": "Organization Name",
    "url": "https://example.com",
    "logo": { "@type": "ImageObject", "url": "https://example.com/logo.png" },
    "sameAs": ["https://en.wikipedia.org/wiki/Organization_Name", "https://www.linkedin.com/company/organization"]
  },
  "mainEntityOfPage": "https://example.com/page-url"
}
```

Rules: every value must appear on the visible page; dateModified changes only with substantive edits; validate with a general structured-data validator rather than a rich-result test tied to a retired feature.
