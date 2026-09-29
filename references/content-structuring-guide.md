# Content structuring guide — eleven steps

Follow in order for every new page and every refresh. These rules satisfy Google's documented preferences (headings, sections, readable paragraphs, indexable HTML) [G], the passage-extraction patterns observed across AI Overviews, ChatGPT, and Perplexity [I], and the single-passage read-aloud constraint of voice assistants [P].

Contents: 1 Query and answer sentence · 2 Page anatomy · 3 Paragraphs · 4 Headings · 5 Tables · 6 Lists · 7 FAQ · 8 Voice layer · 9 Authority · 10 Technical wrap · 11 Pre-publish checklist

---

## Step 1 — Define the target query and write the answer sentence first

Work backward. Before drafting, write down the one question this page exists to answer and the one sentence you want an engine to quote. Everything else supports that sentence.

1. State the primary query in the words a person would type or say.
2. List three to five fan-out sub-questions the query implies. Google documents fan-out [G]; these become your H2s.
3. Write the answer sentence: 20–35 words, plain language, no pronoun at the start, names the subject explicitly.
4. Write the answer block: the answer sentence plus two or three supporting sentences, 40–75 words total. This is the passage you are optimizing.

Why 40–75 words: that range maps to the average length of passages quoted by ChatGPT, Perplexity, and AI Overviews in 2025–2026 citation studies [I]. The older 40–60 word featured-snippet target sits inside it.

## Step 2 — Page anatomy: put the answer in the top third

55% of cited passages appear in the first 30% of the source page [I]. Google states that AI features extract the relevant piece from a page and that structured sections help readers [G].

| Order | Element | Rules |
|---|---|---|
| 1 | Title tag and H1 | One H1 containing the primary query's key entity. Title tag under ~60 characters; H1 may be longer. |
| 2 | Byline block | Author name linked to a bio page; credentials in one clause; visible "Published" and "Last updated" dates matching Article schema. |
| 3 | Answer block | The 40–75 word passage from Step 1, immediately after the H1 or after one short framing sentence. No image, ad, or table of contents before it. |
| 4 | Key facts strip (optional) | Two to four sourced numbers in short sentences. Each is a candidate citation on its own. |
| 5 | Table of contents | Jump links to every H2. Exposes the H2 set to crawlers early. |
| 6 | Body sections | One H2 per fan-out sub-question, each opening with its own answer-first paragraph. |
| 7 | Comparison or data table | Where two or more entities are compared. Rules in Step 5. |
| 8 | FAQ | Four to eight visible questions not already answered by an H2. Rules in Step 7. |
| 9 | Author bio and sources | Two to three sentence bio with real credentials; numbered sources with links and access dates. |

## Step 3 — Paragraph rules

1. **One idea per paragraph.** If a paragraph contains "also" or "in addition" introducing a second point, split it.
2. **Lead with the claim, then the evidence.** The first sentence should survive being quoted alone.
3. **Make every answer paragraph self-contained.** Name the subject; never open with This, It, They, or These. An engine that lifts the paragraph must not need the previous one to resolve a pronoun.
4. **Name entities explicitly and consistently.** Full name on first mention in each section; one spelling of every product, person, and organization across the page. Entity density is reported to correlate with AI Overview selection [I].
5. **Attach number, unit, source, and date to every statistic.** Pattern: `[metric] [value] [unit] ([source], [month year])`. Unsourced numbers are the first thing to cut.
6. **Keep answer passages at 40–75 words; supporting paragraphs under ~110 words.** Vary sentence length inside the paragraph.
7. **Write in the register the engine answers in.** ChatGPT's content-answer-fit finding [I] means plain, direct, well-organized prose outperforms marketing voice. Google's guide says the same for humans [G].
8. **Avoid keyword repetition.** Google states AI systems understand synonyms and variant-chasing is unnecessary [G]; the Princeton GEO study found keyword stuffing reduced visibility by about 10% [I].

**Before:** "It's a huge shift. Marketers everywhere are realizing that things have changed and that they need to adapt their strategies to this new landscape, which is why so many are talking about GEO these days."

**After:** "Generative engine optimization (GEO) is the practice of structuring content so that LLM-based answer engines such as Perplexity and ChatGPT search retrieve and cite it. It differs from traditional SEO in one respect: the unit of selection is the passage, not the page. Ahrefs found only about 38% of Google AI Overview citations rank in the organic top 10 (May 2026)."

## Step 4 — Heading rules

1. One H1 per page. Do not reuse H1 styling for section titles.
2. Phrase H2s as fan-out sub-questions or as noun phrases a person would search ("How Perplexity selects sources," not "Under the hood").
3. Use H3s only for sub-questions of the H2 above them. Never skip a level.
4. Every heading must make sense read alone in a list. The table of contents is the test.
5. The first paragraph under any heading answers that heading directly, answer-first.
6. Keep headings under ~70 characters so voice assistants and mobile SERPs do not truncate them.
7. Do not put the primary query into more than two headings.

## Step 5 — Data and comparison table rules

Tables map directly onto structured data an LLM can quote or reformat [I], and Google shows table content in snippets [G]. Voice assistants cannot read a table aloud, so every table needs a prose summary beside it.

