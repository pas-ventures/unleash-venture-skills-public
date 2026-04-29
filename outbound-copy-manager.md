# Outbound Copy Manager Skill

## When to Use
- "Write outbound emails for [niche]"
- "Create a cold email sequence for [target group]"
- "Add a new niche to our outbound"
- "Iterate on the email copy based on [A/B test results / feedback]"

## Overview
Create and manage cold outbound email sequences targeting German SMB niches. Produces ready-to-send copy in markdown format. Based on Hormozi, Belfort, and Brunson frameworks.

## Core Principles (always apply these)

### Tone & Approach
- **Pain-first**: Open by asking how THEY solve the problem — never pitch the product
- **No AI/KI language**: Use "vereinfachte Automatisierung", "Entlastung", "Assistent" — never "AI", "KI", "künstliche Intelligenz"
- **Peer social proof**: "50+ Gespräche letzte Woche, alle sehen die gleichen Muster"
- **Remove fear**: No US cloud, no IT project, servers in Germany, DSGVO-konform
- **Feedback angle**: "Wie lösen Sie das intern? Mich würde ehrlich interessieren"
- **Soft CTA**: "Würde mich freuen, mal kurz zu sprechen" — not hard sell
- **Unternehmer zu Unternehmer**: Peer framing, not vendor-to-buyer

### Frameworks
- **Hormozi** (100M Leads): Value-first, specific numbers, minimize effort/sacrifice
- **Belfort** (Straight Line): Pattern interrupt, certainty transfer, urgency via scarcity
- **Brunson** (DotCom Secrets): Hook-Story-Offer, Epiphany Bridge via peer quotes

### Ansprache Rules
- **Sie**: Hausverwaltungen, Steuerberater, Ärzte, Anwälte — formal industries
- **Du**: Handwerker, Schornsteinfeger, Gastro, Fitness — trades & informal industries
- Match the niche's natural communication style

## Sequence Structure

### 3-Email Sequence
| Email | Timing | Purpose | Length |
|-------|--------|---------|--------|
| Email 1 — Opener | Day 0 | Ask about their pain, establish peer proof | Multiple variants (A-E) |
| Email 2 — Follow-up | Day 3 | Deepen pain, show concrete solution, quote from peer | Single version |
| Email 3 — Breakup | Day 8 | Last chance, results list, soft exit | Single version |

### Email 1 Variants (always create all 5)
| Variant | Style | Length |
|---------|-------|--------|
| A | Lang — full pain list + peer proof | ~200 words |
| B | Mittel — pain + peer proof, compact | ~100 words |
| C | Kurz — pure pain question, minimal | ~70 words |
| D | Feedback-Angle — research framing | ~100 words |
| E | Provokant-kurz — shocking stat as hook | ~80 words |

### Alternative Subject Lines (always include 5 for A/B testing)

## Step-by-Step Procedure

