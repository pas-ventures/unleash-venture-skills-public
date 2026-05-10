# Unleash Venture Skills

A set of battle-tested go-to-market skills for [Claude Code](https://claude.ai/code). Each skill is a structured prompt that turns Claude into a specialist for that GTM function — asset foundations, outbound, landing pages, drip campaigns, LinkedIn, prospect sourcing, sales scripting, ad copy.

These are the skills used inside the [Unleash](https://unleash-ventures.com) community to ship GTM assets in hours, not workshop weeks.

## Skills Included

### Foundations (start here)
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Asset Foundation Builder](asset-foundation-builder.md)** | Kennedy 13-row CSV + niche-brief MD from YouTube / web / Reddit / forums / podcasts / call transcripts. Pains, false beliefs, market size, jargon (use vs avoid), recognition quotes, where they gather, hooks. The upstream contract every other skill consumes. | Before writing any copy or building any landing page |

### Inbound (capture + nurture)
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Landing Page Builder](landing-page-builder.md)** | Build a high-converting 2-page landing page + progressive signup flow | You need a niche-specific landing page fast |
| **[Drip Campaign Builder](drip-campaign-builder.md)** | 12-email, 25-day post-opt-in nurture sequence | Converting landing-page leads into calls / demos |
| **[Inbound Marketing Playbook](inbound-marketing-playbook.md)** | Combined Landing Page + Drip Campaign as a single sequenced funnel | You want both assets built and aligned in one pass |

### Outbound (direct prospecting)
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Prospect List Builder](prospect-list-builder.md)** | Systematic prospect identification, enrichment, and scoring (Sales Navigator, Dream 100, multi-source export) | Before launching any outbound or ABM campaign |
| **[Outbound Copy Manager](outbound-copy-manager.md)** | 3-email cold outbound sequence with 5 opener variants for A/B testing | Running cold email campaigns to a new niche |
| **[Outreach Draft Writer](outreach-draft-writer.md)** | Content-first LinkedIn / email outreach with engagement-before-outreach playbook and Cialdini principles per message | When you want personal, founder-led outreach (not cold blast) |
| **[LinkedIn Outreach](linkedin-outreach.md)** | Systematic LinkedIn connection + DM pipeline with safety limits | Building founder / prospect pipeline via LinkedIn |

### Sales + Conversion
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Sales Script Creator](sales-script-creator.md)** | Bilingual (EN / DE) discovery + closing framework from your customer transcripts. Belfort + Hormozi + Kagan under the hood | When launching outbound into a new niche with real interview data |

### Content + Paid
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Content Engine](content-engine.md)** | Framework-driven content production with voice training, target-group research, platform optimization | Producing founder-led thought leadership at scale |
| **[Facebook Ads From Customer Transcripts](facebook-ads-from-customer-transcripts.md)** | Turn customer transcripts into hook / body / CTA variants in the customer's own language | Running Meta ads in B2C or SMB-B2B |

## How They Work Together

```
                       Asset Foundation Builder
                                  │
                       (the customer-truth input
                        every other skill consumes)
                                  │
        ┌─────────────────────────┼─────────────────────────┐
        ↓                         ↓                         ↓
  Prospect List Builder    Landing Page Builder        Sales Script Creator
        │                         │                         │
        ↓                         ↓                         ↓
  Outbound Copy Manager    Drip Campaign Builder      Booked calls + closes
  Outreach Draft Writer     Inbound Marketing Playbook
  LinkedIn Outreach          (page + drip combined)
        │
        ↓
                  Content Engine + FB Ads
                 (paid + organic amplification)
```

1. **Foundation first.** Asset Foundation Builder before anything else. Output (CSV + niche-brief MD) is the upstream contract every other skill consumes. Skip it and every downstream asset will be guessing.
2. **Build the page.** Landing Page Builder creates the conversion endpoint.
3. **Nurture inbound.** Drip Campaign Builder handles post-signup email. Use Inbound Marketing Playbook to build both as a single connected funnel.
4. **Build the list.** Prospect List Builder — identify, score, prioritise.
5. **Run cold outbound.** Outbound Copy Manager for cold sequences. Outreach Draft Writer for content-first founder outreach. LinkedIn Outreach for the personal connection pipeline.
6. **Book calls.** Sales Script Creator turns your customer transcripts into the first-call + closing framework.
7. **Produce content.** Content Engine for founder-led thought leadership.
8. **Paid amplification.** Facebook Ads From Customer Transcripts for Meta campaigns.

## How to Use with Claude Code

### Option A: Drop into project context
Copy the `.md` files into your project's root or a `skills/` folder. Claude Code will pick them up as project context.

### Option B: Add to Claude Code memory
Copy files into your Claude Code memory directory:
```
~/.claude/projects/{your-project}/memory/
```

