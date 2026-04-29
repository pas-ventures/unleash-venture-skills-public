# Prospect List Builder Skill

## When to Use
- "Build me a prospect list for [venture]"
- "Find 100 high-fit prospects for [ICP description]"
- "Set up Sales Navigator searches for [audience]"
- "Run the Dream 100 for [venture/product]"
- "Who should we be targeting for [offer]?"
- "Enrich and score this raw prospect list"
- "Help me identify warm paths into [target company/person]"
- Before launching any outbound campaign, cold email sequence, or ABM play

## Overview
Systematic identification, enrichment, and scoring of high-value prospects for any founder-led business. Takes ICP criteria as input, produces a prioritized, enriched prospect list with outreach recommendations as output.

The skill has 5 core capabilities:
1. **ICP Definition & Validation** — Sharpen the Ideal Customer Profile using Hormozi's Grand Slam Market framework (massive pain, purchasing power, easy to target, growing market). Reject weak ICPs before wasting time on list-building.
2. **Systematic Search Construction** — Build LinkedIn Sales Navigator saved searches with specific filter combinations, plus secondary source searches (events, communities, publications, public databases).
3. **Export & Clean** — Extract raw prospect data using Evaboot (Sales Navigator CSV export) and PhantomBuster (scrape post engagers, group members, event attendees, company employees). Clean and deduplicate.
4. **Enrichment & Scoring** — 2 minutes per prospect: what did they build/exit, mutual connections, recent posts, network overlap, timing signals. Score by fit, warmth, and timing.
5. **Dream 100 Mapping** — Russell Brunson's Dream 100: identify 100 places where prospects congregate (influencers, podcasts, events, communities, service providers) and systematically infiltrate them.

This skill is venture-agnostic. It works for any founder-led business where outbound or relationship-driven sales matter. The Configuration Template below uses `{PLACEHOLDER}` syntax — fill in your own values.

## Core Frameworks (Always Apply)

### Alex Hormozi — $100M Leads: Grand Slam Market
Before building any list, validate the target market against all 4 variables. All four must score high — a weak score on any one disqualifies the segment.

| Variable | Question | What "Good" Looks Like |
|----------|----------|----------------------|
| **Massive Pain** | Does this group have a problem so painful they'll pay almost anything to solve it? | They're actively searching for solutions, complaining in forums, switching providers, losing sleep |
| **Purchasing Power** | Can they actually pay? Not "would they like to" — CAN they? | Revenue, net worth, budget authority, or institutional backing to write the check |
| **Easy to Target** | Can you find them in a list, a room, a community, or a search? | They self-identify in LinkedIn titles, attend specific events, belong to named associations, show up in databases |
| **Growing Market** | Is the pool getting bigger or smaller? | More people entering the segment each year, tailwinds from macro trends, regulatory changes creating new demand |

**Kill criterion:** If Purchasing Power or Easy to Target scores below 7/10, stop. No amount of outreach fixes an untargetable or broke audience.

### Russell Brunson — Dream 100
The Dream 100 is not a prospect list — it's a map of where prospects gather. Instead of finding 100 individuals, find 100 **congregations**:

- **Influencers** — Who do your prospects follow, trust, and listen to? (LinkedIn creators, podcast hosts, newsletter writers, YouTube channels)
- **Podcasts** — Which shows do they appear on as guests or listen to regularly?
- **Events** — Which conferences, retreats, mastermind dinners, and industry meetups do they attend?
- **Communities** — Which membership groups, associations, peer networks, and online forums do they belong to?
- **Service Providers** — Which lawyers, accountants, bankers, consultants, and advisors already serve them? (These are referral partners, not competitors.)
- **Publications** — Which newsletters, trade magazines, and media outlets cover their world?

**The play:** Show up in these 100 places before you ever send a cold message. Comment on the influencer's posts. Attend the events. Join the communities. Get on the podcasts. By the time you reach out to an individual prospect, they've already seen your name 3-5 times.

