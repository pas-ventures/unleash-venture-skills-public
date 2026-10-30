---
name: landing-page-builder
description: "Builds a high-converting two-page landing page plus progressive signup flow for a specific niche, with scene-first headlines, proof-only claims and pre-publish checks. Use when you need a niche-specific landing page, opt-in page or signup funnel fast."
---

# Landing Page Builder Skill

### At a glance

**Who it's for** — Founders who need a niche landing page to capture leads — built originally for B2B SaaS targeting German SMBs, but the structure adapts to any niche.

**What it does for you** — Produces a two-page setup — landing page plus a multi-step signup with progressive email capture — built on your customer's real pains and language.

**When to use it** — When you need the entry point of an inbound funnel: somewhere to send traffic that captures qualified leads.

**Where it comes from** — Direct-response landing-page structure, applied across Unleash ventures.

**How to use it** — Feed it your Asset Foundations and brand inputs (or an existing page to adapt); it generates the landing and signup pages ready to ship.


## Build Principles (read before Step 0)

These principles come from real-world battle-testing on conservative B2B audiences (industrial SMBs, owner-managed firms, skeptical buyers). They override any step below when the two conflict.

### A · What the page is for
1. **The page sells the conversation, not the product.** The only job of the page is to get a qualified person into a free first conversation. Product name, feature names and architecture stay out of the first impression.
2. **Problem first, solution last.** Enter the conversation already running in the prospect's head (Kennedy). Scene, consequences, proof, then the offer. Never lead with feature cards, a product demo or technology.
3. **One page, one audience, one offer.** One niche per page. Inside a page only the *role* changes, never the offer.

### B · Headline and first impression
4. **The headline is a scene from one role's working week.** Name a concrete system, a concrete event and a concrete person the reader knows. The reader should think: *"That exact thing happened here last month."* Generic claims ("only a few people really know how things work") fail this test.
5. **Every buying role gets its own headline.** Owner/MD, operations lead, sales lead and technical lead feel different frustrations. Switch the hero via a URL parameter (`?r=owner`, `?r=ops`, `?r=sales`, `?r=tech`) so each person you message directly lands on their own version.
6. **Curiosity, not explanation.** Pose a question about the reader's own business that they want answered. The answer comes in the conversation, not on the page.
7. **No product name, no tech, no "AI" in headline, sub-line or CTA.**
8. **Numbers must be about the reader's business, not the macro trend.** A national statistic is only useful when translated to a firm of the reader's size in the reader's industry. Industry figure + "for a company of your size that means …" (mark arithmetic as an estimate).

### C · Credibility
9. **Only claim what real proof carries.** "The best companies in your industry do X" is only allowed if you can show them. With one reference customer, name that one case. With none in this niche, say so and switch to a question ("What if you knew …?").
10. **Quotes only with a source, each quote once.** A quote in quotation marks comes from a real conversation. Never reuse the same "customer quote" across pages.
11. **No false precision.** No "in one minute", "the last ten percent", "check it in ten seconds" unless measured.
12. **Honesty as a style.** Say what is missing ("we don't have a reference in your industry yet") and who the offer is *not* for. It builds more trust than any promise.
13. **No pressure tactics that aren't true.** Scarcity, countdowns and "waiting costs you" only when real. Conservative buyers spot them instantly.

### D · The offer
14. **The free entry point reveals a problem.** The first conversation is a lead magnet in its own right: the reader learns something about their business they didn't know (Hormozi, *$100M Leads*). Never "book a demo" for cold traffic.
15. **The next step has a price and is small.** A short paid test with a fixed price that is credited if they continue. Big outcome, little effort, fast result (Hormozi value equation).
16. **Risk reversal only when contractually backed** and clearly defined.

