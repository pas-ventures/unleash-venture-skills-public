# Asset Foundation Builder Skill

## Overview
Turn raw customer signal — YouTube transcripts, founder/sales calls, web research, Reddit threads, industry forums, and podcasts — into the **Asset Foundations** every downstream asset depends on: ICP, deepest desires, frustrations, failed attempts, market shifts, the layered benefit stack, and the false beliefs that block conversion.

Built on Dan Kennedy's Sales Letter Framework + Russell Brunson's Three False Beliefs: you cannot write copy that converts until you have done the foundation work. Output is two coupled artefacts:

1. **Asset-Foundations CSV** — 13 rows × N niches, paste-ready into Sheets.
2. **Niche-Brief MD** — narrative companion with hard market stats, jargon (use vs avoid), recognition quotes, where they gather, and suggested hooks.

Both feed downstream skills: landing pages, sales scripts, ads, drip campaigns, prospect lists, LinkedIn outreach, content engines. Every other skill in this repo gets sharper when fed an Asset Foundation produced here.

## When to Run
- **You are entering a new niche** and need the foundation BEFORE writing landing pages, ads, or scripts. Skipping this step means you are guessing what the customer feels — Kennedy: *"Don't write to people. Listen to people, then echo what they already said."*
- **You have call recordings, transcripts, or a list of niche-relevant YouTube videos / podcasts / forum threads.** One well-qualified call works. Five to ten dialled in. Ten to twenty produce a Foundation that compounds. Scraped sources (YouTube, podcasts, forums) are valid signal when founder-call data is thin.
- **Your existing positioning feels generic** and you suspect you are speaking *about* the customer instead of *as* the customer.

## Requirements
- `yt-dlp` — `brew install yt-dlp` (macOS) or `pip install yt-dlp` (any). Used for YouTube transcript scrape.
- `whisper` (OpenAI Whisper) — `pip install openai-whisper` plus `ffmpeg` (`brew install ffmpeg`). Used for podcast transcription when no YouTube version exists.
- `gh` CLI authenticated to your venture org — for fetching reference assets from prior niches.
- A scratch directory with at least 5 GB free for raw corpus storage.

## How to Run

### Step 1 — Configure inputs
1. Create scratch dir: `mkdir -p ~/scratch/asset-foundation/{niche-slug}/{raw,processed,output}` with subdirs `raw/{youtube,calls,web,reddit,forums,podcasts}`.
2. Define inputs in `inputs.yaml` at scratch root: niche name, brand, language, target role, company size, source list (URLs per source type).
3. Verify Requirements installed (`yt-dlp --version`, `whisper --help`, `gh auth status`, `ffmpeg -version`).

### Step 2 — Run source ingestion (Phase 1, up to 6 source types)
For each applicable source type:
- **1a YouTube** — `yt-dlp --write-auto-subs --sub-lang {lang} --skip-download --convert-subs srt -o "raw/youtube/%(channel)s/%(title)s.%(ext)s" {URL}` per channel/video.
- **1b Calls** — drop transcripts in `raw/calls/`. Anonymise customer names.
- **1c Web** — Statista / Destatis / Verbands publications / trade press → save MD notes to `raw/web/`.
- **1d Reddit** — DE/EN subreddits → save thread JSON to `raw/reddit/`.
- **1e Forums** — your niche's industry-specific practitioner forums, Innungs- or verband-Foren, or specialist Subreddit equivalents → save HTML→MD to `raw/forums/`.
- **1f Podcasts** — `yt-dlp -x --audio-format mp3 {URL}` then `whisper {file} --language {lang} --output_format srt --output_dir raw/podcasts/`.

Document which sources were used + which were skipped (with reason) in `processed/source-coverage.md`. Per niche the operator picks which sources yield signal — Reddit is often weak for German trades; forums + podcasts are often gold.

### Step 3 — Pain extraction (Phase 2)
- Read all raw corpus end-to-end. Do not skim.
- Cluster sources into 1–5 niches by pain-language similarity (not demographic similarity).
- Pull verbatim quotes per niche, tag with source + timestamp.

### Step 4 — Produce CSV (Phase 3)
- Fill all 13 rows for each niche.
- Use direct quotes in Rows 3–5.
- Mark unknown cells `[unknown — ask in next call]`. Do not guess.
- Save to `output/asset-foundations-{venture}-{niche-slug}-{YYYY-MM-DD}.csv`.

### Step 5 — STOP. Operator CSV review checkpoint
**DO NOT generate the niche-brief until the CSV has been reviewed and approved.** The brief is downstream of the CSV; both are downstream of source quality. If the CSV has wrong rows, the brief amplifies the error.
- Surface CSV in scannable format (e.g. paste into a GDoc tab).
- Wait for operator approval.
- If rows have wrong content, fix → re-surface → wait again.

### Step 6 — Produce niche-brief MD (Phase 4)
Only after CSV approval:
- Generate brief from approved CSV + raw corpus.
- Save to `output/niche-brief-{niche-slug}-{YYYY-MM-DD}.md`.

### Step 7 — Quality pass
Run the QC checklist (see Quality Pass section below).

### Step 8 — Hand-off
Pass CSV + brief paths to whichever downstream skill the operator needs (landing-page-builder, facebook-ads, sales-script-creator, drip-campaign-builder, prospect-list-builder, linkedin-outreach, content-engine, outbound-copy-manager, outreach-draft-writer, inbound-marketing-playbook).