### Robert Cialdini — Social Proof + Unity
Two principles matter most for prospect list building:

- **Social Proof:** Identify which prospects already have connections to your existing network. A warm intro from a shared contact converts 5-10x better than cold outreach. Prioritize prospects where you have mutual connections, shared group memberships, or event co-attendance.
- **Unity:** Find shared tribe markers — same alma mater, same industry origin, same peer network or community, same city, same career trajectory, same background story. Unity ("you're one of us") is more powerful than liking ("I like you"). Build outreach around these identity overlaps.

## Step-by-Step Procedure

### Step 1: Define and Validate the ICP
Confirm with the user:
- [ ] **Role/Title** — What is the prospect's job title or function? (e.g., Founder, CEO, Geschäftsführer, Head of {function}, Managing Partner)
- [ ] **Geography** — Where are they located? Be specific: country, region, city cluster
- [ ] **Qualifying Threshold** — What revenue, headcount, budget, or other quantitative threshold qualifies them? (e.g., EUR 5M+ ARR, 50+ employees, USD 500K+ annual spend)
- [ ] **Industry / Sector** — Which verticals? Or is this industry-agnostic?
- [ ] **Company Size** — Employees, revenue, or other size proxy
- [ ] **Psychographic Qualifier** — What mindset or situation are they in? (e.g., "recently exited", "succession planning", "scaling past 50 employees", "frustrated with current provider")
- [ ] **Disqualifiers** — Who do you NOT want? (e.g., "no corporate employees", "no pre-revenue startups", "no inherited wealth without operating experience")

**Then validate against Hormozi's Grand Slam Market (Step 1b):**

| Variable | Score (1-10) | Evidence |
|----------|-------------|----------|
| Massive Pain | | |
| Purchasing Power | | |
| Easy to Target | | |
| Growing Market | | |

If any variable scores below 5, discuss with the user before proceeding. If Purchasing Power or Easy to Target is below 7, strongly recommend narrowing or switching segments.

### Step 2: Build Sales Navigator Saved Searches
LinkedIn Sales Navigator is the primary identification tool. Build 3-5 saved searches using specific filter combinations. Each search should target a different angle into the same ICP.

**Sales Navigator Filter Reference:**

| Filter | How to Use |
|--------|-----------|
| **Job Title** | Current title keywords (CEO, Founder, Geschäftsführer, Managing Partner, Inhaber). Use OR logic for synonyms. |
| **Company Headcount** | Proxy for business size and purchasing power. 11-50 = established SMB, 51-200 = mid-market, 201-500 = upper mid. |
| **Geography** | Country, region, or specific metro areas. Layer multiple for DACH (Germany + Austria + Switzerland). |
| **Industry** | LinkedIn's industry taxonomy. Select primary + adjacent industries. |
| **Years in Current Position** | Filter for tenure: 1-2 years = recent move/exit, 10+ years = established owner. |
| **Company Type** | Privately Held (exclude public companies if targeting owners). Self-Employed for solopreneurs. |
| **Posted on LinkedIn** | Last 30 days = active user, more likely to see/respond to outreach. |
| **Changed Jobs** | Last 90 days = transition signal (exit, new role, retirement). |
| **Groups** | Member of specific LinkedIn groups relevant to ICP. |
| **School** | Shared alma mater for Unity-based outreach. |
| **Connections Of** | 2nd-degree connections of your existing network = warm path available. |
| **Spotlight: Company Activity** | Companies with recent funding, leadership changes, or job postings. |

**Search Construction Pattern:**
```
Search 1: [Core ICP] — Title + Geography + Company Size
Search 2: [Transition Signal] — Changed Jobs Last 90 Days + Title + Geography
Search 3: [Network Proximity] — 2nd-Degree Connections + Title + Industry
Search 4: [Community Signal] — Group Members + Geography + Title
Search 5: [Activity Signal] — Posted Last 30 Days + Title + Geography + Industry
```

