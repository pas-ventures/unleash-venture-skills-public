# Landing Page Builder Skill

## Overview
Build high-converting niche landing pages for B2B SaaS targeting German SMBs. Two-page setup: Landing Page + Signup Page with progressive email capture.

## Architecture
- **Page 1**: `{niche}.html` — Landing page (hook, pain, features, social proof, exit popup)
- **Page 2**: `{niche}-signup.html` — Multi-step signup with progressive data capture (email first)

## Step-by-Step Procedure

### Step 1: Research the Niche's Top Pains
- Use web search to find the **Top 5 biggest pains** for the target group
- Sources: YouTube, industry studies, forums, trade associations, Innungen
- Get **hard data points** (percentages, costs, time lost) — these become the stats bar and hooks
- Focus on: What keeps the Geschäftsführer up at night? What's the #1 complaint?

### Step 2: Build the Hook (Hero Section)
- **Urgency badge**: Lead with the most shocking stat (e.g., "73% nennen Fachkräftemangel als #1 Problem")
- **Headline**: State the pain in concrete numbers, then promise: "So lösen es die Besten der Branche"
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

### Step 5: Feature Cards (Pain-Point Driven)
- 6 cards, each named after a PAIN being solved (not a feature)
- Pattern: "[Pain] bändigen/beenden/im Griff" — not "AI Email Triage"
- Each card: Pain description + Before/After comparison
- Use real industry terminology the niche uses daily

### Step 6: How It Works
- 4 simple steps: Check machen → Gespräch → Verbinden → Läuft
- Emphasize: No IT, no technical knowledge, no team training needed
- Position the founder as "selbst Unternehmer" not "tech expert"

### Step 7: Daily Example / Chat Mock
- Show a realistic morning briefing conversation
- Use niche-specific scenarios (e.g., WEGs for Verwalter, Feuerstätten for Schornsteinfeger)
- Make it feel like "someone already did my morning work"

### Step 8: Case Study ("Stell dir vor")
- Aspirational narrative: What a good day looks like WITH the product
- End with 4 result boxes (time saved, tasks automated, no system changes, your pace)

### Step 9: Testimonials
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
- 90-day pilot, zero risk
- "10 Pilotplätze" creates urgency

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

Run `asset-foundation-builder.md` first if you don't have a filled CSV.