## Inputs
1. **Niche definition**
   - **Niche name** (e.g. {NICHE} — your specific industry vertical + role + company-size segment, like "boutique law firms" or "small property-management businesses")
   - **Target role** (Inhaber, Geschäftsführer, Meister, Bezirksinhaber, Founder, Head of Sales)
   - **Company size** (solo, 2–5, 5–15, 15–50 employees)
   - **Product/service** this research is for ({BRAND})
   - **Language** ({LANGUAGE} — DE / EN / both)
2. **Source list** — at least one of:
   - YouTube channels / videos
   - Founder / sales call transcripts
   - Web sources (Statista, Destatis, Verbands publications, trade press)
   - Reddit subreddits
   - Industry forums
   - Podcasts
3. **Qualification question set** (optional) — if you don't have one, the skill drafts one from BANT / MEDDIC / The Mom Test and surfaces it for review.
4. **Niche hypothesis (optional)** — if you already suspect 3–5 distinct buyer segments, name them. Otherwise the skill clusters the sources and proposes niches.

## Output

### Output 1 — Asset-Foundations CSV (13 rows)

| Field | Niche 1 | Niche 2 | … |
|---|---|---|---|
| **Position** (Location, income, team size, budget, vertical, job title, marital, family, years in role) + **Disqualifiers** (roles/sizes/geos/situations that look like fit but aren't) | | | |
| Deepest Desires of your prospect | | | |
| What keeps them up at night, eyes wide open, glaring at the ceiling? | | | |
| What are they frustrated by? Why? How are they feeling? | | | |
| What are they angry at? Why? | | | |
| What have they tried but have failed at? | | | |
| What trends are happening in the market? How will this negatively affect them if they don't adapt? | | | |
| What will happen if they don't make a change? **EUR/month baseline** + time horizon (e.g. "12h/wk × 60 EUR/hr × 4 wk = 2,880 EUR/mo leaking into Bürokratie. Window: 12–24 mo before unbridgeable.") | | | |
| Solution / Vehicle | | | |
| Bodacious Claim (the audacious promise that maps to Row 2) | | | |
| Secondary Benefits (quantifiable side-effects: time, money, errors, headcount) | | | |
| Auxiliary Benefits (emotional payoff: how they feel, how they sleep, family/status impact) | | | |
| **3 False Beliefs (Brunson)** — Vehicle ("X solution doesn't work for our industry") · Internal ("I can't do this — I'm not technical enough") · External ("It won't work for me — my team won't adopt it / my customers want analog") | | | |

Save as `asset-foundations-{venture}-{niche-slug}-{YYYY-MM-DD}.csv`. UTF-8, comma-delimited, double-quoted strings, line-breaks within cells preserved using `\n`.

### Output 2 — Niche-Brief MD (narrative companion)

```markdown
# Niche Brief: {Niche Name}

**Date:** {YYYY-MM-DD}
**Market:** {X} Betriebe in DE / {X} businesses in target market
**Entscheider:** {role}
**Ansprache:** {Du/Sie / first-name vs formal}
**Trend:** {growing/shrinking/consolidating}
**Sources used:** {YouTube ✅ · Web ✅ · Reddit ⚠ thin · Forums ✅ · Podcasts ✅ · Calls ❌ none yet}

## Top 5 Pains
For each pain, all five sub-bullets:
1. **{Pain name}**
   - **Stat / number:** {%, hours, count} — {study, year}
   - **Money impact:** {EUR/month or hours/week with calculation}
   - **Source:** {URL + access date}
   - **Recognition quote:** "{verbatim line, native language}" — {source + timestamp}
2. ... (repeat structure)

## Money Left on Table
- {Specific revenue opportunity they're missing, with numbers}

## Industry Jargon

### Use (their words — copy verbatim into ads/copy)
- Client term: {what they call customers}
- Process names: {list}
- Tool names they use: {list — Haufe PowerHaus, TopKontor, etc.}
- Daily-grind language: {how they describe their work — Baustelle, Dach, Objekt, Bezirk}

### Avoid (outsider words that flag you as a stranger)
- Generic SaaS terms: {synergy, leverage, ecosystem, streamline, unlock}
- Adjacent-industry terms that don't fit: {list}
- Anglicisms when DE niche prefers German: {list — "Workflow" → "Ablauf", etc.}

## Emotional Core
- Started because: {motivation — Freiheit, Handwerk, eigener Chef}
- Frustrated by: {what kills their joy — Bürokratie statt Kernarbeit}
- Dream day: {what they wish work looked like}
- Identity quote: "{verbatim}" — {source + timestamp}

## Competitive Landscape
- Current solutions: {list}
- Why they hate them: {zu komplex, zu teuer, US-Cloud, fits-nobody}
- Gap: {what's missing}

## Where They Gather
- **LinkedIn groups:** {list with member counts where available}
- **Industry events / Messen:** {list with dates, recurrence, audience size}
- **Podcasts they listen to:** {list}
- **Trade publications:** {list}
- **Online forums / communities:** {list with URLs}
- **Service providers serving them:** {accountants, lawyers, software vendors — sources of warm intros}

## Suggested Hooks
- **Stat hook:** "{number} — {pain}"
- **Question hook:** "Wie lösen Sie {pain}?" / "How are you solving {pain}?"
- **Peer hook:** "Andere {niche} in Ihrer Region…" / "Other {niche} owners…"
- **Provocation hook:** "{X}% Ihrer Zeit geht für {pain} drauf"
- **Recognition-quote hook:** lift one of the verbatim Top-5-Pain quotes directly

## Sources
- {URL or publication} — {data point}
- {YouTube URL + timestamp} — {direct quote}
- {Forum thread URL} — {pain dimension}
- {Podcast episode + timestamp} — {quote}
```

Save as `niche-brief-{niche-slug}-{YYYY-MM-DD}.md`.

## Methodology (Kennedy 12-row spine + Brunson Row 13)

The 13 fields are not arbitrary. Rows 1–12 mirror the spine of a Kennedy long-form sales letter; Row 13 borrows Brunson's *Expert Secrets* false-belief teardown.

1. **Position + Disqualifiers** — the prospect must recognise themselves in the first sentence. Specificity (location, role, family status, years in position) signals you understand their world. Generic ICPs ("SMB founder") never trigger recognition. Disqualifiers are equally important: prospect-list-builder needs an explicit exclude list, not just an include list.
2. **Deepest Desires** — Kennedy: *"Enter the conversation already happening in their head."* Desire is the engine; everything else amplifies or unblocks it.
3–5. **Up-at-night / Frustrated / Angry** — the emotional layer. Each is distinct: fear (up-at-night), helplessness (frustrated), blame (angry). Skip one and the copy reads flat.
6. **Tried but failed at** — eliminates the alternatives in the prospect's mind before you pitch yours. Kennedy's "false-solutions audit."
7. **Trends + threats** — gives urgency without being apocalyptic. Connects the prospect's problem to a wider, observable shift.
8. **Cost of inaction (EUR/month) + time horizon** — the close-the-loop on urgency. Without a concrete EUR number AND a deadline, urgency dissolves. If sources don't yield a EUR figure, calculate it (hours × hourly rate) and mark the assumption.
9. **Solution / Vehicle** — only NOW does your product enter. The first 8 rows earn the right to mention it.
10. **Bodacious Claim** — Kennedy's term. The single audacious promise that maps directly onto Row 2 (Deepest Desires). Not a tagline. Not a feature. The thing that, if true, makes them buy.
11. **Secondary Benefits** — measurable side-effects. Time saved, frustrations eliminated, cognitive load removed. Quantify wherever possible.
12. **Auxiliary Benefits** — the emotional payoff. How they *feel* after the transformation. How their family, team, or status is affected.
13. **3 False Beliefs (Brunson)** — every prospect carries three objections that block the buy:
    - **Vehicle:** "Your *type* of solution doesn't work for my industry" (e.g. "AI assistants for trades don't understand our jargon").
    - **Internal:** "Even if it works for others, I can't do this" (e.g. "I'm not technical enough to use software").
    - **External:** "Even if I could, my situation makes it impossible" (e.g. "My team won't adopt it" / "My customers want analog").
    Drip-campaign-builder Email 3–5 (destroy false beliefs sequence) and content-engine "destroy false beliefs" content type both stall without this row.

Skip layers and the asset built on top will leak conversion. Do all thirteen and the landing page, sales script, and ad copy almost write themselves.

## Step-by-Step Procedure

### PHASE 1 — Source Ingestion (5+1 source types canvas)

The skill canvas lists six source types. Per niche the operator picks which yield signal — not all six apply to every niche. Reddit is often weak for German trades; forums + podcasts are often gold for B2B/trade niches. Document which sources were used + skipped (with reason) in `processed/source-coverage.md`.

#### 1a. YouTube (auto-subs via yt-dlp)

When the niche has rich YouTube content (Meister channels, Innung talks, trade-show recordings, coach interviews), this is often the fastest way to build signal volume.

```bash
# Per video — auto-subs in target language, no audio download
yt-dlp --write-auto-subs --sub-lang {LANG_CODE} --skip-download \
       --convert-subs srt -o "raw/youtube/%(channel)s/%(title)s.%(ext)s" "{VIDEO_URL}"

# Per channel — last N videos
yt-dlp --write-auto-subs --sub-lang {LANG_CODE} --skip-download \
       --convert-subs srt --playlist-end {N} \
       -o "raw/youtube/%(channel)s/%(upload_date)s_%(title)s.%(ext)s" "{CHANNEL_URL}"
```

For German niches use `--sub-lang de`. For English `--sub-lang en`. Auto-subs are imperfect but adequate for pain-mining (verbatim phrases survive transcription noise).

**Cleanup:**
1. Strip SRT timestamps but keep them as `[12:34]` anchors so direct quotes can be sourced back to the original video.
2. Concatenate all transcripts per channel into one file: `{channel}-corpus.txt`.
3. Drop intro/outro boilerplate, sponsor reads, and content that's not niche-relevant.
4. If auto-subs are unreadable for a high-value video, fall back to manual whisper transcription.

**Source-quality bar:**
- Min 8–10 videos, 30+ min each, watched-by-the-ICP (channel demographics matter — a Meister-channel or coach-interview channel matters more than a generic news channel).
- Mix: how-to / business-side / customer-complaints / trade-show panels / coach interviews.
- Avoid: corporate brand channels (sanitised language), news segments (journalist voice, not practitioner voice), DIY-tutorial channels aimed at consumers (wrong audience).

#### 1b. Founder / Sales Call Transcripts

If discovery / sales / customer-interview transcripts exist, they outweigh scraped sources on every dimension — direct named pains, real budget signals, observed buying behaviour. Use them as primary signal; scraped sources fill the gap when call volume is thin.

- Read every transcript end-to-end. Do not skim.
- Anonymise customer names before feeding if output will be shared.
- Tag each speaker by: industry vertical, company size, role, geography, apparent buying urgency.

#### 1c. Web Research

Search for each of these data points to anchor the niche-brief stats:

**Market size**
- Total businesses in target market (Statistisches Bundesamt for DE, ZDH for Handwerk, BFB for Freie Berufe, your industry's verband or trade-association for other markets).
- Trend: growing, shrinking, consolidating?
- Key stat: "X Betriebe in DE" / "X businesses in {market}".

**Top 5 pains with hard numbers** — search queries to try:
- `"{niche} größte Herausforderungen" site:handwerksblatt.de OR site:iww.de`
- `"{niche} Probleme Digitalisierung"`
- `"{niche} Fachkräftemangel Studie"`
- `"{niche} Zeitaufwand Bürokratie Statistik"`

For each pain: percentage or hours, money impact, source (study name, publication, year).

**Industry jargon** (split Use vs Avoid — see Output 2 template).

**Competitive landscape** — what solutions exist, what they hate, what they've tried and abandoned.

**Where they gather** — LinkedIn groups, events / Messen, podcasts they listen to, trade publications, forums, service providers (accountants, lawyers, software vendors who can warm-intro).

#### 1d. Reddit

DE/EN subreddits relevant to the niche. Search queries:
- `site:reddit.com "{niche}" Probleme`
- `site:reddit.com r/{Trade} OR r/Selbststaendig OR r/{Vertical}`
- Filter for threads with >10 replies for verbatim language density.

For some niches (German trades) Reddit pain density is verifiably weak. Document this in source-coverage.md and move on — don't burn time forcing thin signal.

#### 1e. Industry Forums

Niche-specific forums often outperform Reddit for B2B/trade niches:
- Trades: practitioner forums and Innungs-Foren for your specific Gewerk.
- Professional services: industry-association communities, member-only forums, and verband publication archives.
- Mine the long threads (>20 replies) for verbatim Selbstständigkeit / Personal / Pricing pain.

#### 1f. Podcasts (Whisper-transcribe)

When a podcast doesn't publish a YouTube version, audio-extract + whisper-transcribe:

```bash
yt-dlp -x --audio-format mp3 -o "raw/podcasts/%(title)s.%(ext)s" "{PODCAST_EPISODE_URL}"
whisper raw/podcasts/{file}.mp3 --language {lang} --output_format srt --output_dir raw/podcasts/
```

German Handwerker podcasts (e.g. Mosler Workers Cast, MISSION STARKES HANDWERK, E-Show) hold the densest practitioner-pain talk that survives outside YouTube's politeness filter.

### PHASE 2 — Pain Extraction & Niche Clustering

#### Step 2.1: Cluster sources into niches
- Group sources where the **language** of the pain matches, not just the demographic. A 10-person agency CEO and a 50-person SaaS founder may live in the same niche if they describe their pain identically.
- Propose 3–5 niches. Name each by their most defining trait (role + vertical + size — e.g. *"Mid-market manufacturing CEO, 50–250 staff, DACH"*).
- Flag any single source that doesn't fit a cluster — these are either a sixth niche or a misqualified prospect. Surface to the user.

#### Step 2.2: Extract verbatim pain language
- For each niche, pull direct quotes covering: fear, frustration, anger, failed attempts, market shifts, identity statements, and the three false beliefs.
- Tag each quote with source + timestamp/line so it's traceable back.
- This pool feeds Rows 3–6 + Row 13 of the CSV directly, and the recognition quotes in the niche-brief Top 5 Pains.

### PHASE 3 — Kennedy 13-Row CSV Synthesis

#### Step 3.1: Fill Row 1 (Position + Disqualifiers) verbatim
- Pull every demographic detail mentioned: location, team size, revenue band if disclosed, job title, marital status, family status, years in role, vertical, budget signals.
- Add a Disqualifiers sub-bullet listing who NOT to target: roles that look like fit but aren't, company sizes that disqualify, geos that disqualify, tech stacks / situations that disqualify.
- Write in compact form. Use line breaks inside cells so each attribute is scannable.
- If a detail is missing across all sources in a niche, mark it `[unknown — ask in next call]`. Do not guess.

**Critical disambiguation rule for service businesses:**

If the niche has multiple worker categories (white-collar admin vs field operatives, partners vs associates, full-time vs contractor, etc.), the Position row MUST specify which category the headcount metric refers to.

Example formulations:
- *"2-50 white-collar / admin staff (NOT field operatives)"* — for cleaning, security, landscaping, logistics, facilities
- *"2-15 partners (NOT associates or paralegals)"* — for law firms, accounting, consulting
- *"Founder + 1-3 full-time eng (NOT contractors)"* — for early-stage SaaS / agencies
- *"2-25 Innendienst-Mitarbeiter (NICHT Außendienst / Field-Operatives)"* — DE equivalent for service-firms with field/back-office split

Disqualifiers must be explicit: *"Companies with admin headcount above the upper bound, even if total headcount fits, are excluded."*

Why this matters: marketing assets target the BUYER, not the workforce. Misaligned headcount metrics break ICP filtering in `prospect-list-builder` and ad targeting in `facebook-ads-from-customer-transcripts`. A 50-cleaner / 5-admin firm and a 5-cleaner / 50-admin firm are different prospects despite the same total headcount.

#### Step 3.2: Fill Row 2 (Deepest Desires)
- Listen for *aspirations* — what they say they want, what they envy, what status object they reference, what they would do "if I had this nailed."
- Phrase in their words, not yours. *"Get business to the next level"* beats *"achieve scalable growth."*
- Look for what they want to **be**, not just what they want to **do**. Status, recognition, security, peace of mind.

#### Step 3.3: Fill Rows 3–5 (Up-at-night / Frustrated / Angry)
- Three distinct emotional registers — keep them separate.
  - **Up at night** = fear of loss, the catastrophe scenario.
  - **Frustrated** = helplessness, things-aren't-moving.
  - **Angry** = blame, betrayal, things-are-actively-wrong.
- Each row should pass the *"would the prospect underline this if they read it"* test.
- Use direct quotes from sources wherever possible. Mark them with quotation marks in the cell. Include source tag (e.g. `[YouTube: Channel @ 12:34]` or `[Forum: industry-forum-name thread X]`).

#### Step 3.4: Fill Row 6 (Tried but failed at)
- List specific tools, agencies, hires, frameworks, channels they have already tried.
- Note **why** each failed — usually one of: too expensive, too slow, didn't understand the niche, lacked accountability, founder didn't follow through.
- This row is the source for your *"why this is different"* messaging later.

#### Step 3.5: Fill Rows 7–8 (Trends + Cost of inaction)
- **Trends**: which shifts in their market are observable and accelerating? Pull from what they themselves named, anchored against the web/Verbands stats from Phase 1c.
- **Cost of inaction**: BOTH a concrete EUR/month baseline AND a time horizon. If sources don't yield a EUR figure, calculate it (hours × effective hourly rate) and mark the assumption explicitly.

#### Step 3.6: Operator Voice Injection (BEFORE finalizing emotional rows)

Before locking Rows 2–5, 12, 13 (the emotional + identity rows), surface this prompt to the operator:

> *"I've drafted these rows from the source corpus. Before I finalize: do you have practitioner verbatim from your own conversations, coaching sessions, customer calls, or operator network that should anchor the recognition-quote in any of these rows?*
>
> *Even 2–3 verbatim lines from a real practitioner in this niche lifts the foundation from 'good research' to 'magnetic recognition'. The downstream landing pages, ads, and scripts will inherit this voice — and operators tell us this is the single biggest quality lift we make."*

**If the operator provides verbatim:**
- Insert into Row 4 (Frustrated by) / Row 5 (Angry at) / Row 12 (Auxiliary Benefits) / Row 13 (False Beliefs) where it fits the emotional register.
- Tag with `[Operator voice {YYYY-MM-DD}; verify against future transcripts]`.
- Echo the same lines into the niche-brief's Emotional Core section + Top-5-Pains recognition-quote slots.

**If the operator declines or has none yet:**
- Use synthesized voice from the source corpus (forum / podcast / YouTube quotes — never invent).
- Mark the affected cells `[needs operator validation]` so the operator knows where to come back when they have real verbatim.
- Surface this list in the delivery summary at the end of Phase 4.

**Why this is its own step:** real-world battle-tests across multiple niches show that operator-injected verbatim is the single biggest quality multiplier. Synthetic voice is workable; real practitioner voice is magnetic. This step is the difference between "research" and "resonance".

#### Step 3.7: Fill Row 9 (Solution / Vehicle)
- Your product or service, named precisely.
- If different niches require different framing of the same product, write the framing per niche, not just the name.

#### Step 3.8: Fill Rows 10–12 (Bodacious Claim + Secondary + Auxiliary Benefits)
- **Bodacious Claim**: one sentence that, if proven, makes the prospect buy today. Map directly back to Row 2 (Deepest Desires). Numbers help; specificity helps more.
- **Secondary Benefits**: enumerate every quantifiable side-effect. Time saved, money saved, headcount avoided, errors reduced.
- **Auxiliary Benefits**: the emotional and lifestyle payoff. *How they sleep. How they show up at home. What they get to stop worrying about.*

#### Step 3.9: Fill Row 13 (3 False Beliefs)
- **Vehicle false belief** — what they believe about your category/solution-type that's wrong. Quote them: "Solutions like that don't work for {industry/situation}…"
- **Internal false belief** — what they believe about themselves that blocks adoption. Quote: "I'm not the kind of person who…" / "I could never…"
- **External false belief** — what they believe about their context that blocks adoption. Quote: "Even if I tried, my {team/customers/regulators/spouse} would…"
- Each must come from sources, not invention. If a source doesn't surface a false belief, mark `[unknown — surface in next call by asking 'what's the one thing that almost stopped you?']`.

### PHASE 3.5 — STOP. Operator CSV Review Checkpoint

**DO NOT generate the niche-brief until the CSV has been reviewed and approved.** The brief synthesises from the CSV; if the CSV has wrong rows, the brief amplifies the error. CSV review must happen first.

- Surface CSV in scannable format (e.g. paste into a GDoc tab).
- Wait for operator approval before continuing.
- If rows have wrong content, fix → re-surface → wait again.

### PHASE 4 — Niche-Brief MD Synthesis (post-approval)

Only after CSV approval, generate the niche-brief MD using the template in Output 2 above. Specifically:

- **Top 5 Pains** — five sub-bullets each (pain name, stat, money impact, source, recognition quote). The recognition quote is the "yes that's exactly me" verbatim line that ad/landing-page hooks borrow directly.
- **Industry Jargon** — split into Use vs Avoid lists. The Avoid list is non-negotiable: facebook-ads-from-customer-transcripts has explicit "do not use" requirement.
- **Where They Gather** — LinkedIn groups, events, podcasts, publications, forums, service providers. Feeds prospect-list-builder Dream 100 + linkedin-outreach Unity hooks.
- **Sources** — every claim cited.

### PHASE 4 — Quality Pass

Before delivering, run this checklist:
- [ ] Every CSV cell traces back to something said in a source, or marked `[unknown]`. Zero invention.
- [ ] No GPT-language (no *"leverage", "unlock", "streamline", "delve"*).
- [ ] Direct quotes appear in at least Rows 3–5 + Row 13, with source tags. The customer's voice is non-negotiable.
- [ ] Bodacious Claim is not a feature list. If it sounds like a tagline, sharpen it until it sounds like a bet.
- [ ] No two niches have identical content in any row. If they do, you have one niche, not two — merge them.
- [ ] Row 8 has BOTH a EUR/month figure AND a time horizon.
- [ ] Row 13 has all three false-belief types filled (Vehicle / Internal / External), each with a source-tagged quote.
- [ ] Niche-brief Top 5 Pains: every pain has a recognition quote with source + timestamp.
- [ ] Niche-brief Jargon split into Use + Avoid lists.
- [ ] Niche-brief Where They Gather populated with at least 3 categories.
- [ ] Market size sourced (not guessed), industry jargon verified (not generic business terms), Ansprache confirmed (Du vs Sie — *Sie* for formal industries: Steuerberater, Ärzte, Anwälte, professional-services firms; *Du* for trades and informal: Handwerker, Gastro, Fitness; for non-DE niches, document the equivalent register choice).
- [ ] Anonymise: replace personal names with role labels (`Founder 1`, `Head of Sales 2`).

### Step 4.2: Deliver
- Write the CSV. UTF-8, comma-delimited, double-quoted strings, line-breaks within cells preserved using `\n`.
- Write the niche-brief MD alongside.
- Hand back both file paths plus a one-paragraph summary per niche so the user can scan before opening the files.
- Recommend the next skill to run, based on which downstream asset the user needs first:
  - Landing page → `landing-page-builder.md`
  - Outbound copy → `outbound-copy-manager.md`
  - Sales script → `sales-script-creator.md`
  - Facebook ads → `facebook-ads-from-customer-transcripts.md`
  - Drip campaign → `drip-campaign-builder.md`
  - Prospect list → `prospect-list-builder.md`
  - LinkedIn outreach → `linkedin-outreach.md`
  - Content engine → `content-engine.md`

## What a filled cell should look like

Each cell needs to be **specific, source-grounded, and customer-voiced.** Generic SaaS marketing language is the failure mode.

Use these structural rules per row:

- **Position + Disqualifiers (Row 1)** — pack 6–9 attributes in: location, team size, revenue or budget band, role, marital + family status, years in role, vertical. List Disqualifiers as a separate sub-bullet. Use line breaks for scannability. *"Generic founder"* is not a Position.
- **Deepest Desires (Row 2)** — phrase in their words. *"Get the admin off my desk so I can do the work I trained for"* beats *"achieve operational efficiency."*
- **Up at night / Frustrated / Angry (Rows 3–5)** — three distinct emotional registers. Fear, helplessness, blame. Each row should pass the *"would they underline this if they read it"* test. Use direct quotes from sources wherever possible, with tags.
- **Tried but failed at (Row 6)** — specific tools, agencies, hires, frameworks by name. Note **why** each failed: cost, speed, fit, accountability, follow-through.
- **Trends + threats / Cost of inaction (Rows 7–8)** — pull from what they themselves named. Row 8 needs EUR/month + time horizon together.
- **Solution / Vehicle (Row 9)** — your product or service, named. Different niches may need different framings of the same product.
- **Bodacious Claim (Row 10)** — one sentence that, if proven, makes the prospect buy today. Maps directly back to Row 2. Should sound like a bet, not a tagline.
- **Secondary Benefits (Row 11)** — quantifiable side-effects. Time saved, cost avoided, errors removed, headcount unneeded.
- **Auxiliary Benefits (Row 12)** — emotional and lifestyle payoff. *How they sleep. How they show up at home. What they stop worrying about.* Often the row that closes the sale.
- **3 False Beliefs (Row 13)** — three quotes (Vehicle / Internal / External). Each must come from sources. If absent, ask explicitly on next call.

If your filled CSV reads with this kind of specificity — verbs from the source, numbers from real conversations, identity-level language in Row 12, and named objections in Row 13 — you are done. If it reads like generic SaaS marketing, go back to the sources.

## Worked example — single niche, fully filled (illustrative only)

Below is what one column of the CSV looks like for a fictional `{Your Venture}` selling vertical scheduling + intake software to boutique law firms. **Read it for the structural moves, not the content** — your filled cells must come from your own sources.

| Field | Niche A — solo & 2-partner family-law firms, US East Coast |
|---|---|
| **Position + Disqualifiers** | Solo or 2-partner family-law firms · Boston / NYC / DC metro · 1–4 staff · billing $300–600k/yr · married, mid-40s, kids in school · 5–15 years in own practice · **Disqualifiers:** firms with >5 attorneys (different ops); litigation-only without intake volume; firms outside metro (different referral dynamics); already on a vertical-stack like Clio Grow |
| **Deepest Desires** | "Get the admin off my desk so I can do the law I went to law school for." Status: be the firm clients refer friends to. Security: predictable book without chasing. |
| **Up at night** | Losing the next big retainer to the firm two streets over that has a real intake system. Becoming a one-trick small firm forever. |
| **Frustrated by** | Calendly never syncs to the conflict-check process. Paralegal turnover. The 11pm email triage that never ends. *"I built this firm to escape that life and now I'm doing it again."* |
| **Angry at** | The cost of every legal-tech tool they've bought and abandoned. The bar association's "innovation" CLEs that never address actual workflow. |
| **Tried but failed at** | A generic case-management platform (too big), virtual paralegals (couldn't handle conflicts), a junior associate who left in 8 months, three intake-form tools. |
| **Trends + threats** | Larger firms productising fixed-fee family-law packages. AI intake bots showing up in competitor websites. Younger clients expecting same-day response. |
| **Cost of inaction (EUR/mo) + time** | ~12 hrs/wk of after-hours admin × $150 effective hourly = $7,200/mo of partner-time leaking into intake. Lost-retainer attrition: 1 high-value client/quarter @ $25k = $8,300/mo. **Total: ~$15,500/mo.** Window: 12–24 mo before the gap to systematised firms is unbridgeable. |
| **Solution / Vehicle** | `{Your Venture}` — vertical intake + scheduling + conflict-check stack purpose-built for solo and 2-partner family-law. |
| **Bodacious Claim** | "Get every new-client inquiry, conflict-checked and on the calendar, before you finish your morning coffee — or we work for free until it does." |
| **Secondary Benefits** | 6+ hours/week back. Zero missed intakes. Paralegal cost down 30–50%. End of the 11pm email run. No more lost-conflict embarrassment. |
| **Auxiliary Benefits** | Sleep through the night. Be home for dinner. Feel like the senior practitioner you are, not the receptionist of your own firm. Stop apologising to your spouse for the laptop at the dinner table. |
| **3 False Beliefs (Brunson)** | **Vehicle:** *"Legal-tech tools never fit family-law specifically — they're built for litigation or estate planning."* **Internal:** *"I'm not a tech person — I'd spend more hours setting it up than it'd save me."* **External:** *"Even if I love it, my paralegal won't adopt it — and clients my age expect to call my office, not fill in a form."* |

### What this column shows you (the structural moves)
- **Row 2 maps to Row 10.** *"Do the law I went to law school for"* → *"every inquiry on the calendar before coffee."* Same idea, expressed two ways.
- **Row 6 names specific failed alternatives.** *"Generic case-management platform, virtual paralegals, junior associate, three intake-form tools."* Not abstract.
- **Row 8 has a real number.** *"$15,500/mo"* — calculated from the pains, not vibes. Sales-script and drip Email 6 ROI maths now have a concrete anchor.
- **Row 12 is identity, not features.** *"Sleep through the night. Be home for dinner."* The auxiliary benefits row is often what closes the sale.
- **Row 13 names the three objections that block conversion.** Drip Email 3 destroys the Vehicle belief; Email 4 the Internal; Email 5 the External. Without this row, you're guessing which objection to address first.
- **Direct quotes appear** in Rows 4 and 13. Customer voice is non-negotiable.

## Anti-patterns (what makes this skill fail)

- **Skipping the cluster step.** If you fill one big column for "all customers," every downstream asset will be vague. The whole point is that copy converts when it speaks to *a niche*, not *the market*.
- **Inventing pain that wasn't said.** Rows 3–5 + Row 13 must come from sources. If you fabricate, the asset built on top will sound like everyone else's marketing.
- **Mixing the three emotional rows.** Up-at-night ≠ Frustrated ≠ Angry. Keep them clean.
- **Writing the Bodacious Claim like a tagline.** Tagline = vibe. Bodacious Claim = bet. The customer should think *"that's a big swing — but if it's true, I want it."*
- **Treating Auxiliary Benefits as a throwaway.** Row 12 is often the row that closes the sale. Spend real time on it.
- **Skipping Row 13.** Drip-campaign-builder + content-engine both consume false-belief rows. Without them, both skills produce generic content.
- **Skipping the CSV review checkpoint.** Generating the brief before the CSV is approved bakes errors into both artefacts. The checkpoint is non-negotiable.
- **YouTube-only without verifying viewership match.** A channel ABOUT the trade isn't always WATCHED BY the trade. Cross-check at least one channel against forum/Reddit references from actual practitioners.
- **DIY-tutorial channels treated as practitioner-pain sources.** Tutorial channels show *how* to do the work for consumer audiences. They rarely surface what practitioners hate about *running the business*. Filter for coach-interview / Geschäftsführer / podcast-interview formats instead.
- **Translating instead of voicing.** For German niches, do not write the CSV in English and translate. The German must be drafted in German, in the native register (Du/Sie), with native idioms — translation kills voice.
- **Forcing thin-signal sources.** If Reddit yields nothing for a German trade after 30 minutes of searching, skip and document. Don't spend hours forcing low-density signal.

## Frameworks referenced
- **Dan Kennedy** — *Magnetic Marketing*, *No B.S. Direct Marketing*. The 12-row Kennedy spine.
- **Russell Brunson** — *Expert Secrets*. Row 13 (Three False Beliefs) + the Vehicle / Internal / External taxonomy.
- **Robert Cialdini** — *Influence*. Rows 7–8 lean on commitment/consistency and loss aversion.
- **Alex Hormozi** — *$100M Offers*. The Bodacious Claim row owes the "value equation" framing.
- **Jordan Belfort** — *Way of the Wolf*. The emotional separation of fear / frustration / anger comes from the Straight Line.
- **Noah Kagan** — *Million Dollar Weekend*. Validation-first: every input source is a datapoint, even when nobody buys.

## Tracking the impact

Once the CSV + brief are filled and downstream assets are built from them, log:
- Which asset (landing page, ad, script) used which row most heavily.
- Conversion delta vs. the previous asset built without an Asset Foundation.
- Quote-recognition rate from the prospect ("yes, that's exactly what I'm dealing with") on the next 5 sales calls. If recognition rate is below 70%, the Foundation is wrong — go back to sources.
- False-belief hit-rate: did Row 13 predict the actual objection that came up on the call? If Row 13 missed, surface the new objection and update.

## Hand-off — what flows downstream

This is the source skill in the GTM stack. Every other skill in this repo expects the Asset Foundation CSV + niche-brief MD as upstream input.

| Asset Foundation Row / Brief Section | Where it flows downstream |
|---|---|
| Row 1 — Position + Disqualifiers | `landing-page-builder` hero context · `outbound-copy-manager` opener line · `prospect-list-builder` ICP filters + exclude list · `sales-script-creator` qualification |
| Row 2 — Deepest Desires | `landing-page-builder` headline · `facebook-ads-from-customer-transcripts` hooks · `content-engine` aspirational angles |
| Rows 3–5 — Up-at-night / Frustrated / Angry | `landing-page-builder` pain story · `outbound-copy-manager` Email 1 problem statement · `outreach-draft-writer` DM hooks · `facebook-ads` problem-led hooks |
| Row 6 — Tried but failed at | `landing-page-builder` "why this is different" · `outbound-copy-manager` objection handling · `sales-script-creator` competitor section |
| Rows 7–8 — Trends + Cost of inaction (EUR/mo) | `drip-campaign-builder` urgency emails + Email 6 ROI maths · `sales-script-creator` pricing anchor · `content-engine` market-shift commentary |
| Row 9 — Solution / Vehicle | `landing-page-builder` offer block · `sales-script-creator` pitch · all skills' "what we do" framing |
| Row 10 — Bodacious Claim | `landing-page-builder` headline · `facebook-ads` primary hook · `outbound-copy-manager` opener |
| Rows 11–12 — Secondary + Auxiliary Benefits | `landing-page-builder` benefit cards · `drip-campaign-builder` nurture stories · `facebook-ads` body · `content-engine` auxiliary-benefits content type |
| **Row 13 — 3 False Beliefs** | `drip-campaign-builder` Email 3-5 (destroy false beliefs sequence) · `content-engine` "destroy false beliefs" content type · `sales-script-creator` objection-handling section |
| Niche-brief: Top 5 Pains stats | `landing-page-builder` proof block · `facebook-ads` stat-hooks · `content-engine` data-led posts |
| Niche-brief: Industry Jargon **(Use list)** | All skills — keeps copy in-language so it doesn't read like outsider marketing |
| Niche-brief: Industry Jargon **(Avoid list)** | `facebook-ads` "do not use" list · `outbound-copy-manager` anti-pattern check · all skills' QC |
| Niche-brief: Recognition quotes | `facebook-ads` hooks · `landing-page-builder` testimonial-style headlines · `outbound-copy-manager` first-line · `linkedin-outreach` openers |
| Niche-brief: **Where They Gather** | `prospect-list-builder` Dream 100 · `linkedin-outreach` Unity hooks · `outbound-copy-manager` opener variations · `content-engine` distribution channel choice |
| Niche-brief: Suggested Hooks | `facebook-ads` ad variants · `outbound-copy-manager` subject lines · `linkedin-outreach` openers |

> **Note (2026-05-08):** `content-engine`'s `target-group-foundations.md` is now deprecated. The niche-brief MD output of this skill replaces it. Update `content-engine` to consume `niche-brief-{slug}-{date}.md` directly.

Run this skill once per niche. Re-run it quarterly as your sources pile up — the Foundation compounds.

## Notes
This skill is venture-agnostic. It produces an artefact, not a pitch. The artefact is the same shape every time; what differs is the language inside the cells, which must always come from the customer.

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