Save each search in Sales Navigator. Set weekly alerts for new matches.

### Step 3: Map the Dream 100 Congregations
Before exporting individual prospects, map the 100 places where your ICP gathers. This feeds both prospecting AND content/visibility strategy.

**Dream 100 Worksheet:**

| Category | Target Count | Examples to Find |
|----------|-------------|-----------------|
| **Influencers / LinkedIn Creators** | 15-20 | Who posts content your ICP engages with? Check comments on relevant posts. |
| **Podcasts** | 10-15 | Which shows feature guests matching your ICP? Which shows does your ICP listen to? |
| **Events & Conferences** | 10-15 | Industry conferences, invite-only dinners, masterminds, summits. Both virtual and in-person. |
| **Communities & Peer Networks** | 15-20 | EO, YPO, Vistage, industry Verbände, paid masterminds, Slack/Discord groups, WhatsApp groups. |
| **Service Providers (Referral Partners)** | 15-20 | M&A advisors, wealth managers, tax advisors, corporate lawyers, executive coaches — anyone who already has trust with your ICP. |
| **Publications & Newsletters** | 10-15 | Trade press, Substack newsletters, industry reports, media outlets your ICP reads. |
| **LinkedIn Groups** | 5-10 | Active groups with 500+ members matching your ICP. |

**How to find them:**
1. Start with 5-10 known prospects and reverse-engineer: What do they follow? What events did they attend? Who do they engage with on LinkedIn?
2. Search LinkedIn for posts with high engagement from your ICP — who wrote them?
3. Search podcast directories (Apple Podcasts, Spotify) for keywords matching your ICP's world
4. Search Eventbrite, Meetup, conference websites for industry events
5. Ask existing clients/partners: "What communities are you part of? What do you read?"

Save the Dream 100 list in a spreadsheet with columns: Name, Type (influencer/event/community/etc.), URL, Audience Size, Overlap with ICP (H/M/L), Infiltration Status (not started / engaging / relationship built).

### Step 4: Export & Clean Raw Prospect Data
Use specialized tools to extract prospect data from Sales Navigator and Dream 100 sources.

#### Evaboot (Primary — Sales Navigator Export)
- Install Evaboot Chrome extension
- Run each saved search from Step 2
- Evaboot auto-cleans: removes false positives, verifies titles match your search, flags mismatches
- Export as CSV with columns: First Name, Last Name, Title, Company, Location, LinkedIn URL, Connection Degree

**Evaboot settings:**
- Enable "Verify prospect relevance" — removes people whose title doesn't actually match your keywords
- Enable "Find email" if you need email addresses for outbound (uses a built-in email finder)
- Export in batches of 100-500 to avoid LinkedIn rate limits
- Run exports on different days/times to stay under radar

#### PhantomBuster (Secondary — Engagement & Community Mining)
Use PhantomBuster for sources Sales Navigator can't reach:

| Phantom | Use Case | Output |
|---------|----------|--------|
| **LinkedIn Post Likers** | Scrape everyone who liked/commented on a key influencer's post | People who actively engage with ICP-relevant content = high intent |
| **LinkedIn Group Members** | Extract members from LinkedIn groups matching your ICP | Community signal + shared interest |
| **LinkedIn Event Attendees** | Scrape attendee lists from LinkedIn Events | Timing signal + topic interest |
| **LinkedIn Company Employees** | Extract all employees from a target company | For ABM plays targeting specific organizations |
| **LinkedIn Profile Scraper** | Enrich a list of LinkedIn URLs with full profile data | Fill in missing fields from partial lists |
| **LinkedIn Search Export** | Alternative to Evaboot if you don't have it | Raw export from any LinkedIn search |

