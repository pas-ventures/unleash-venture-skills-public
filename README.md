# Unleash Venture Skills

A set of battle-tested go-to-market skills for [Claude Code](https://claude.ai/code). Each skill is a structured prompt that turns Claude into a specialist for that GTM function — asset foundations, niche research, outbound, landing pages, drip campaigns, LinkedIn, prospect sourcing, sales scripting, ad copy.

These are the skills used inside the [Unleash](https://unleash-ventures.com) community to ship GTM assets in hours, not workshop weeks.

## Skills Included

### Foundations (start here)
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Asset Foundation Builder](asset-foundation-builder.md)** | Turn customer call transcripts into a 12-row CSV — ICP, deepest desires, frustrations, failed alternatives, market threats, and the layered benefit stack. The input every other skill expects. | You have call recordings and you're about to write any market-facing copy |
| **[Niche Research](niche-research.md)** | Deep-dive into any vertical — pains, market size, jargon, emotional hooks, competitor landscape | Before writing any copy or building any landing page |

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
  Niche Research          Landing Page Builder        Sales Script Creator
        │                         │                         │
        ↓                         ↓                         ↓
  Prospect List Builder    Drip Campaign Builder      Booked calls + closes
        │                         │
        ↓                         ↓
  Outbound Copy Manager    Inbound Marketing Playbook
  Outreach Draft Writer     (page + drip combined)
  LinkedIn Outreach
        │
        ↓
                  Content Engine + FB Ads
                 (paid + organic amplification)
```

1. **Foundations first.** Asset Foundation Builder + Niche Research before anything else. Skip these and every downstream asset will be guessing.
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
- **Russell Brunson** — *DotCom Secrets* / *Expert Secrets* (hook–story–offer, epiphany bridge)
- **Jordan Belfort** — *Way of the Wolf* (pattern interrupt, certainty transfer, looping)
- **Robert Cialdini** — *Influence* (the 7 principles, mapped into outreach + content)
- **Noah Kagan** — *Million Dollar Weekend* (validation-first thinking)
- **Toyota / Eric Ries** — 5 Whys, build–measure–learn (foundations + iteration)

## Language & Market

These skills were first battle-tested on German B2B SMB niches, so you'll see DACH examples in several of them (e.g. Niche Research references Hausverwaltungen, SHK-Handwerk, Schornsteinfeger). The frameworks work anywhere — the examples are illustrative. Adapt the language sections for your target market.

The **Sales Script Creator** is bilingual by design (EN / DE) and outputs both languages natively.

## Q&A Transcripts

The [`qa-transcripts/`](qa-transcripts/) folder contains anonymised transcripts of Unleash community Q&A sessions. Drop one into a Claude conversation and ask questions — they're a useful pattern-matching resource alongside the skills.

## License + Use

This repo is shared openly so any founder building inside the Unleash community — and beyond — can fork it, adapt it, and ship faster. Please credit Unleash if you publish derivatives.

For the four core skills bundled separately for the EO community, see [pas-ventures/eo-gtm-skills-public](https://github.com/pas-ventures/eo-gtm-skills-public). For deeper application support and live working sessions, find Unleash at [unleash-ventures.com](https://unleash-ventures.com).