### E · Language
17. **Choose the form of address for the audience**, even against the brand guideline (e.g. formal *Sie* for conservative German owners).
18. **Use the industry's own words**, no anglicisms or consultant vocabulary.
19. **No slop.** No dashes as punctuation, no three-item lists in sub-lines, no "not X, but Y", no sentence template repeated across roles.
20. **Answer the audience's first objections** in the FAQ, concretely and without invented commitments (e.g. works council, customer data, "it's all in our system already", budget).

### F · Before anyone sees it
21. **Three checks before showing a draft:** a slop check (the `unleash-stop-slop` skill), a target-group check per niche that plays every role, and a fact check against sources.
22. **No placeholder and no unconfirmed commitment on the page.** Open items go on the operator's open-points list, not on the page.

## Overview
Build high-converting niche landing pages for B2B SaaS targeting German SMBs. Two-page setup: Landing Page + Signup Page with progressive email capture.

## Architecture
- **Page 1**: `{niche}.html` — Landing page (hook, pain, features, social proof, exit popup)
- **Page 2**: `{niche}-signup.html` — Multi-step signup with progressive data capture (email first)

## Step-by-Step Procedure

### Step 0: Inputs & CI Setup (ask the operator before drafting)

**0a. Existing-niche template (preferred starting point)**

If you've already shipped a landing page for an adjacent niche in this venture, **start from that file** — don't generate from scratch. The proven path:

1. `cp existing-niche.html → {new-niche}.html`
2. Bulk-replace niche terms via `sed` (term mappings the operator gives you upfront)
3. Make 4-5 targeted Edits for:
   - Hero stat / urgency badge / H1
   - Day-in-life narrative paragraph
   - Pull-quote (operator verbatim if available)
   - Stats bar (4 numbers from the new foundation)
   - Feature card titles (pain-named)

This saves 30+ min, guarantees design fidelity, preserves the venture's CI without rebuilding it. Generative-from-scratch is the fallback only when no adjacent template exists.

**0b. CI inputs (mandatory — ask the operator, do not invent)**

Before writing a single line of HTML, collect:

| Variable | What to ask | Example value |
|---|---|---|
| `{PRIMARY_HEX}` | Primary brand color — main CTA + accents | `#5A9E72` (your brand-primary teal) |
| `{PRIMARY_DARK_HEX}` | Hover / pressed state | `#4a8a62` |
| `{PRIMARY_LIGHT_HEX}` | Hero gradient end / soft section bg | `#F0F7F2` |
| `{ACCENT_HEX}` | Highlight / amber-style accent | `#E8C547` |
| `{BG_HEX}` | Page background | `#FAF8F4` (warm white) |
| `{BODY_TEXT_HEX}` | Body text | `#2C2C2C` |
| `{HEADING_FONT}` | Headings — Google Font name | `DM Sans` |
| `{ACCENT_FONT}` | Eyebrows / pull-quotes — Google Font name | `Caveat` |
| `{BODY_FONT}` | Body text — Google Font name | `DM Sans` |
| `{LOGO}` | Path to logo asset OR "text-only logo with brand name" | `/assets/logo.svg` or `text-only` |
| `{TONE_REGISTER}` | `formal` or `casual` — affects copy register | `casual` |
| `{DU_OR_SIE}` (DE only) | `Du` (trades, casual B2B) or `Sie` (professional services, formal) | `Sie` |
| `{REFERENCE_LANDING_URL}` | Existing landing the operator wants design fidelity to | `https://example.com/landing` |
| `{LANGUAGE}` | `EN` or `DE` (or both) | `DE` |

If `{REFERENCE_LANDING_URL}` is provided, fetch it and extract the actual hex codes + font stack — DO NOT guess. The operator's existing site is the source of truth for CI, not the skill's defaults.

**0c. Operator-supplied content placeholders**

| Variable | What to ask |
|---|---|
| `{PRODUCT_NAME}` | Your product/service name |
| `{COMPANY}` | Company / brand name shown in nav and footer |
| `{DOMAIN}` | Your website domain |
| `{BOOKING_LINK}` | Calendly / booking endpoint |
| `{FOUNDER_NAME}` | Founder name for team section |
| `{WEBHOOK_URL}` | Form submission endpoint (Zapier / Make / custom API) |

