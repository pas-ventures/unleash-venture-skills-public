# Asset Foundation Builder Skill

## Overview
Turn raw customer call data into the **Asset Foundations** every downstream asset depends on — ICP, deepest desires, frustrations, failed attempts, market shifts, and the layered benefit stack. Built on Dan Kennedy's Sales Letter Framework: you cannot write copy that converts until you have done the foundation work.

The output is a single spreadsheet — one row per framework question, one column per niche — that becomes the input for landing pages, sales scripts, ads, drip campaigns, offer design, and outbound copy. Every other skill in this repo gets sharper when fed an Asset Foundation produced by this skill.

## When to Run
- **You have call recordings or transcripts** (sales, qualification, design-partner interviews, customer success calls). One well-qualified call works. Five to ten dialled in. Ten to twenty produce a Foundation that compounds.
- **You are about to write any market-facing copy.** Skipping this step means you are guessing what the customer feels — Kennedy's principle: *"Don't write to people. Listen to people, then echo what they already said."*
- **Your existing positioning feels generic** and you suspect you are speaking *about* the customer instead of *as* the customer.

## Inputs
1. **Transcripts** — plain text, Markdown, or VTT. Multiple files supported. Anonymise customer names before feeding if the output will be shared widely.
2. **Qualification question set** — the questions you ask on a discovery call. If you don't have one, the skill will draft one from common B2B qualification frameworks (BANT, MEDDIC, the Mom Test) and surface it to you for review.
3. **Niche hypothesis (optional)** — if you already suspect 3–5 distinct buyer segments, name them. Otherwise the skill will cluster the transcripts and propose niches.

## Output
A CSV (paste-ready into Google Sheets or Excel) with this exact structure:

