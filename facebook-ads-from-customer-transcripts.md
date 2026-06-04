---
name: Facebook Ads From Customer Transcripts
description: Turn a set of customer interview transcripts into a battery of Facebook / Meta ad variants (hooks, bodies, CTAs) that use the customer's own language. For B2C and SMB-B2B where Meta ads are a viable channel.
type: skill
---

# Facebook Ads From Customer Transcripts

### At a glance

**Who it's for** — B2C and SMB-B2B founders running (or about to run) Meta / Facebook / Instagram ads who have a stack of customer interviews or sales-call transcripts.

**What it does for you** — Mines your customers' own words and produces a battery of ad variants — 10 hooks, 5 bodies, 5 CTAs, a creative brief, and a "do not use" list — written in your customer's language, not your marketing team's.

**When to use it** — When you're launching or refreshing a Meta ad campaign and want copy grounded in real customer language.

**Where it comes from** — Direct-response copy principles applied to paid social, across Unleash ventures.

**How to use it** — Drop in 5–20 transcripts plus your offer, audience, and landing page; it returns a single document of ready-to-test ad copy.

## When to Run
- You're launching a Meta / Facebook / Instagram ad campaign.
- You've done 5+ customer interviews or have a stack of sales call transcripts.
- You want ad copy that sounds like your customer, not like your marketing team.
- Triggered by: "/fb-ads", "turn these interviews into Facebook ads", "ad copy from transcripts".

## Inputs You Need
1. **5–20 customer interview transcripts, sales call transcripts, or written testimonials** — the rawer and longer, the better.
2. **Product / offer one-liner** — what you're advertising.
3. **Target audience definition** — who sees the ad (demographics, interests, behaviours).
4. **Landing page URL or headline** — so ad copy matches what the click leads to.
5. **Desired conversion event** — lead form, purchase, trial signup, book-a-call.

## Output You Produce
A single document with:

1. **10 hooks** — the first 3–5 words of an ad that stops the scroll. Pulled from real customer quotes where possible.
2. **5 ad bodies** — each 40–90 words, written in the customer's voice, ending in a clear CTA.
3. **5 CTA variants** — tested directly against the conversion event.
4. **A "do not use" list** — words or phrases from the transcripts that sound fine in a call but die in a feed (industry jargon, insider language).
5. **Creative direction brief** — what the visuals should show, based on the context the customers describe.

## Output Format (LOCKED — do not deviate)

**Output the playbook as plain text with section headers, NOT markdown headings.**

- `{LANGUAGE}` = `DE` → use `TEIL 1:`, `TEIL 2:`, `TEIL 3:` …
- `{LANGUAGE}` = `EN` → use `PART 1:`, `PART 2:`, `PART 3:` …

**Do NOT use** `## TEIL 1:` / `## PART 1:` / `### 1.1` markdown forms. Reason: operators paste these playbooks into Notion, Google Docs, Brevo, Meta Ads Manager — environments where markdown headings render inconsistently or not at all. Plain section labels (`TEIL 1: Setup`, `PART 1: Setup`) survive every paste target.

Sub-sections use number-dot notation in plain text:

```
TEIL 1: Setup

1.1 Business Manager
- bullet
- bullet

1.2 Pixel
- bullet
```

Not:

```
## TEIL 1: Setup        ← WRONG (markdown heading)
### 1.1 Business Manager ← WRONG
```

This is a one-line check before you deliver: `grep -c "^## TEIL\\|^## PART\\|^### [0-9]" output.md` should return `0`.

## Step-by-Step

### Step 1 — Mine the transcripts
Pull these four categories of quotes:

- **Problem statements** — how the customer describes the pain in their own words. Extract 20–30.
- **Failed attempts** — what they tried before and why it didn't work. Extract 10–15.
- **Outcome language** — how they describe life after the problem is solved. Extract 10–15.
- **Surprise moments** — where they realised your product was the answer. Extract 5–10.

### Step 2 — Build hooks from problem statements
Rules for hooks:
- 3–7 words.
- Specific number or concrete noun.
- First-person when possible ("I can't get...", "My team keeps...").
- If a hook could belong to any product in the category, rewrite it.