**PhantomBuster workflow:**
1. Create a Phantom for each source (post, group, event, search)
2. Set rate limits: max 80-100 profiles per day per Phantom to avoid LinkedIn restrictions
3. Export to CSV
4. Merge all CSVs into one master sheet
5. Deduplicate on LinkedIn URL (primary key)

#### Deduplication & Cleaning
After combining all exports:
1. Remove duplicates (same LinkedIn URL appearing in multiple sources)
2. Remove prospects matching any disqualifier from Step 1
3. Flag prospects appearing in multiple sources (multi-signal = higher priority)
4. Standardize geography names and company names
5. Add a "Source" column tracking which search/export found each prospect

### Step 5: Enrich Each Prospect (2 Minutes Per Prospect)
For each prospect in the cleaned list, spend exactly 2 minutes gathering enrichment data. This is NOT deep research — it's a quick scan to inform scoring and outreach approach.

**2-Minute Enrichment Checklist:**

| Data Point | Where to Find | Why It Matters |
|------------|--------------|----------------|
| **What they built/exited** | LinkedIn About/Experience, Crunchbase, press coverage | Establishes their story and potential pain points |
| **Exit details** (if available) | Press releases, Crunchbase, LinkedIn posts about "new chapter" | Timing signal: recent exit = active capital deployment window |
| **Mutual connections** | LinkedIn "X shared connections" | Warm intro path — note the strongest shared contact |
| **Recent posts/activity** | Last 3-5 LinkedIn posts | Topics they care about, tone, engagement level. Also: are they active on LinkedIn at all? |
| **Network overlap** | Shared groups, events, communities | Unity markers for outreach personalization |
| **Current situation** | LinkedIn headline, About section, recent job changes | Are they in transition? New role? Retired? Actively investing? |
| **Trigger event** | Job change, company milestone, funding round, speaking engagement | Timing hook for outreach: "Congratulations on [trigger]..." |
| **Location specifics** | LinkedIn location, company HQ | Relevant for in-person events, regional references |

**Record enrichment in the spreadsheet:**
- Column: `Enrichment Notes` (free text, 2-3 sentences max)
- Column: `Warm Path` (name of mutual connection or shared community)
- Column: `Trigger Event` (what happened recently that creates an opening)
- Column: `Suggested Approach` (see Step 6)

**Time management:** For a list of 200 prospects, enrichment takes ~7 hours. Batch in 45-minute sessions (about 22 prospects per session). Do NOT try to enrich all at once — quality drops after 60 minutes.

### Step 6: Score and Rank Prospects
Every prospect gets three scores (1-5 each), combined into a Priority Score.

#### Fit Score (ICP Match) — How well do they match your Ideal Customer Profile?
| Score | Criteria |
|-------|----------|
| 5 | Perfect match: right role, geography, net worth/revenue, industry, company size. Hits every ICP criterion. |
| 4 | Strong match: hits 4 of 5 ICP criteria. One minor deviation (e.g., slightly outside geography, adjacent industry). |
| 3 | Moderate match: hits 3 of 5 ICP criteria. Could be a good prospect but not a slam dunk. |
| 2 | Weak match: hits 1-2 criteria. Only pursue if warmth or timing is exceptional. |
| 1 | Poor match: doesn't fit. Remove from active list. |

#### Warmth Score (Existing Connection / Engagement) — How warm is the path to them?
| Score | Criteria |
|-------|----------|
| 5 | Direct relationship: you've met, they know your name, mutual respect exists. Or: strong mutual connection willing to make an intro. |
| 4 | Shared community: same peer network, same mastermind, same event attendee list. OR: they've engaged with your content (liked, commented, shared). |
| 3 | Second-degree connection: you share 3+ mutual connections. They're aware of your brand/company but no direct interaction. |
| 2 | Third-degree or single mutual connection. No engagement history. Found only via search. |
| 1 | Completely cold: no shared connections, no engagement, no community overlap. Pure outbound. |

