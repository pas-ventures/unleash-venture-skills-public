# Niche Research Skill

## When to Use
- Before writing outbound copy for a new niche
- Before building a landing page for a new niche
- "Research [niche] for me"
- "What are the biggest pains for [target group]?"
- Any time you need industry-specific data points for German SMB niches

## Overview
Research a German SMB niche to produce the data needed for outbound copy and landing pages. Output is a structured brief that feeds directly into the Outbound Copy Manager and Landing Page Builder skills.

## Step-by-Step Procedure

### Step 1: Define the Niche
Confirm:
- **Niche name** (e.g., Hausverwaltungen, SHK-Handwerk, Schornsteinfeger)
- **Target role** (Inhaber, Geschäftsführer, Meister, Bezirksinhaber)
- **Company size** (solo, 2-5, 5-15, 15-50 employees)
- **Product/service** this research is for

### Step 2: Web Research
Search for each of these data points:

#### Market Size
- Total number of businesses in DE (Statistisches Bundesamt, relevant industry association — e.g., ZDH for Handwerk, DDIV for Hausverwaltungen, BFB for Freie Berufe)
- Trend: growing, shrinking, consolidating?
- Key stat: "X Betriebe in DE"

#### Top 5 Pains (with hard numbers)
Search queries to try:
- `"{niche} größte Herausforderungen" site:handwerksblatt.de OR site:iww.de`
- `"{niche} Probleme Digitalisierung" site:youtube.com`
- `"{niche} Fachkräftemangel Studie"`
- `"{niche} Zeitaufwand Bürokratie Statistik"`
- `"{niche} Forum Probleme` (industry forums, Innungen)

For each pain, find:
- **Percentage or hours** (e.g., "30-40% der Arbeitszeit = Büro")
- **Money impact** (e.g., "300-800€ pro Energieberatung bleiben liegen")
- **Source** (study name, publication, year)

#### Industry Jargon
- What do they call their clients? (Eigentümer, Bauherr, Kunden, WEG)
- What are their key processes? (ETV, Kehrbezirk, Angebotserstellung)
- What tools/software do they currently use? (Haufe PowerHaus, TopKontor, etc.)
- How do they talk about their day? (Baustelle, Dach, Objekt, Bezirk)

#### Competitive Landscape
- What solutions exist? (industry software, generic tools)
- What do they hate about current solutions? (zu komplex, zu teuer, US-Cloud)
- What have they tried and abandoned?

#### Emotional Core
- Why did they start this business? (Freiheit, Handwerk, eigener Chef)
- What frustrates them most? (Bürokratie statt Kernarbeit)
- What would their ideal day look like?
- Find 1-2 real quotes from forums/YouTube/interviews
- **Note:** If you can't extract YouTube transcripts directly, video titles, descriptions, and comment sections are valid sources for quotes and pain language

### Step 3: Produce the Niche Brief

Output format:

```markdown
# Niche Brief: {Niche Name}

**Date:** {YYYY-MM-DD}
**Market:** {X} Betriebe in DE
**Entscheider:** {role}
**Ansprache:** {Du/Sie}
**Trend:** {growing/shrinking/consolidating}

## Top 5 Pains
1. **{Pain}** — {stat with source}
2. **{Pain}** — {stat with source}
3. **{Pain}** — {stat with source}
4. **{Pain}** — {stat with source}
5. **{Pain}** — {stat with source}

## Money Left on Table
- {Specific revenue opportunity they're missing, with numbers}

## Industry Jargon
- Client term: {what they call customers}
- Key processes: {list}
- Current tools: {list}
- Daily language: {how they describe their work}

## Emotional Core
- Started because: {motivation}
- Frustrated by: {what kills their joy}
- Dream day: {what they wish work looked like}
- Quote: "{real quote from forum/interview}" — {source}

## Competitive Landscape
- Current solutions: {list}
- Why they hate them: {list}
- Gap: {what's missing}

## Suggested Hooks (for copy)
- Stat hook: "{number} — {pain}"
- Question hook: "Wie lösen Sie {pain}?"
- Peer hook: "Andere {niche} in Ihrer Region..."
- Provocation hook: "{X}% Ihrer Zeit geht für {pain} drauf"

## Sources
- {URL or publication} — {what data point}
```

### Step 4: Save & Link
- Save brief to: `{project-root}/niche-briefs/niche-brief-{niche-slug}.md`
- Reference in the venture's outbound copy or landing page files

## Quality Checklist
- [ ] At least 3 pains have hard numbers (%, hours, euros)
- [ ] At least 1 real quote from the industry
- [ ] Market size sourced (not guessed)
- [ ] Industry jargon verified (not generic business terms)
- [ ] Ansprache confirmed (Du vs Sie) — Rule of thumb: Sie for formal industries (Steuerberater, Ärzte, Anwälte, Hausverwaltungen), Du for trades and informal (Handwerker, Gastro, Fitness)
- [ ] Sources listed for key claims

## Hand-off — relationship with Asset Foundation
Niche Research is the **outside-in** view (market structure, association data, public discourse). Asset Foundations is the **inside-out** view (one prospect at a time). They cross-validate:

- **Niche pains (Niche Research)** should match Asset Foundation Rows 3–5 (Up-at-night / Frustrated / Angry). If they don't, your transcripts may not be representative — or your secondary research is stale.
- **Market size context (Niche Research)** ↔ Asset Foundation Row 7 (Trends + threats)
- **Industry jargon (Niche Research)** ↔ verbatim language in Asset Foundation Rows 3–5 + Row 6
- **Suggested hooks (Niche Research)** ↔ Asset Foundation Row 10 (Bodacious Claim formulas)

Run both in parallel before any copy. Discrepancies between them are signal, not noise.