**0d. Foundation upstream (mandatory)**

The landing page consumes the Asset Foundation CSV + niche-brief MD produced by the `asset-foundation-builder` skill. If those don't exist, run that skill FIRST. Hero / pain story / stats / feature cards all map to specific Foundation rows (see Hand-off section below).

---

### Step 1: Research the Niche's Top Pains
- Use web search to find the **Top 5 biggest pains** for the target group
- Sources: YouTube, industry studies, forums, trade associations, Innungen
- Get **hard data points** (percentages, costs, time lost) — these become the stats bar and hooks
- Focus on: What keeps the Geschäftsführer up at night? What's the #1 complaint?

### Step 2: Build the Hook (Hero Section)
- **Urgency badge**: Lead with the most relevant sourced stat, translated to the reader's firm where possible (Principle 8)
- **Headline**: A concrete scene from one role's week (Principle 4). Write one headline per buying role (Principle 5)
- **Curiosity line**: "So lösen es die Besten der Branche" only if you can show them (Principle 9). Otherwise name your one real case, or ask "What if …?"
- **Sub-headline**: Name the top 2-3 pains explicitly. Emphasize: no IT project, no technical knowledge, from the industry
- **CTA**: Curiosity-driven, NOT product-driven. Pattern: "Jetzt herausfinden, wie [niche] unter [size] [pain] lösen"
- **Trust line**: "Kein IT-Projekt · Kein technisches Wissen nötig · Von [niche] für [niche] · Server in Deutschland"

### Key CTA Principles
- **Drive curiosity, don't pitch product**: "Jetzt herausfinden wie..." not "Kostenlos testen"
- **No AI language**: Say "Automatisierung", "Entlastung", "Assistent" — not "KI" or "AI"
- **Frame as secret knowledge**: "How the best ones do it" — makes people want to peek behind the curtain
- **Low commitment**: "herausfinden", "ansehen", "erfahren" — not "anfragen", "buchen", "kaufen"

### Step 3: Pain Story Section
- Write a narrative "Montagmorgen" story using the niche's real daily pain
- Include specific scenarios (names, addresses, situations)
- End with a pullquote that captures the emotional core
- Transition: "Trotzdem gibt es [niche] die es anders machen..."

### Step 4: Stats Bar
- 4 data points from the research, with sources cited
- Use the most shocking/relatable numbers
- Format: Big number + short explanation

### Step 5: Pain Cards (Pain-Point Driven)
- 4–6 cards, each named after a PAIN (not a feature). No mechanism, no technology (Principles 2 and 7)
- Pattern: "[Pain] bändigen/beenden/im Griff" — not "AI Email Triage"
- Each card: Pain description + Before/After comparison
- Use real industry terminology the niche uses daily

### Step 6: How It Works
- 4 simple steps: Check machen → Gespräch → Verbinden → Läuft
- Emphasize: No IT, no technical knowledge, no team training needed
- Position the founder as "selbst Unternehmer" not "tech expert"

### Step 7: Daily Example / Chat Mock (optional)
- Skip it for skeptical, conservative audiences or when the operator wants no product on the page; a "How it can look" scene written in prose works better there
- Show a realistic morning briefing conversation
- Use niche-specific scenarios (e.g., a recurring inbound the practitioner deals with daily — quote requests, compliance deadlines, customer escalations)
- Make it feel like "someone already did my morning work"

### Step 8: Case Study ("Stell dir vor")
- Aspirational narrative: What a good day looks like WITH the product
- End with 4 result boxes (time saved, tasks automated, no system changes, your pace)

### Step 9: Testimonials
- Only real, sourced quotes, each used once (Principle 10). No testimonials yet? Use one reference case with facts instead
- 3 testimonials: 2 from the niche, 1 cross-niche credibility
- Frame as operational relief, NOT technology praise