#### Timing Score (Recency of Trigger Event) — Is there a reason to reach out NOW?
| Score | Criteria |
|-------|----------|
| 5 | Massive trigger: just exited a company, just raised a fund, just posted about the exact problem you solve, actively looking for what you offer. |
| 4 | Recent trigger (last 30 days): job change, company milestone, spoke at a relevant event, published content on a relevant topic. |
| 3 | Moderate trigger (last 90 days): some activity suggesting relevance, but not urgent. |
| 2 | Stale trigger (90+ days ago) or general relevance without a specific timing hook. |
| 1 | No trigger: nothing recent to reference. Outreach would be purely cold and untimed. |

#### Priority Score Calculation
```
Priority Score = (Fit × 2) + Warmth + Timing
```

Fit is weighted double because targeting the wrong person wastes everything.

| Priority Score | Tier | Action |
|---------------|------|--------|
| 13-20 | **Tier 1 — Hot** | Top 50. Outreach this week. Personal, 1:1 approach. |
| 9-12 | **Tier 2 — Warm** | Next 50. Outreach this month. Semi-personalized approach. |
| 5-8 | **Tier 3 — Nurture** | Add to content/newsletter. Engage on LinkedIn. Monitor for trigger events. |
| 1-4 | **Tier 4 — Archive** | Remove from active list. Re-evaluate quarterly. |

### Step 7: Determine Outreach Approach
For each Tier 1 and Tier 2 prospect, assign a primary outreach approach based on enrichment data.

| Approach | When to Use | Example |
|----------|------------|---------|
| **Warm Intro** | Warmth 4-5: you have a strong mutual connection | Ask the mutual to make an email intro or a 3-way coffee/dinner |
| **Content Share** | They posted about a relevant topic, or you have content that directly addresses their situation | Send the article/video with a 2-line personal note: "Saw your post about X — wrote about this recently, thought you'd find it relevant" |
| **Event Invite** | You're hosting or attending an event they'd value | Personal invite to a dinner, roundtable, or conference. Exclusivity matters: "Keeping it to 12 people" |
| **Community Invite** | You run or are active in a community they'd benefit from joining | "We have a group of [similar people] — thought you'd be a great fit" |
| **DM / Direct Message** | Warmth 3+, clear trigger event, something specific to reference | LinkedIn DM referencing their recent post, exit, or shared connection. NEVER generic. |
| **Cold Email** | Warmth 1-2, but Fit 5 and Timing 4-5 — they're too perfect to skip | Highly personalized email. Reference something specific (their company, their content, their exit). Use the Outbound Copy Manager skill for the sequence. |
| **Long Game / Nurture** | Fit 5 but Warmth 1-2 and no trigger | Engage with their content. Attend their events. Join their communities. Build visibility before making contact. |

Record the approach in the spreadsheet: `Suggested Approach` column.

### Step 8: Produce the Final Deliverable
The output is a scored spreadsheet (Google Sheets or CSV) with the following columns:

| Column | Description |
|--------|------------|
| First Name | |
| Last Name | |
| Title | Current role |
| Company | Current company |
| Location | City, Country |
| LinkedIn URL | Primary key / dedup anchor |
| Source | Which search/export found them (and how many sources) |
| Fit Score | 1-5 |
| Warmth Score | 1-5 |
| Timing Score | 1-5 |
| Priority Score | Calculated: (Fit × 2) + Warmth + Timing |
| Tier | 1-4 |
| Enrichment Notes | 2-3 sentence summary from enrichment |
| Warm Path | Mutual connection or shared community |
| Trigger Event | Recent relevant event |
| Suggested Approach | warm intro / content share / event invite / community invite / DM / cold email / nurture |
| Status | not contacted / contacted / responded / meeting booked / converted / declined |

**Sort by:** Priority Score descending, then Warmth Score descending (warm prospects get priority within the same score).

**Save to:** `{venture-folder}/prospect-lists/{YYYY-MM}-{icp-slug}-prospects.csv`

