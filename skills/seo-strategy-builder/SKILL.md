---
name: seo-strategy-builder
description: "Crawls your website with a real browser, researches live search results for your niche, and returns a prioritised list of new pages to create — each with a target keyword, a demand estimate backed by evidence, and the reason you can rank. Use when the user asks for an SEO strategy, content gap analysis, keyword research, 'what pages should I write', or how to get organic traffic."
---

# SEO Strategy Builder

### At a glance

**Who it's for** — Founders and operators who need organic search traffic but have no SEO budget, no agency, and no paid keyword tool.

**What it does for you** — Reads every page you already have, studies what actually ranks for the searches your buyers make, and hands back a ranked build list of pages worth creating: target keyword, demand evidence, ranking rationale, and a one-paragraph brief per page.

**When to use it** — Before you write blog posts or landing pages for search. Also when traffic has stalled and you don't know what to write next.

**Where it comes from** — Adapted from a solo-founder practitioner workflow that pairs two free MCP servers (a browser and a live search API), hardened with an evidence rule for demand estimates.

**How to use it** — Give it your site URL and your niche in a sentence. It checks the two tools are connected, crawls, researches, and writes the plan to `seo/`.

## Overview

Two tools do the work:

| Tool | What it gives Claude | Cost |
|---|---|---|
| **Playwright MCP** | A real browser: crawls your site, renders JavaScript pages, saves each page as markdown | Free, runs locally |
| **SerpApi MCP** | Live search results: organic rankings, "People also ask", related searches, autocomplete, Google Trends | Free tier, a few hundred searches a month |

Claude decides how to use them. This skill sets the order, the budget, and the evidence standard for the output.