### Step 10: Objections (FAQ)
- 5-6 objections, reframed from niche perspective
- Lead with "Ich bin kein Technik-Mensch" — always the #1 fear
- Address: time to implement, data privacy, false actions, existing software compatibility

### Step 11: Comparison (Product vs. Traditional)
- Side-by-side: "Klassische Software" vs "{Product}"
- Emphasize: No migration, no training, no team involvement

### Step 12: Guarantee
- Only a guarantee that is contractually backed and clearly defined (Principle 16)
- Scarcity ("10 Pilotplätze") only if the limit is real (Principle 13)

### Step 13: Team Section
- Frame founders as industry people, NOT tech people
- "Selbst Unternehmer, verwaltet eigene [Objekte/Betrieb]"
- "In Familienbetrieb aufgewachsen" — relate to the audience

### Step 14: Exit-Intent Popup
- "5 Fehler, die [niche] unter [size] am meisten kosten"
- Pain-focused mistakes (waiting for staff, big software projects, thinking automation is for big firms)
- CTA: Same curiosity-driven pattern

### Step 15: Build Signup Page (Progressive Capture)

**Flow — email is ALWAYS captured first:**

| Step | Fields | Required? | Skip? |
|------|--------|-----------|-------|
| 1 | Email + Name | Email only | No |
| 2 | Phone | No | Yes |
| 3 | Position + Team size | No | Yes |
| 4 | Quiz: Org size | Click = advance | Auto |
| 5 | Quiz: Biggest time waster | Click = advance | Auto |
| 6 | Quiz: What held you back | Multi-select | Submit |

**Key rules:**
- Email fires to backend IMMEDIATELY at step 1
- `beforeunload` saves whatever data collected if they close tab
- No required fields except email — nothing blocks the flow
- Enter key works on every step
- Success screen shows booking link (e.g., Calendly)
- Landing page must link to `{niche}-signup.html` in all CTAs

## Worked example — illustrative only

Below is what the hero + pain-story sections look like for a fictional `{Your Venture}` selling a dental-practice CRM. Read for the structural moves — the language must come from your own niche research and Asset Foundations.

### Hero (Step 2 output)

```
🦷 73% of independent dental practices report missing 1+ recall appointments
   per day to scheduling glitches. Industry data.

Headline:    Patient recalls don't have to be a Monday-morning fight.
             So lösen es die führenden Praxen unter 10 Stuhlplätzen.

Sub-line:    No new software for your team. No IT project. Built by
             dentists, for dentists. Server in Germany.

CTA:         Jetzt herausfinden, wie führende Zahnarztpraxen
             unter 10 Stuhlplätzen ihre Recalls automatisieren.

Trust:       Kein IT-Projekt · Kein technisches Wissen nötig
             Von Praxisinhabern für Praxisinhaber · Server in Deutschland
```

### Pain story (Step 3 output)

> Montagmorgen, 7:45. Frau Dr. {Name} öffnet die Praxis. 14 Anrufe auf der Mailbox vom Wochenende, davon 9 Recall-Verschiebungen. Die Helferin am Empfang ist heute krank. Bis 9 Uhr sind die ersten drei Patienten schon da — zwei davon mit Terminen, die im System nicht mehr gepflegt sind. Sie macht den Spagat zwischen Behandlung und Telefonat den ganzen Vormittag. Mittags ist sie schon ausgelaugt. Das ist die Praxis, die sie sich nie aufbauen wollte.
>
> *"Ich wollte Zahnärztin sein, keine Telefonzentrale."*

Trotzdem gibt es Praxen, die es anders machen.

### What this example shows you (the structural moves)