Also produce a **Prospect List Summary** document:
```markdown
# Prospect List: {ICP Description}

**Venture:** {name}
**Date Built:** {YYYY-MM-DD}
**Total Prospects:** {count}
**Tier 1 (Hot):** {count} — outreach this week
**Tier 2 (Warm):** {count} — outreach this month
**Tier 3 (Nurture):** {count} — content + monitor
**Tier 4 (Archive):** {count} — removed from active

## Search Configuration
- Search 1: {description} — {results count}
- Search 2: {description} — {results count}
- ...

## Dream 100 Summary
- {count} influencers identified
- {count} events mapped
- {count} communities joined/targeted
- {count} service providers (referral partners) identified
- {count} publications tracked

## Top 10 Prospects (Tier 1, Highest Priority)
| # | Name | Company | Score | Approach | Why |
|---|------|---------|-------|----------|-----|
| 1 | {name} | {company} | {score} | {approach} | {1-line reason} |
| ... | | | | | |

## Warmest Paths
- {Mutual connection} can intro to: {prospect 1}, {prospect 2}, {prospect 3}
- {Community/event} gives access to: {prospect 4}, {prospect 5}

## Next Steps
1. Execute Tier 1 outreach (this week)
2. Begin Tier 2 outreach (this month)
3. Engage with Dream 100 congregations (ongoing)
4. Add Tier 3 to newsletter/content nurture
5. Re-score list in 30 days (triggers change, new connections made)
```

## Quality Checklist
Before delivering the final list, verify:
- [ ] **ICP validated** against Hormozi's Grand Slam Market — all 4 variables score 5+/10
- [ ] **At least 3 Sales Navigator saved searches** built with distinct filter angles
- [ ] **Dream 100 mapped** with at least 50 congregations across all 7 categories
- [ ] **Deduplication complete** — no duplicate LinkedIn URLs in the master list
- [ ] **Every Tier 1 prospect enriched** — enrichment notes, warm path, trigger event filled in
- [ ] **Scoring applied consistently** — Fit, Warmth, Timing scores all present with clear rationale
- [ ] **Suggested approach assigned** for every Tier 1 and Tier 2 prospect
- [ ] **No generic outreach** — every approach leverages something specific (shared connection, content, event, trigger)
- [ ] **Disqualifiers enforced** — no prospects matching the disqualifier criteria remain in the list
- [ ] **Multi-signal prospects flagged** — prospects appearing in 3+ sources are highlighted as high-confidence
- [ ] **Export tools configured** — Evaboot and/or PhantomBuster set up with proper rate limits
- [ ] **Spreadsheet sortable and filterable** — proper column headers, no merged cells, consistent formatting
- [ ] **Cialdini check:** Unity markers (shared tribe) and Social Proof paths (mutual connections) identified for top 50
- [ ] **Dream 100 infiltration plan** started — not just listed, but first engagement actions defined

## Configuration Template