**The honesty rule:** search APIs return rankings, not search volume. Never print a monthly-volume number you did not get from a real source. Demand is graded **High / Medium / Low** from the signals in Step 4, and the evidence is written next to the grade. If the operator supplies real numbers (Search Console export, Keyword Planner, a paid tool's CSV), use theirs and say so.

## When to Use
- "Build me an SEO strategy for {site}"
- "What pages should I create to get search traffic?"
- "Find content gaps between me and {competitor}"
- "Keyword research for {niche}"

Not for: technical audits (crawl errors, Core Web Vitals, schema). This skill is about **which pages to create**.

## Inputs

Ask for anything missing, in one message:

1. **Site URL**
2. **Niche in one sentence** — who you serve and what you sell
3. **Market** — country and language (sets SerpApi `location`, `gl`, `hl`)
4. **Known competitors** (optional — Step 3 finds them anyway)
5. **Real volume data** (optional — Search Console export, keyword-tool CSV)

If an Asset Foundation exists (see the `asset-foundation-builder` skill), read it first. Its **jargon (use vs avoid)**, **pains**, **false beliefs**, and **recognition quotes** are the best seed keywords you will get: they are the words buyers actually type.

## Step 0 — Check the tools

Check which MCP tools you have. MCP tools are often deferred (listed by name only), so search for and load `playwright` and `serpapi` tools before calling one missing. If either is genuinely absent, give the operator the command to run in their terminal, then stop until they restart Claude Code:

```bash
# Browser
claude mcp add playwright npx @playwright/mcp@latest

# Live search data (free key at serpapi.com → dashboard)
claude mcp add --transport http serpapi https://mcp.serpapi.com/mcp \
  --header "Authorization: Bearer YOUR_SERPAPI_API_KEY"
```

Package names drift. If an install fails, check the official Playwright MCP and SerpApi MCP READMEs for the current command.

**Fallbacks**, so the skill still runs:
- No Playwright: fetch `sitemap.xml` and pages with your web-fetch tool. JavaScript-rendered pages may come back thin, so say so in the report.
- No SerpApi MCP: use any installed SerpApi skill, or, if `SERPAPI_API_KEY` is set, call `https://serpapi.com/search.json?engine=…&q=…&api_key=$SERPAPI_API_KEY` with curl.
- No search data at all: offer a **crawl-only run** (Steps 0–1 plus the on-page gaps you noticed), and say clearly that no build list comes without live results. A strategy without them is guessing.

## Step 1 — Crawl your site

Goal: know exactly what exists, so you never recommend a page the operator already has.

1. Read `robots.txt` and respect it. If there is none (404), crawling is allowed; still go one page at a time.
2. Get the URL list from `sitemap.xml` (and nested sitemaps). With no sitemap, follow internal links from the homepage, breadth-first.
3. **Cap at 100 pages** unless the operator asks for more. On a large blog, take every non-post page plus the 50 most recent posts.
4. **Off-domain content counts.** If the site links to the operator's own blog, newsletter, or docs on another domain, crawl those too (same cap). A topic covered there is a page they already have. Note which domain it lives on, since content off the main domain builds that domain's rankings, not the site's.
5. For each page, `browser_navigate`, then pull the content with `browser_evaluate`. `browser_snapshot` returns an accessibility tree without meta tags, so it is a fallback only. A function like this returns what you need:

```js
() => ({
  title: document.title,
  h1: document.querySelector('h1')?.innerText.trim() ?? '',
  meta_description: document.querySelector('meta[name="description"]')?.content ?? '',
  canonical: document.querySelector('link[rel="canonical"]')?.href ?? '',
  text: document.body.innerText,
  links: [...document.querySelectorAll('a[href]')].map(a => a.href),
})
```

6. Save clean markdown to `seo/site/{slug}.md`, where slug is the URL path with `/` as `-`, and `home` for the root. Start each file with a header:

```markdown
---
url: https://example.com/pricing
title: <title tag>
h1: <h1>
meta_description: <meta description>
words: <approx word count>
---
```

7. Write `seo/site-map.csv`: `url, title, h1, words, topic, inferred_target_keyword`. Keep any raw captures in `seo/raw/`. Playwright may also write its own files to `.playwright-mcp/`; tell the operator so they can delete them or add the folder to `.gitignore`.

Then summarise in five lines: what the site is about, which topics it already covers, which pages look thin (under ~300 words) or duplicated, and on-page gaps you saw on the way: missing meta descriptions, missing canonicals, tools or offers mentioned but with no page of their own.

## Step 2 — Seed keywords

Build 15–30 seed queries from four sources:

| Source | What to pull |
|---|---|
| Asset Foundation (if present) | Buyer jargon, pain phrases, false beliefs said as questions |
| Your own site | The topic of each money page (pricing, product, service pages) |
| Problem language | "how to {job}", "{problem} fix", "why does {symptom}" |
| Comparison language | "{category} for {segment}", "best {category}", "{competitor} alternative" |

Write seeds in the buyer's words, not yours. A buyer types the problem, not your product category.

## Step 3 — Research live results

**Budget searches.** Free tiers run out fast. Plan the calls before making them and stay under ~60 for a full run. Log every call in `seo/serp-log.csv` (`query, engine, date`) so a rerun doesn't pay twice.

Per seed, in this order:

1. **`google_autocomplete`** — expands one seed into real long-tail queries. Cheap breadth; do it first.
2. **`google`** (full results, not `google_light`, when you need these blocks) — record:
   - top 10 organic: URL, domain, title, content type (guide, listicle, tool, product page, forum thread, video)
   - `related_questions` ("People also ask")
   - `related_searches`
   - whether ads appear (a commercial-intent signal)
3. **`google_trends`** on the 10 most promising expanded queries — relative interest and direction (rising, flat, falling).

Set `location`, `gl`, `hl` from the operator's market on every call. Results from the wrong country are worthless.

**Competitors:** domains that show up in the top 10 across three or more seeds are your real search competitors, whoever the operator thinks they compete with. List them. For the top 3, fetch their sitemaps (cheap, no search credits) and note which topics they have pages for that you don't.

Save raw findings to `seo/keyword-research.csv`:
`query, source_seed, intent, demand_grade, demand_evidence, top_result_types, weak_spots_in_top10, competitor_coverage, you_have_page`

## Step 4 — Grade each opportunity

**Intent**, from what ranks: guides = informational, product and category pages = commercial, "X vs Y" and lists = comparison, a brand's own pages = navigational (skip these).

**Demand (High / Medium / Low)**, from evidence you saw:

| Signal | Points to higher demand |
|---|---|
| Autocomplete suggests it from a short prefix | Many people type it |
| Ads on the results page | Someone pays for this click |
| A "People also ask" block, a video carousel, many SERP features | Google has invested in the query |
| Google Trends interest that is sustained or rising | Lasting, not a one-off spike |
| Several competitors built dedicated pages | They saw traffic worth chasing |

High needs three or more signals; Low is one or none. Write the signals down in `demand_evidence`. That column is what makes the grade believable.

**Winnability** — read the top 10 as an operator would:
- **Winnable:** forum threads, Q&A answers, thin or outdated pages (check dates), results that answer a different question than was asked, small sites
- **Hard:** ten strong, current, on-intent pages from large established domains
- **Mismatch you can exploit:** the query wants a tool, template, or calculator, but the results are articles

**Fit** — would someone searching this become a customer, or at least a subscriber? A high-demand query no buyer types is a vanity target.

## Step 5 — The build list

Drop anything the site already covers well (check `site-map.csv`). Where an existing page targets the query but is thin, recommend **improving it** rather than creating a new page.

Rank by **fit first, then winnability, then demand**. A Medium-demand query you can win with buyers behind it beats a High-demand query you can't rank for.

Write `seo/opportunities.md`:

```markdown
# SEO build list — {site} — {date}

## Summary
- Pages crawled: N · Searches used: N · Competitors found: {domains}
- The 3 pages to build first, and why

## Build list

### 1. {Working title}
- **Target keyword:** {query}  · **Supporting:** {3–5 related queries / PAA questions}
- **Intent:** {informational | commercial | comparison}
- **Demand:** {High/Med/Low} — {evidence}
- **Why you can rank:** {specific weakness in the current top 10}
- **Why it's worth it:** {how this searcher becomes a lead}
- **Format:** {guide | comparison | tool | template | landing page} · ~{length matched to what ranks}
- **Brief:** one paragraph: the question it answers, the angle the current results miss, the proof you can bring
- **Links:** to {existing money page} · from {existing pages that should link here}

## Improve, don't create
{existing pages + what to fix}

## Skipped, and why
{tempting queries you rejected: unwinnable, wrong intent, no fit}
```

Aim for **10–20 pages**. More than that is a backlog nobody ships.

## Step 6 — Hand-off

Tell the operator, in under ten lines: the top 3 pages, the searches used and how many remain on the free tier, and what to do next:

- Commercial pages → the `landing-page-builder` skill, with the brief as input
- Informational guides → the `content-engine` skill
- Before publishing anything → the `unleash-stop-slop` skill
- Rerun this skill in ~90 days. Rankings move, and `serp-log.csv` shows what changed.

## Rules

- **No invented numbers.** Demand is a graded estimate with evidence, unless the operator gave you real volume data.
- **Buyer language over industry language.** If buyers don't type it, don't target it.
- **One page, one primary keyword.** Two pages chasing the same query compete with each other.
- **Respect robots.txt and rate limits.** Crawl politely: one page at a time, no hammering.
- **The operator's market only.** Every search runs with their location and language.