### Step 3 — Build bodies
Each body follows this structure:
1. The problem (customer's words).
2. The failed attempt (what else they tried).
3. The pivot (what actually worked).
4. The CTA (concrete next step, matched to the conversion event).

Write 5. Vary the opening — some start with the pain, some with a question, some with a number.

### Step 4 — Test CTA variants
Five variants:
- Direct command ("Book a demo.")
- Benefit-led ("See it in action.")
- Soft invite ("See if it fits.")
- Urgency ("This month only.")
- Specific ("Free 15-min call with the founder.")

### Step 5 — Build the "do not use" list
From the transcripts, identify words or phrases that:
- Are industry jargon that only insiders understand.
- Would trigger Meta's policy filters (health claims, financial promises).
- Sound natural in a conversation but awkward in text.

### Step 6 — Creative brief
From the context in the transcripts, describe:
- The setting (office, kitchen, site, car).
- The emotional state (frustrated, relieved, sceptical, confident).
- The object or screen the customer is looking at.

## Quality Bar
- A scroller who doesn't know you can understand the ad in 3 seconds.
- Every hook and body traces back to a specific transcript line.
- Nothing is invented. If you can't source a line, cut it.
- CTAs match the landing page exactly.

## Common Failure Modes
- Hooks are abstract ("Unlock your potential"). Rewrite until they're concrete.
- Body sounds like your landing page. Rewrite in first-person using transcript language.
- No "do not use" list. You'll ship jargon by accident.
- Creative brief skipped. Stock images kill ad performance.

## Worked example — illustrative only

Below is what hooks + body + CTAs look like for a fictional `{Your Venture}` running ads for a boutique creative agency targeting Series-A SaaS founders. Read for the structural moves — your copy must come from your own customer transcripts.

### Three hook variants (test all three, kill the loser)

```
Hook A — problem-statement, mirrors customer language:
"My deck looked like a pitch for the wrong company. We
weren't a feature-list anymore. We were a category."

Hook B — failure-of-alternatives:
"We hired three freelance designers before we figured out
the issue wasn't design. It was that nobody was asking why."

Hook C — moment-of-recognition:
"The investor who passed told us our brand made us look
like a feature, not a platform. That feedback cost us a
$4M round."
```

### Body (one variant, ~80 words)

```
After our Series A pre-empted by 6 months, we needed a brand
that matched where the company was going — not where it was
last year. {Your Venture} ran 6 weeks of strategy interviews
before they touched a Figma file. The new identity launched
two weeks before our board offsite. Same week, two outbound
prospects mentioned the new positioning unprompted on first
calls. The first time that's ever happened to us.

— {Founder name}, {Company}, Series A SaaS
```

### CTA variants

```
CTA A (low commitment):  "See the 6-week process"
CTA B (specific outcome): "Book your brand strategy call"
CTA C (peer signal):     "Join 12 Series-A founders we've worked with this year"
```

### "Do not use" list (Step 5 output for this niche)

- Generic creative-agency words: *"vibrant"*, *"award-winning"*, *"world-class"* — your customers never used these.
- Process-y language: *"our proprietary methodology"*, *"design thinking workshops"* — the customer cares about outcomes, not method names.
- Anything that could appear in a stock-photo agency ad. If it could be the same ad with a different logo, kill it.

### What this example shows you (the structural moves)

- **Each hook is verbatim or near-verbatim from a customer call.** Hook A and C are direct quotes; Hook B is a tight paraphrase. None invent emotion that wasn't said.
- **The body is a single customer story with a specific moment of recognition** — concrete, time-bound, falsifiable.
- **CTAs ladder commitment**: low (browse) → specific (call) → peer signal (join). Test all three; the winning CTA pairs with the winning hook.
- **The "do not use" list is as important as the ad copy.** Most failed Meta ads die on industry-cliché vocabulary the customer never used.

If your hooks read like direct quotes from your transcripts and your CTAs ladder commitment, you're done. If they read like generic agency-marketing, go back to the transcripts.

## Hand-off — what to consume from upstream
- **Hook variants** ← Asset Foundation Row 10 (Bodacious Claim) + Rows 3–4 (pain hooks)
- **Body copy** ← Row 2 (Desires) + Row 12 (Auxiliary, lifestyle payoff)
- **CTA variants** ← Row 9 (Vehicle, named simply)
- **Creative brief / scene direction** ← Row 1 (Position — setting, situation, who's nearby)
- **"Do not use" list** ← inverse of Row 1's vocabulary (jargon insiders use that scrollers won't recognise in 3 seconds)

Run `asset-foundation-builder.md` first.

---

## Final Quality Check (run before delivering output)

- [ ] **Language consistency** — every cell/section uses the operator's specified `{LANGUAGE}` (no mixing EN+DE in one artefact unless explicitly asked).
- [ ] **Umlaut integrity (German output only)** — verify zero ASCII-substitutions of umlauts. Run:
      ```
      grep -c "ä\|ö\|ü\|ß" output.md          # should be > 0 for any non-trivial DE output
      grep -cE "(fuer|ueber|muessen|koennen|haette|wuerde|aendern|groesse|Geschaefts|Auftraege|Beschaeftigte)" output.md   # should be 0
      ```
      If any positive matches in the second grep: do a sed pass converting `ae→ä`, `oe→ö`, `ue→ü`, `sz→ß` for the affected words. Common LLM-tooling artefact — easy to catch, easy to fix, but kills credibility if shipped.
- [ ] **Voice consistency** — direct quotes are tagged with source (transcript / forum / podcast / operator-supplied). Zero invented quotes. If a recognition quote slot is empty, mark `[needs transcript validation]` rather than fabricating.
- [ ] **Ansprache lock (DE)** — `Du` or `Sie` chosen explicitly per the operator's `{DU_OR_SIE}` input and applied throughout. Mixed register kills credibility on a niche audience.
- [ ] **No GPT-language** — strip on sight: *leverage, synergize, unlock, streamline, delve, ecosystem, robust, holistic, cutting-edge, next-gen, disruptive*. DE: strip *skalieren, Stack, Pipeline, Funnel, Conversion-Rate-Optimierung* (Sales-Englisch — German operators recognise it instantly as outsider voice).
- [ ] **No fabricated stats** — every number has a source citation; if unverifiable, mark `[needs validation]`. Common to hallucinate "73% of X say Y" — never ship without a real source URL.
- [ ] **No venture-specific brand baked in** — output uses operator-supplied `{COMPANY}`, `{PRODUCT_NAME}`, `{PRIMARY_HEX}` etc. The skill itself is venture-agnostic; venture content is injected at runtime.