- **Stat-led hero** with a concrete percentage and a cited source.
- **Niche-specific scenario**: Stuhlplätze, Empfang, Recalls — the prospect recognises their world in the first paragraph.
- **Pull-quote**: customer-voice in italics ends the pain section.
- **CTA is curiosity, not sales**: *"Jetzt herausfinden..."* not *"Kostenlos testen"*.
- **Trust line** addresses the niche's three biggest fears explicitly: technical complexity, foreign software, data location.

If your hero + pain story read with this kind of niche specificity — real industry stats, real terminology, customer voice in the pull-quote — you're done. If it reads like generic SaaS copy, go back to Step 1 and dig deeper.

## Language Rules
- German (du-Form or Sie-Form depending on niche), professional but warm
- NO "AI", "KI", "künstliche Intelligenz" in headlines or CTAs
- Use instead: "Automatisierung", "Entlastung", "Assistent", "übernimmt für dich"
- Industry jargon: Use the exact terms the niche uses (WEG, ETV, Kehrbezirk, Angebot, etc.)
- Pain-first, solution-second in every section

## Technical
- Single HTML files, no build tools
- Google Fonts: DM Sans + Caveat
- CSS variables for theming (swap accent color per niche if needed)
- Scroll animations via IntersectionObserver
- Exit-intent via mouseout on document
- Form data logged to console with TODO for webhook endpoint
- Booking link as placeholder: `{BOOKING_LINK}`

## File Naming
- `{niche}.html` — Landing page
- `{niche}-signup.html` — Signup flow
- Store in: `{project-root}/landing-pages/` folder

## Anti-patterns
- **Hero copy talks about the product, not the prospect's pain.** Hero headline must echo what the prospect already says — not what your team calls the feature.
- **Generic stock imagery instead of niche-specific scenarios.** A dental-practice CRM page with stock office photos converts worse than the same page with a real reception-desk shot.
- **More than one primary CTA on the page.** The brain freezes when forced to choose. One headline CTA, one secondary, no third.
- **A signup form with more than 3 required fields on first capture.** Every extra field cuts conversion ~7%. Email first; everything else can come later.
- **No commitment ladder behind a "Learn more" CTA.** "Learn more" is not a CTA — it's a stall. Always escalate to a date, a download, or a calendar slot.
- **Long-form copy with no scannable subheadings.** Readers leave in 8 seconds without subheadings; subheadings let them self-qualify.

## Customization Checklist
Before using, replace these placeholders:
- `{PRODUCT_NAME}` — Your product/service name
- `{BOOKING_LINK}` — Your Calendly or booking link
- `{FOUNDER_NAME}` — Founder name for team section
- `{DOMAIN}` — Your website domain
- `{WEBHOOK_URL}` — Your form submission endpoint (e.g., Zapier, Make, custom API)

## Hand-off — what to consume from upstream
- **Hero headline** ← Asset Foundation Row 10 (Bodacious Claim) + Row 2 (Deepest Desires)
- **Pain story section** ← Rows 3–5 (Up-at-night / Frustrated / Angry) — use direct quotes from transcripts
- **"Why this is different"** ← Row 6 (Tried-but-failed) — name the failed alternatives explicitly
- **Stats bar** ← Row 7 (Trends) + Row 11 (quantified Secondary Benefits)
- **Feature cards** ← Row 11 (each card frames one quantified benefit)
- **Daily-example / scenario** ← Row 12 (Auxiliary Benefits — identity-level payoff)
- **Objection FAQ** ← Row 6 + Row 4 (frustration sources)

Run the `asset-foundation-builder` skill first if you don't have a filled CSV.

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
- [ ] **Build Principles applied** — one headline per role, scene not claim, no product in the hero, only real proof, no placeholder visible.
- [ ] **Three checks run** — slop check (the `unleash-stop-slop` skill), target-group check per role, fact check (Principle 21).
- [ ] **No venture-specific brand baked in** — output uses operator-supplied `{COMPANY}`, `{PRODUCT_NAME}`, `{PRIMARY_HEX}` etc. The skill itself is venture-agnostic; venture content is injected at runtime.