1. **Use a real HTML `<table>` with `<thead>`, `<th>`, `<tbody>`.** Never an image, screenshot, CSS grid of divs, or PDF-only table.
2. **One entity per row, one attribute per column.** No merged cells; no nested tables.
3. **Units and dates in the header, not the cells.** "Citations per answer (2026)" as header; "21.9" as cell. Numeric cells contain only the number.
4. **Limit to seven columns.** Split wider comparisons into two tables sharing the first column.
5. **Add a `<caption>` or bold lead-in** stating what the table compares and the date of the data.
6. **Add a source line directly under the table** naming each source and month; link it.
7. **Write a one- to two-sentence prose summary above the table** stating the single most important comparison. That is the passage voice assistants and LLMs quote; the table is the evidence.
8. **Use the same entity names in the table as in the body text.**
9. **Sort rows deliberately** and say so in the caption.
10. **Keep the table server-rendered** inside the main content container.

## Step 6 — List rules

1. Numbered lists (`<ol>`) for anything sequential; bullets (`<ul>`) only for unordered sets.
2. Each step starts with a verb and is self-contained: no "then do the same as above."
3. Keep process lists to ten steps or fewer; split longer procedures under H3s.
4. Introduce every list with one sentence stating what the list accomplishes; that sentence is often what gets quoted.
5. HowTo rich results are retired, so the visible `<ol>` is the extraction target. Do not depend on HowTo markup.

## Step 7 — FAQ block rules

1. Include only questions the page has not already answered under an H2.
2. Write each question as a person would speak it, as an H3 or `<dt>`.
3. Answer in the first sentence, under 50 words per answer, self-contained, with a sourced figure where one exists.
4. Keep the FAQ visible in the HTML; never behind JavaScript accordions that do not render server-side.
5. FAQPage markup is optional after May 7, 2026. Keep it if present; add it only for Bing, voice indexers, or your own RAG systems, not for a Google SERP effect.

## Step 8 — Voice assistant layer

Working assumption: voice surfaces read one short passage aloud and increasingly route through LLMs (Gemini, Siri with Apple Intelligence and ChatGPT, Alexa+) [P]. The answer block from Step 1 already serves them. Add:

1. A spoken-register version of the answer sentence: under 30 words, no parentheses, no abbreviations that sound wrong aloud, numbers written to read naturally.
2. Speakable markup on that sentence and one summary paragraph, if eligible (news publishers, US English, beta per Google).
3. A prose summary above every table and list, because those elements are not spoken.
4. LocalBusiness and Organization schema aligned field-for-field with Google Business Profile and Bing Places.

## Step 9 — Authority layer at publish

1. Byline with a real named author, one-clause credential, and a link to a ProfilePage with Person schema.
2. Numbered sources list with links; prefer primary sources over articles about them.
3. At least one first-hand element Google would call non-commodity: original data, a tested result, a documented decision, a screenshot of your own process.
4. Honest dateModified. Update only on substantive change; refresh competitive pages at least quarterly, monthly where ChatGPT citation matters.
5. Organization schema with sameAs to Wikipedia or Wikidata, LinkedIn, and major profiles.

## Step 10 — Technical wrap before publish

1. JSON-LD in `<head>` matching visible content exactly [G].
2. Server-rendered HTML for the answer block, tables, prices, specs; verify with JavaScript disabled.
3. No nosnippet or max-snippet limits on the article body; data-nosnippet only on legal boilerplate.
4. Descriptive alt text on every image; VideoObject markup and a YouTube copy for any video.
5. Canonical set; page in the XML sitemap with correct lastmod; IndexNow ping on publish.
6. robots.txt allows the search-time bots listed in `technical-requirements.md`.
7. Page passes Core Web Vitals; sub-2-second load on mobile.

## Step 11 — Pre-publish QA checklist

Report every line as pass / fail with the fix and the layer it belongs to.

| Check | Pass condition |
|---|---|
| Answer block position | 40–75 words, within the first ~300 words, before any table of contents or image. |
| Answer sentence stands alone | Names the subject; no leading pronoun; under 35 words. |
| Heading hierarchy | One H1; H2s read as sub-questions; no skipped levels; every heading meaningful alone. |
| Paragraphs | One idea each; none over ~110 words; every statistic has value, unit, source, date. |
| Tables | Real HTML; units in headers; caption; source line; prose summary above; ≤7 columns; no merged cells. |
| Lists | Sequential steps in `<ol>`; verb-first; ≤10 steps; one-sentence intro. |
| FAQ | 4–8 visible questions; answer in first sentence; ≤50 words each. |
| Author and dates | Named author with credential and bio link; visible published and updated dates matching schema. |
| Sources | Numbered, linked, primary where possible; no unsourced claims of prevention, elimination, or guarantee. |
| Non-commodity element | At least one first-hand data point, test, or documented decision. |
| Schema | Article + Person + Organization present and validated; Product / LocalBusiness / Video where relevant; matches visible text. |
| Rendering | Answer block and tables visible with JavaScript disabled. |
| Crawler access | robots.txt verified against the bot list; no nosnippet on body. |
| Entity consistency | One spelling per product, person, and organization across page, table, and schema. |
| Third-party plan | At least one authentic distribution action queued (LinkedIn article, community post, YouTube version, industry publication pitch). |