### Step 1: Gather Niche Intel
Before writing, you need:
- [ ] **Niche name** and market size (# of businesses in DE)
- [ ] **Entscheider** role (Inhaber, Geschäftsführer, Meister, Bezirksinhaber)
- [ ] **Top 3 pains** with specific numbers (hours lost, money left on table, % of time wasted)
- [ ] **Ansprache** (Du or Sie)
- [ ] **Industry-specific jargon** (WEG, ETV, Kehrbezirk, Feuerstätte, etc.)
- [ ] **Product name + what it does** (what solution is being offered)
- [ ] **Differentiator** (deutsche Server, kein IT-Projekt, etc.)

Use the **Niche Research skill** if this data isn't available yet.

### Step 2: Write the Header Block
```markdown
# Outbound: {Niche Name}

**Markt:** {X} Betriebe in DE | {Entscheider-Rolle} = Entscheider
**Ansprache:** {Du/Sie}
**Biggest Pain:** {Pain 1}, {Pain 2}, {Pain 3}
```

### Step 3: Write Email 1 — All 5 Variants
For each variant, include:
- **Betreff:** (subject line)
- Full email body
- Sign-off (same for all emails): `{SENDER_NAME}\n{COMPANY} | {DOMAIN}`

Key elements per variant:
- **A (Lang)**: "ich suche den Ansprechpartner..." → pain list (4 bullet points with →) → peer proof → fear removal → feedback question → soft CTA
- **B (Mittel)**: Pain summary in 2 sentences → peer proof → "passt nicht bei jedem" → CTA
- **C (Kurz)**: Direct question → 2-sentence pain → peer proof one-liner → "10 Minuten?"
- **D (Feedback)**: "ich arbeite an einer Lösung für..." → pain summary → peer proof → "Ihr Feedback wäre wertvoll"
- **E (Provokant)**: Stat in subject line → "Kennt ihr das?" → number-heavy pain → peer proof → CTA

### Step 4: Write Email 2 — Follow-up (~100-150 words)
- Subject: `Re: {Email 1 Betreff}` (reply threading)
- Acknowledge they're busy (niche-specific: "als Meister sitzt man nicht am Rechner" / "als Verwalter hat man keine Zeit")
- One powerful stat or peer quote
- Concrete solution description (what it looks like in practice, NOT features)
- Upgrade CTA: "15 Minuten zeigen, wie das konkret aussieht"

### Step 5: Write Email 3 — Breakup (~80-120 words)
- "Zwei Nachrichten, keine Antwort — alles gut"
- Mention pilot/trial offer (90 Tage, kein Risiko)
- Results list (4 bullet points with →): time saved, money gained, specific outcomes
- Binary close: "Falls nicht → melde mich nicht wieder. Falls doch → kurze Antwort oder {BOOKING_LINK}"

### Step 6: Add Subject Line Table
5 alternative subject lines for A/B testing, covering different angles.

### Step 7: Output
- Write to markdown file: `{project-root}/outbound/outbound-{niche-slug}.md`
- Optionally sync to Google Doc or push to GitHub repo

## Quality Checklist
Before delivering, verify:
- [ ] No "AI", "KI", or "künstliche Intelligenz" anywhere
- [ ] Pain is mentioned before any solution
- [ ] Specific numbers (hours, euros, percentages) in every email
- [ ] Peer proof ("50+ Gespräche", "Betriebe in deiner Region")
- [ ] Fear removal (deutsche Server, kein IT-Projekt, DSGVO)
- [ ] Soft CTA — never "Jetzt kaufen" or "Demo buchen"
- [ ] Correct Ansprache (Du/Sie) consistently throughout
- [ ] Industry jargon used correctly
- [ ] `{SENDER_NAME}` and `{BOOKING_LINK}` as placeholders
- [ ] All 5 Email 1 variants included

## Worked example — illustrative only

Below is what a 3-email sequence looks like for a fictional `{Your Venture}` selling a vertical accounting platform to small CPA firms in the US. Read for the structural moves — your copy must come from your own customer transcripts.

### Email 1 — Variant A (problem-led opener, ~120 words)

```
Subject: 11pm reconciliations again?

{First name},

Saw you've been running {firm name} for {N} years out of {city}. Most 2–4-partner CPA shops I talk to in {state} say the same thing about January–April: the reconciliation work pushes the partners back to the desk after dinner. Three weekends in a row.

We built {Your Venture} for exactly that pattern. Vertical-built for CPA firms under 10 staff. Bookkeeping platform pulls in feeds, AI categorises, exceptions land in a queue your senior reviews — not your partners.

Three of our pilot firms cut their April overtime by 60%+ in their first season.

Worth a 15-minute look at how it works for {firm name}? I have Wednesday or Thursday next week open.

— {Sender}
```

### Email 1 — Variant B (peer social-proof opener, ~110 words)

```
Subject: How {peer firm} cut April overtime 60%

{First name}, quick note — {peer firm} (similar size to {firm name}, also serving small businesses in {state}) used {Your Venture} this past tax season. Partners home by 7pm during the busy weeks. April overtime down 60%+ vs prior year.

The platform is built specifically for 2–4-partner CPA firms — feeds, categorisation, exceptions queue. No Excel rebuild, no migration project.

Open to a 15-minute walkthrough? Wednesday or Thursday next week works on my side.

— {Sender}
```

### Email 2 — Follow-up (Day 4, ~120 words)

```
Subject: Re: 11pm reconciliations again?

{First name}, following up. Specific point that landed with most CPAs we talk to:

{Your Venture}'s exception queue cuts 80–90% of the manual review work. The remaining 10–20% — the genuinely ambiguous transactions — still hit your senior. That's the whole point. The platform doesn't try to replace judgment, it just stops you doing the easy 80% by hand at midnight.

If the timing is wrong this season, that's totally fine. If it's the value, I'd love to know what's missing — written reply works, no need for a call.

— {Sender}
```

### Email 3 — Breakup (Day 9, ~80 words)

```
Subject: Closing the loop

{First name}, last note — assuming this isn't the right time. I'll stop here so I'm not in the way.

If anything changes between now and next January, you know where to find me. And if you'd ever want me to reach out to a peer in {state} who's a better fit, I'm always open to that.

— {Sender}
```

### What this example shows you (the structural moves)

- **Subject lines name the pain in their words** ("11pm reconciliations") — not generic ("Quick question").
- **Two opener variants test different angles** (problem-led vs peer social-proof). Send each to half the list and compare reply rates.
- **Vertical specificity** ("2–4-partner CPA shops in {state}") earns the right to be in their inbox. Generic outbound dies on opener.
- **Email 2 introduces a concrete mechanism** (the exception queue) — moves from "we have a thing" to "here's why it works for your specific workflow."
- **Email 3 (breakup) is honest, low-pressure, asks for a referral** — the highest-yielding cold breakup pattern in B2B.

If your sequence reads with this kind of niche-specific concreteness — real terms, real cadence-fit reasoning, no vague "we help companies achieve growth" — you're done.

## Anti-patterns
- **Email opens with "I hope you're well."** Instant trash-flag. Open with a specific observation about their world, not a niceness ritual.
- **Product mentioned before paragraph 2.** Makes the email pitch-shaped from the first line. The prospect's brain pattern-matches "ad" and stops reading.
- **Generic personalisation tokens without genuine specificity.** `{Company}` doesn't fool anyone. Either personalise with a real, specific reference (their post, their hire, their funding) or skip the variable entirely.
- **Day-1 CTA asking for a 30-min demo.** Escalator too steep. Day-1 CTA is a yes/no question or a 5-line content share. The demo close is Email 3 at the earliest.
- **Subject lines longer than 6 words.** Phone preview cuts them. Aim 4–6 words, end with the most curiosity-load.
- **Email 2 that doesn't reference Email 1.** Feels like a fresh cold blast. Always thread to the previous send so the prospect feels continuity, not noise.

## Customization Checklist
Before using, replace these placeholders:
- `{SENDER_NAME}` — Person sending the emails
- `{COMPANY}` — Your company name
- `{DOMAIN}` — Your website domain
- `{BOOKING_LINK}` — Your Calendly or booking link
- `{PRODUCT_NAME}` — Your product/service name

## Hand-off — what to consume from upstream
- **Email 1 opener** ← Asset Foundation Row 1 (Position) + Row 2 (Deepest Desires)
- **Email 1 body** ← Rows 3–5 (Up-at-night / Frustrated / Angry) — verbatim where possible
- **Email 2 (alternatives)** ← Row 6 (Tried-but-failed)
- **Email 3 (close)** ← Row 9 (Solution / Vehicle) + Row 10 (Bodacious Claim)
- **Subject lines** ← rotate Row 2 (desire) / Row 7 (trend) / Row 10 (claim)

Run `asset-foundation-builder.md` first.
