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

## Customization Checklist
Before using, replace these placeholders:
- `{SENDER_NAME}` — Person sending the emails
- `{COMPANY}` — Your company name
- `{DOMAIN}` — Your website domain
- `{BOOKING_LINK}` — Your Calendly or booking link
- `{PRODUCT_NAME}` — Your product/service name