### Option C: Reference directly
Just tell Claude: *"Use the Landing Page Builder skill in `skills/landing-page-builder.md` to build a page for {niche}."*

### Option D: Fork this repo
Fork the repo, replace the placeholders with your venture's specifics, and use it as a reusable skill set across all your projects.

## Customisation

Each skill uses `{PLACEHOLDER}` variables. Before first use, search for `{` and replace:

- `{PRODUCT_NAME}` — your product or service
- `{COMPANY}` — your company name
- `{DOMAIN}` — your website
- `{BOOKING_LINK}` — your Calendly or scheduling link
- `{SENDER_NAME}` — person sending outbound emails

Each skill includes a Configuration Template using `{PLACEHOLDER}` syntax. Search for `{` and replace each placeholder with your venture's specifics before running the skill.

## Frameworks Underneath

- **Alex Hormozi** — *$100M Offers* / *$100M Leads* (value equation, grand-slam offers, scarcity)
- **Dan Kennedy** — *The Ultimate Sales Letter*, *Magnetic Marketing* (pain–agitate–solve, value stacking, the bodacious claim)
- **Russell Brunson** — *DotCom Secrets* / *Expert Secrets* (hook–story–offer, epiphany bridge, three false beliefs)
- **Jordan Belfort** — *Way of the Wolf* (pattern interrupt, certainty transfer, looping)
- **Robert Cialdini** — *Influence* (the 7 principles, mapped into outreach + content)
- **Noah Kagan** — *Million Dollar Weekend* (validation-first thinking)
- **Toyota / Eric Ries** — 5 Whys, build–measure–learn (foundations + iteration)

## Language & Market

These skills were first battle-tested on German B2B SMB niches, so you'll see DACH-flavored examples in several of them (Anlage A trades, professional-services firms, service-businesses with white-collar/field-operative splits). The frameworks work anywhere — the examples are illustrative. Adapt the language sections for your target market.

The **Sales Script Creator** is bilingual by design (EN / DE) and outputs both languages natively.

## Q&A Transcripts

The [`qa-transcripts/`](qa-transcripts/) folder contains anonymised transcripts of Unleash community Q&A sessions. Drop one into a Claude conversation and ask questions — they're a useful pattern-matching resource alongside the skills.

## Validating Your Asset Bundle

Before pushing assets into paid channels or your sales pipeline, run these 5 checks. They're cheap, fast, and catch the failure modes that kill conversion before it starts. Most operators have one product / one niche — these checks are how you stress-test your single bundle from different angles before you spend a euro.

### 1. Quote-recognition test
Read your CSV's Row 4–5 verbatim to **3 real practitioners** in the niche (current customers, prospects, or even cold-outreach interview partners). Track recognition rate — i.e. unprompted *"yes, that's exactly me"* reactions.
- ≥70% recognition: foundation is solid.
- <70%: the language is yours, not theirs. Go back to sources, pull more verbatim.

### 2. Different-angles A/B
From your foundation, draft **3 different positioning angles** off the same Row 2 / Row 10:
- **Pain-led** (Rows 3–5 dominant) — "you're drowning in X"
- **Aspiration-led** (Row 2 + Row 12 dominant) — "imagine the day you stop drowning"
- **Contrast-led** ("everyone else does X, the best do Y") — Row 6 dominant

Run each with $100 budget on Meta to the same audience. Winner = CPL ≥50% below the losers. That's your master frame for the next 90 days. The losers tell you what your prospects don't believe yet — useful intel for nurture content.

### 3. Hook-density check
Each of your Top 5 Pains should yield **at least 2 distinct ad hooks**. If a pain only yields 1, it's not pain-rich enough — drop it from rotation, or go back to source corpus and dig deeper.

### 4. Cost-of-inaction sanity
Your Row 8 EUR/month (or USD/month) status-quo cost should be **5–10× your monthly subscription price**. If it's less, urgency won't carry — your offer doesn't pay for itself fast enough in the prospect's mental math. Either find more leak-points to add to the cost calculation, or reposition price.

### 5. Voice-borrowing audit
Print your landing page, ads, and discovery script side-by-side. Read them out loud.
- Does the language sound like the practitioner talking to themselves?
- Or does it sound like generic SaaS marketing?

If even 20% reads as outsider voice, strip until practitioner phrases dominate. The fastest fix: replace your own paraphrase with a verbatim quote from a transcript or the niche-brief's recognition-quote slots.

---

If you fail check 1 or 5, the foundation needs more work — go back to the corpus. Checks 2–4 are run after launch, mostly to optimize spend. Run check 1 weekly during the first quarter of a niche; run check 5 every time you change copy.

## License + Use

This repo is shared openly so any founder building inside the Unleash community — and beyond — can fork it, adapt it, and ship faster. Please credit Unleash if you publish derivatives.

For deeper application support and live working sessions, find Unleash at [unleash-ventures.com](https://unleash-ventures.com).