Fill in this YAML before running the skill. Every value should come from your Asset Foundations CSV (run `asset-foundation-builder.md` first if you don't have one).

```yaml
venture: {YOUR_VENTURE_NAME}
founder: {FOUNDER_NAME}
icp:
  role: {PROSPECT_ROLES — e.g., Founder, CEO, Head of {function}}
  qualifying_threshold: {REVENUE_OR_HEADCOUNT_OR_BUDGET_RANGE}
  geography: {COUNTRIES_OR_CITY_CLUSTERS}
  industry: {VERTICALS — or "industry-agnostic" if defined by other traits}
  company_size: {EMPLOYEE_OR_REVENUE_BAND}
  psychographic: "{ONE_SENTENCE_DESCRIBING_HOW_THEY_THINK_AND_WHAT_THEY_WANT}"
  disqualifiers:
    - {DISQUALIFIER_1}
    - {DISQUALIFIER_2}
    - {DISQUALIFIER_3}
grand_slam_market:
  massive_pain: {1-10 score} — "{ONE_LINE_DESCRIPTION_OF_THE_PAIN_INCLUDING_QUANTIFIED_LOSS}"
  purchasing_power: {1-10 score} — "{WHO_HAS_BUDGET_AND_HOW_MUCH}"
  easy_to_target: {1-10 score} — "{HOW_THEY_SELF-IDENTIFY_ONLINE_AND_OFFLINE}"
  growing_market: {1-10 score} — "{WHY_THIS_MARKET_IS_EXPANDING}"
```

### Sales Navigator Search Patterns

Build 3–5 searches by combining filters. Each search is a hypothesis about where your ICP self-identifies. The patterns below show structure — fill in the `{placeholders}` from your own ICP.

**Pattern A: Title-led search (the "they call themselves X" angle)**
```
Title: {TITLE_1} OR {TITLE_2} OR {TITLE_3}
AND Geography: {YOUR_TARGET_REGIONS}
AND Company Headcount: {YOUR_RANGE}
AND Posted on LinkedIn: Last 30 days
```
*Rationale: anchored on the prospect's stated identity. Works when your ICP self-describes consistently.*

**Pattern B: Trigger-event search (the "they just changed something" angle)**
```
Title: {TITLE_1} OR {TITLE_2}
AND Changed Jobs: Past Year
AND {ADDITIONAL_TRIGGER_FILTER — e.g., past company size, funding event, role change}
AND Geography: {YOUR_TARGET_REGIONS}
```
*Rationale: trigger events create buying windows. People in motion are easier to reach.*

**Pattern C: Group / community membership search (the "they belong to X tribe" angle)**
```
Groups: {RELEVANT_PROFESSIONAL_GROUP_1} OR {RELEVANT_PROFESSIONAL_GROUP_2}
AND Title: {TITLE_1} OR {TITLE_2}
AND Geography: {YOUR_TARGET_REGIONS}
```
*Rationale: peer-network membership signals identity + openness to peer recommendations.*

**Pattern D: Tenure / stage search (the "they're at the right point in their journey" angle)**
```
Title: {TITLE_1} OR {TITLE_2}
AND Years in Current Position: {RANGE — e.g., 10+ if you target experienced operators}
AND Company Type: {PRIVATELY_HELD / PUBLIC / etc.}
AND Geography: {YOUR_TARGET_REGIONS}
```
*Rationale: career stage often predicts buying readiness more than role does.*

**Pattern E: Adjacent-role search (the "they sit next to your real buyer" angle)**
```
Title: {ROLE_THAT_INFLUENCES_OR_RECOMMENDS_YOUR_BUYER}
AND Company Type: {YOUR_FILTER}
AND Geography: {YOUR_TARGET_REGIONS}
```
*Rationale: in many B2B contexts, the influencer is more reachable than the decision-maker.*

### Dream 100 Categories — Skeleton

| Category | What to look for |
|----------|------------------|
| **Influencers / LinkedIn Creators** | People your ICP follows and engages with. Use Sales Navigator + post-engagement scraping. |
| **Podcasts** | Shows your ICP listens to (or appears on as guests). Cross-reference against your customer interviews. |
| **Events** | Conferences, summits, dinners your ICP attends. Both virtual and in-person. |
| **Communities** | Peer networks (founder groups, masterminds, industry associations) where your ICP gathers. |
| **Service Providers (Referral)** | Adjacent service providers who already have trust with your ICP — lawyers, accountants, agencies, advisors. |
| **Publications** | Trade press and newsletters your ICP reads. |
| **LinkedIn Groups** | Active groups (500+ members) matching your ICP. |

For each category, list 10–20 specific names relevant to your market and geography. The categories are universal; the contents are venture-specific.

### Export & Scoring Workflow

1. **Export** all searches via Evaboot — expect a few hundred to a few thousand raw results.
2. **PhantomBuster scrape**: top engagers on relevant influencer posts — adds 200–500 prospects.
3. **Deduplicate** on LinkedIn URL — multi-source prospects get flagged as high-confidence.
4. **Quick filter** to remove disqualified profiles per your `disqualifiers` list.
5. **Enrich Tier 1 candidates** (top 100 by initial Fit score) — 2 min each.
6. **Score** all enriched prospects (Fit × 2 + Warmth + Timing).
7. **Prioritise** top 50 for immediate outreach.
8. **Assign approach** for each of top 50: warm intro, event invite, content share, or DM — based on the warmest available path.

### Outreach Priority Matrix — Skeleton

| Approach | Typical Volume | Typical Conversion | Use When |
|----------|----------------|---------------------|----------|
| Warm intro via mutual contact | Low (5–10/month) | Highest (30–40% to meeting) | You share a peer network, group, or strong mutual connection |
| Exclusive event invite | Medium (10–20/quarter) | High (20–30% to meeting) | You host a relevant gathering and they fit |
| Content share | High (20–30/month) | Medium (5–10% to response) | Prospect has signalled interest in the topic via their own posts |
| LinkedIn DM | High (30–50/month) | Low-Medium (3–7% to response) | Recent trigger event, personalised reference, no better warm path |
| Cold email | High (50–100/month) | Low (1–3% to response) | Fit ≥ 5, no warm path — use Outbound Copy Manager sequences |

## Anti-patterns
- **Title-only filters without industry / company-size context.** The list explodes with bad fits. Always combine 2+ filters minimum.
- **One mega-search instead of 3–5 narrower searches.** You can't A/B the angle. Each pattern should test a different hypothesis about where your ICP self-identifies.
- **Skipping the disqualifier list.** You burn enrichment budget on profiles you'd never close. Disqualifiers cost minutes, save hundreds of dollars.
- **Enriching the entire list at $1+/profile before scoring.** Score first (cheap), enrich tier 1 only (expensive). Reverse order torches the budget.
- **Building Dream 100 from imagination instead of from where your ICP actually gathers.** Reverse-engineer from 5–10 known prospects: what do they follow, listen to, attend, comment on? That's your Dream 100.
- **Treating Sales Nav as the only source.** Misses post-engagers, podcast guests, conference attendees, content commenters. Multi-source raises top-of-funnel quality.

## Adaptation Notes
This skill is venture-agnostic. When applying:
- Fill the Configuration Template above using your Asset Foundations.
- Adjust Sales Navigator searches — a SaaS founder targeting CTOs needs different title/industry filters than a services founder targeting CFOs.
- Adjust Dream 100 categories — service providers, publications, and communities differ wildly across markets.
- Scoring weights may shift: for transactional sales, Timing matters more; for relationship sales, Warmth matters more.
- For high-volume B2B (100+ prospects/month): automate enrichment with tools like Clay, Apollo, or Clearbit instead of manual 2-min checks.
- For low-volume high-value (10–20 prospects/quarter): spend 10–15 minutes per prospect, not 2, and include deep research.
- For German-speaking markets: search both German and English titles (Geschäftsführer AND CEO, Gründer AND Founder).
- Dream 100 is geography-sensitive: DACH events and communities differ completely from US/UK — rebuild for each market.

---

Status: Live — ready to use now.

## Hand-off — what to consume from upstream
- **ICP block in the YAML** ← Asset Foundation Row 1 (Position) — direct copy
- **Disqualifiers** ← Row 6 (failed alternatives — invert into "people who won't ever buy")
- **Sales Nav title filters** ← Row 1 (job titles) + Row 9 (vehicle context)
- **Trigger-event filters** ← Row 7 (market trends + threats)
- **Dream 100 communities** ← Row 6 (where they look for solutions) + Row 1 (where they self-identify)

Run `asset-foundation-builder.md` first.