| Field | Niche 1 | Niche 2 | Niche 3 | … |
|---|---|---|---|---|
| Position (Location, income, team size, budget, vertical, job title, marital status, family status, years in position) | | | | |
| Deepest Desires of your prospect | | | | |
| What keeps them up at night, eyes wide open, glaring at the ceiling? | | | | |
| What are they frustrated by? Why? How are they feeling? | | | | |
| What are they angry at? Why? | | | | |
| What have they tried but have failed at? | | | | |
| What trends are happening in the market? How will this negatively affect them if they don't adapt? | | | | |
| What will happen if they don't make a change? How much time do they have? | | | | |
| Solution/Vehicle | | | | |
| Bodacious Claim (What claim can you make that appeals to your prospects' deepest desires?) | | | | |
| Secondary Benefits (What other metrics are you affecting and by how much? What frustrations are eliminated or reduced? How much time are they saving doing what? What can they forget about?) | | | | |
| Auxiliary Benefits (How do they feel? How much stress is eliminated? What other areas are affected by the transformation and by how much?) | | | | |

Save as `asset-foundations-{venture}-{YYYY-MM-DD}.csv` and import to Sheets.

## Methodology (Dan Kennedy + the Sales Letter Framework)

The 12 fields are not arbitrary. They mirror the spine of a Kennedy long-form sales letter:

1. **Position** — the prospect must recognise themselves in the first sentence. Specificity (location, role, family status, years in position) signals you understand their world. Generic ICPs ("SMB founder") never trigger recognition.
2. **Deepest Desires** — Kennedy: *"Enter the conversation already happening in their head."* Desire is the engine; everything else amplifies or unblocks it.
3–5. **Up-at-night / Frustrated / Angry** — the emotional layer. Each is distinct: fear (up-at-night), helplessness (frustrated), blame (angry). Skip one and the copy reads flat.
6. **Tried but failed at** — eliminates the alternatives in the prospect's mind before you pitch yours. Kennedy's "false-solutions audit."
7. **Trends + threats** — gives urgency without being apocalyptic. Connects the prospect's problem to a wider, observable shift.
8. **Cost of inaction + time horizon** — the close-the-loop on urgency. Without a date or a deadline, urgency dissolves.
9. **Solution / Vehicle** — only NOW does your product enter. The first 8 rows earn the right to mention it.
10. **Bodacious Claim** — Kennedy's term. The single audacious promise that maps directly onto Row 2 (Deepest Desires). Not a tagline. Not a feature. The thing that, if true, makes them buy.
11. **Secondary Benefits** — measurable side-effects. Time saved, frustrations eliminated, cognitive load removed. Quantify wherever possible.
12. **Auxiliary Benefits** — the emotional payoff. How they *feel* after the transformation. How their family, team, or status is affected.

Skip layers and the asset built on top will leak conversion. Do all twelve and the landing page, sales script, and ad copy almost write themselves.

## Step-by-Step Procedure

### Step 1: Cluster transcripts into niches
- Read every transcript end-to-end. Do not skim.
- Tag each speaker by: industry vertical, company size, role, geography, apparent buying urgency.
- Group transcripts where the **language** of the pain matches, not just the demographic. A 10-person agency CEO and a 50-person SaaS founder may live in the same niche if they describe their pain identically.
- Propose 3–5 niches. Name each by their most defining trait (role + vertical + size — e.g., *"Mid-market manufacturing CEO, 50–250 staff, DACH"*).
- Flag any single transcript that doesn't fit a cluster — these are either a sixth niche or a misqualified prospect. Surface to the user.

### Step 2: Fill Row 1 (Position) verbatim
- Pull every demographic detail mentioned in the transcripts: location, team size, revenue band if disclosed, job title, marital status, family status, years in role, vertical, budget signals.
- Write in compact form. Use line breaks inside cells so each attribute is scannable.
- If a detail is missing across all transcripts in a niche, mark it `[unknown — ask in next call]`. Do not guess.

### Step 3: Fill Row 2 (Deepest Desires)
- Listen for *aspirations* — what they say they want, what they envy, what status object they reference, what they would do "if I had this nailed."
- Phrase in their words, not yours. *"Get business to the next level"* beats *"achieve scalable growth."*
- Look for what they want to **be**, not just what they want to **do**. Status, recognition, security, peace of mind.

### Step 4: Fill Rows 3–5 (Up-at-night / Frustrated / Angry)
- Three distinct emotional registers — keep them separate.
  - **Up at night** = fear of loss, the catastrophe scenario.
  - **Frustrated** = helplessness, things-aren't-moving.
  - **Angry** = blame, betrayal, things-are-actively-wrong.
- Each row should pass the *"would the prospect underline this if they read it"* test.
- Use direct quotes from the transcript wherever possible. Mark them with quotation marks in the cell.

### Step 5: Fill Row 6 (Tried but failed at)
- List specific tools, agencies, hires, frameworks, channels they have already tried.
- Note **why** each failed — usually one of: too expensive, too slow, didn't understand the niche, lacked accountability, founder didn't follow through.
- This row is the source for your *"why this is different"* messaging later.

### Step 6: Fill Rows 7–8 (Trends + Cost of inaction)
- **Trends**: which shifts in their market are observable and accelerating? Pull from what they themselves named, not what you think is true.
- **Cost of inaction**: their stated worst case. If they did not name one, surface this as a follow-up question for the next call.

### Step 7: Fill Row 9 (Solution / Vehicle)
- Your product or service, named precisely.
- If different niches require different framing of the same product, write the framing per niche, not just the name.

### Step 8: Fill Rows 10–12 (Bodacious Claim + Secondary + Auxiliary Benefits)
- **Bodacious Claim**: one sentence that, if proven, makes the prospect buy today. Map directly back to Row 2 (Deepest Desires). Numbers help; specificity helps more.
- **Secondary Benefits**: enumerate every quantifiable side-effect. Time saved, money saved, headcount avoided, errors reduced.
- **Auxiliary Benefits**: the emotional and lifestyle payoff. *How they sleep. How they show up at home. What they get to stop worrying about.*

### Step 9: Quality pass
Before delivering the CSV, run this check:
- [ ] Every cell traces back to something said in a transcript, or marked `[unknown]`. Zero invention.
- [ ] No GPT-language (no *"leverage", "unlock", "streamline", "delve"*).
- [ ] Direct quotes appear in at least Rows 3–5. The customer's voice is non-negotiable.
- [ ] Bodacious Claim is not a feature list. If it sounds like a tagline, sharpen it until it sounds like a bet.
- [ ] No two niches have identical content in any row. If they do, you have one niche, not two — merge them.
- [ ] Anonymise: replace personal names with role labels (`Founder 1`, `Head of Sales 2`).

### Step 10: Deliver
- Write the CSV. UTF-8, comma-delimited, double-quoted strings, line-breaks within cells preserved using `\n`.
- Hand back the CSV path plus a one-paragraph summary per niche so the user can scan before opening the file.
- Recommend the next skill to run, based on which downstream asset the user needs first:
  - Landing page → `landing-page-builder.md`
  - Outbound copy → `outbound-copy-manager.md`
  - Sales script → `sales-script-creator.md`
  - Facebook ads → `facebook-ads-from-customer-transcripts.md`

## What a filled cell should look like

Each cell needs to be **specific, transcript-grounded, and customer-voiced.** Generic SaaS marketing language is the failure mode.

Use these structural rules per row, regardless of your industry:

- **Position (Row 1)** — pack 6–9 attributes in: location, team size, revenue or budget band, role, marital + family status, years in role, vertical. Use line breaks for scannability. *"Generic founder"* is not a Position.
- **Deepest Desires (Row 2)** — phrase in their words. *"Get the admin off my desk so I can do the work I trained for"* beats *"achieve operational efficiency."*
- **Up at night / Frustrated / Angry (Rows 3–5)** — three distinct emotional registers. Fear, helplessness, blame. Each row should pass the *"would they underline this if they read it"* test. Use direct quotes from transcripts wherever possible.
- **Tried but failed at (Row 6)** — specific tools, agencies, hires, frameworks by name. Note **why** each failed: cost, speed, fit, accountability, follow-through.
- **Trends + threats / Cost of inaction (Rows 7–8)** — pull from what they themselves named. Note their stated worst case. If they didn't name one, mark it `[unknown — ask in next call]`.
- **Solution / Vehicle (Row 9)** — your product or service, named. Different niches may need different framings of the same product.
- **Bodacious Claim (Row 10)** — one sentence that, if proven, makes the prospect buy today. Maps directly back to Row 2. Should sound like a bet, not a tagline.
- **Secondary Benefits (Row 11)** — quantifiable side-effects. Time saved, cost avoided, errors removed, headcount unneeded.
- **Auxiliary Benefits (Row 12)** — emotional and lifestyle payoff. *How they sleep. How they show up at home. What they stop worrying about.* Often the row that closes the sale.

If your filled CSV reads with this kind of specificity — verbs from the transcript, numbers from real conversations, identity-level language in Row 12 — you are done. If it reads like generic SaaS marketing, go back to the transcripts.

## Worked example — single niche, fully filled (illustrative only)

Below is what one column of the CSV looks like for a fictional `{Your Venture}` selling vertical scheduling + intake software to boutique law firms. **Read it for the structural moves, not the content** — your filled cells must come from your own customer transcripts.

| Field | Niche A — solo & 2-partner family-law firms, US East Coast |
|---|---|
| **Position** | Solo or 2-partner family-law firms · Boston / NYC / DC metro · 1–4 staff · billing $300–600k/yr · married, mid-40s, kids in school · 5–15 years in own practice |
| **Deepest Desires** | "Get the admin off my desk so I can do the law I went to law school for." Status: be the firm clients refer friends to. Security: predictable book without chasing. |
| **Up at night** | Losing the next big retainer to the firm two streets over that has a real intake system. Becoming a one-trick small firm forever. |
| **Frustrated by** | Calendly never syncs to the conflict-check process. Paralegal turnover. The 11pm email triage that never ends. *"I built this firm to escape that life and now I'm doing it again."* |
| **Angry at** | The cost of every legal-tech tool they've bought and abandoned. The bar association's "innovation" CLEs that never address actual workflow. |
| **Tried but failed at** | A generic case-management platform (too big), virtual paralegals (couldn't handle conflicts), a junior associate who left in 8 months, three intake-form tools. |
| **Trends + threats** | Larger firms productising fixed-fee family-law packages. AI intake bots showing up in competitor websites. Younger clients expecting same-day response. |
| **Cost of inaction + time** | Continued 60-hr weeks. Slow but real attrition of high-value clients to better-systematised firms. Window: 12–24 months before the gap is unbridgeable. |
| **Solution / Vehicle** | `{Your Venture}` — vertical intake + scheduling + conflict-check stack purpose-built for solo and 2-partner family-law. |
| **Bodacious Claim** | "Get every new-client inquiry, conflict-checked and on the calendar, before you finish your morning coffee — or we work for free until it does." |
| **Secondary Benefits** | 6+ hours/week back. Zero missed intakes. Paralegal cost down 30–50%. End of the 11pm email run. No more lost-conflict embarrassment. |
| **Auxiliary Benefits** | Sleep through the night. Be home for dinner. Feel like the senior practitioner you are, not the receptionist of your own firm. Stop apologising to your spouse for the laptop at the dinner table. |

### What this column shows you (the structural moves)

- **Row 2 maps to Row 10.** *"Do the law I went to law school for"* → *"every inquiry on the calendar before coffee."* Same idea, expressed two ways.
- **Row 6 names specific failed alternatives.** *"Generic case-management platform, virtual paralegals, junior associate, three intake-form tools."* Not abstract.
- **Row 12 is identity, not features.** *"Sleep through the night. Be home for dinner."* The auxiliary benefits row is often what closes the sale.
- **Direct quotes appear** in Row 4 (`"I built this firm to escape that life..."`). Customer voice is non-negotiable.

If your filled CSV has cells with this kind of specificity — verbs from the transcript, named alternatives, identity-level Row 12 — you're done. If it reads like generic SaaS marketing, go back to the transcripts.

## Anti-patterns (what makes this skill fail)

- **Skipping the cluster step.** If you fill one big column for "all customers," every downstream asset will be vague. The whole point is that copy converts when it speaks to *a niche*, not *the market*.
- **Inventing pain that wasn't said.** Rows 3–5 must come from transcripts. If you fabricate, the asset built on top will sound like everyone else's marketing.
- **Mixing the three emotional rows.** Up-at-night ≠ Frustrated ≠ Angry. Keep them clean.
- **Writing the Bodacious Claim like a tagline.** Tagline = vibe. Bodacious Claim = bet. The customer should think *"that's a big swing — but if it's true, I want it."*
- **Treating Auxiliary Benefits as a throwaway.** Row 12 is often the row that closes the sale. Spend real time on it.

## Frameworks referenced
- **Dan Kennedy** — *Magnetic Marketing*, *No B.S. Direct Marketing for the Ultimate No B.S. Business*. The 12-row structure is a compressed Kennedy long-form sales letter.
- **Robert Cialdini** — *Influence*. Rows 7–8 lean on commitment/consistency and loss aversion.
- **Alex Hormozi** — *$100M Offers*. The Bodacious Claim row owes the "value equation" framing.
- **Jordan Belfort** — *Way of the Wolf*. The emotional separation of fear / frustration / anger comes from the Straight Line.
- **Russell Brunson** — *Expert Secrets*. The Vehicle / Solution row borrows the "new opportunity" framing.

## Tracking the impact

Once the CSV is filled and downstream assets are built from it, log:
- Which asset (landing page, ad, script) used which row most heavily.
- Conversion delta vs. the previous asset built without an Asset Foundation.
- Quote-recognition rate from the prospect ("yes, that's exactly what I'm dealing with") on the next 5 sales calls. If recognition rate is below 70%, the Foundation is wrong — go back to transcripts.

## Notes
This skill is venture-agnostic. It produces an artefact, not a pitch. The artefact is the same shape every time; what differs is the language inside the cells, which must always come from the customer.
