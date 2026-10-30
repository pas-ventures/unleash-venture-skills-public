# Unleash Venture Skills

A set of battle-tested go-to-market skills for [Claude Code](https://claude.ai/code). Each skill is a structured prompt that turns Claude into a specialist for that GTM function — asset foundations, outbound, landing pages, drip campaigns, LinkedIn, prospect sourcing, sales scripting, ad copy.

These are the skills used inside the [Unleash](https://unleash-ventures.com) community to ship GTM assets in hours, not workshop weeks.

## Install

This repo is a Claude Code plugin marketplace called `unleash-ventures`. You can install all 15 skills as one plugin, `unleash-venture-skills`, or install only the skills you need: every skill is also its own plugin, named after its folder under [`skills/`](skills/).

### In Claude Code

```
/plugin marketplace add pas-ventures/unleash-venture-skills-public
/plugin install unleash-venture-skills@unleash-ventures
```

Then run `/reload-plugins`, or start a new session.

### Install only the skills you need

Add the marketplace once, then install each skill you want on its own:

```
/plugin marketplace add pas-ventures/unleash-venture-skills-public
/plugin install asset-foundation-builder@unleash-ventures
```

| Skill | Install |
|-------|---------|
| [asset-foundation-builder](skills/asset-foundation-builder/SKILL.md) | `/plugin install asset-foundation-builder@unleash-ventures` |
| [content-engine](skills/content-engine/SKILL.md) | `/plugin install content-engine@unleash-ventures` |
| [drip-campaign-builder](skills/drip-campaign-builder/SKILL.md) | `/plugin install drip-campaign-builder@unleash-ventures` |
| [facebook-ads-from-customer-transcripts](skills/facebook-ads-from-customer-transcripts/SKILL.md) | `/plugin install facebook-ads-from-customer-transcripts@unleash-ventures` |
| [how-to-run-a-company-brain](skills/how-to-run-a-company-brain/SKILL.md) | `/plugin install how-to-run-a-company-brain@unleash-ventures` |
| [inbound-marketing-playbook](skills/inbound-marketing-playbook/SKILL.md) | `/plugin install inbound-marketing-playbook@unleash-ventures` |
| [landing-page-builder](skills/landing-page-builder/SKILL.md) | `/plugin install landing-page-builder@unleash-ventures` |
| [linkedin-outreach](skills/linkedin-outreach/SKILL.md) | `/plugin install linkedin-outreach@unleash-ventures` |
| [outbound-copy-manager](skills/outbound-copy-manager/SKILL.md) | `/plugin install outbound-copy-manager@unleash-ventures` |
| [outreach-draft-writer](skills/outreach-draft-writer/SKILL.md) | `/plugin install outreach-draft-writer@unleash-ventures` |
| [prospect-list-builder](skills/prospect-list-builder/SKILL.md) | `/plugin install prospect-list-builder@unleash-ventures` |
| [sales-script-creator](skills/sales-script-creator/SKILL.md) | `/plugin install sales-script-creator@unleash-ventures` |
| [seo-strategy-builder](skills/seo-strategy-builder/SKILL.md) | `/plugin install seo-strategy-builder@unleash-ventures` |
| [unleash-stop-slop](skills/unleash-stop-slop/SKILL.md) | `/plugin install unleash-stop-slop@unleash-ventures` |
| [venture-one-pager-builder](skills/venture-one-pager-builder/SKILL.md) | `/plugin install venture-one-pager-builder@unleash-ventures` |

Some skills point to others. The Asset Foundation Builder feeds the landing page, outreach, sales script, ads and content skills, and the Inbound Marketing Playbook runs the Landing Page Builder and Drip Campaign Builder together. Install those alongside if you use them.

### From your terminal

```bash
claude plugin marketplace add pas-ventures/unleash-venture-skills-public
claude plugin install unleash-venture-skills@unleash-ventures
```

By default the skills are installed for you in every project (`--scope user`). Add `--scope project` to install them for one repo only and share them with everyone who works in it.

### Set it up for a team

Commit this to your repo's `.claude/settings.json`. When teammates trust the folder, Claude Code asks them to install the marketplace and turns the plugin on:

```json
{
  "extraKnownMarketplaces": {
    "unleash-ventures": {
      "source": { "source": "github", "repo": "pas-ventures/unleash-venture-skills-public" }
    }
  },
  "enabledPlugins": {
    "unleash-venture-skills@unleash-ventures": true
  }
}
```

### Use the skills

Ask for what you need ("build me a landing page for…", "write a cold email sequence for…") and Claude picks the right skill. To call one directly, use `/unleash-venture-skills:<skill-name>`, e.g. `/unleash-venture-skills:landing-page-builder`. If you installed a single skill, the prefix is the skill's own name, e.g. `/landing-page-builder:landing-page-builder`. The skill names are the folder names under [`skills/`](skills/). Run `/skills` to see them all.

The SEO Strategy Builder also needs two free MCP servers (Playwright and SerpApi). It checks for them on the first run and tells you the commands.

### Update or remove

```bash
claude plugin marketplace update unleash-ventures            # pull the latest skills
claude plugin uninstall unleash-venture-skills@unleash-ventures
claude plugin marketplace remove unleash-ventures
```

**Switching from copied files?** Before the plugin existed, skills were copied by hand from `.md` files in this repo's root, and those files are gone now. Once the plugin is installed, delete your old copies from `~/.claude/skills/` or your project's `.claude/skills/` so you don't end up with two versions of the same skill.

### Turn on auto-update

Claude Code leaves auto-update off for third-party marketplaces, so switch it on once:

1. Run `/plugin` and open the **Marketplaces** tab
2. Select `unleash-ventures`
3. Choose **Enable auto-update**

Claude Code then checks for new skill versions in the background after each session starts and asks you to run `/reload-plugins` when something changed. Without auto-update, pull changes by hand with `/plugin marketplace update unleash-ventures`.

For organisations, admins can turn it on for everyone in managed settings:

```json
{
  "extraKnownMarketplaces": {
    "unleash-ventures": {
      "source": { "source": "github", "repo": "pas-ventures/unleash-venture-skills-public" },
      "autoUpdate": true
    }
  }
}
```

## Skills Included

### Company OS (build this first)
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[How to Run a Company Brain](skills/how-to-run-a-company-brain/SKILL.md)** | Interviews you about your business, then hands you a ready-to-run build file that scaffolds a complete "company brain" — a folder-based memory Claude draws every answer from, so it stops guessing and remembers your context across chat, Cowork, and Code. Built by a founder in the Unleash community. | Before you automate anything — when you're tired of re-explaining your business to Claude every session |

### Foundations (start here)
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Asset Foundation Builder](skills/asset-foundation-builder/SKILL.md)** | Kennedy 13-row CSV + niche-brief MD from YouTube / web / Reddit / forums / podcasts / call transcripts. Pains, false beliefs, market size, jargon (use vs avoid), recognition quotes, where they gather, hooks. The upstream contract every other skill consumes. | Before writing any copy or building any landing page |

### Inbound (capture + nurture)
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Landing Page Builder](skills/landing-page-builder/SKILL.md)** | Build a high-converting 2-page landing page + progressive signup flow | You need a niche-specific landing page fast |
| **[Drip Campaign Builder](skills/drip-campaign-builder/SKILL.md)** | 12-email, 25-day post-opt-in nurture sequence | Converting landing-page leads into calls / demos |
| **[Inbound Marketing Playbook](skills/inbound-marketing-playbook/SKILL.md)** | Combined Landing Page + Drip Campaign as a single sequenced funnel | You want both assets built and aligned in one pass |

### Outbound (direct prospecting)
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Prospect List Builder](skills/prospect-list-builder/SKILL.md)** | Systematic prospect identification, enrichment, and scoring (Sales Navigator, Dream 100, multi-source export) | Before launching any outbound or ABM campaign |
| **[Outbound Copy Manager](skills/outbound-copy-manager/SKILL.md)** | 3-email cold outbound sequence with 5 opener variants for A/B testing | Running cold email campaigns to a new niche |
| **[Outreach Draft Writer](skills/outreach-draft-writer/SKILL.md)** | Content-first LinkedIn / email outreach with engagement-before-outreach playbook and Cialdini principles per message | When you want personal, founder-led outreach (not cold blast) |
| **[LinkedIn Outreach](skills/linkedin-outreach/SKILL.md)** | Systematic LinkedIn connection + DM pipeline with safety limits | Building founder / prospect pipeline via LinkedIn |

### Sales + Conversion
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Sales Script Creator](skills/sales-script-creator/SKILL.md)** | Bilingual (EN / DE) discovery + closing framework from your customer transcripts. Belfort + Hormozi + Kagan under the hood | When launching outbound into a new niche with real interview data |

### Content + Paid
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Content Engine](skills/content-engine/SKILL.md)** | Framework-driven content production with voice training, target-group research, platform optimization | Producing founder-led thought leadership at scale |
| **[Facebook Ads From Customer Transcripts](skills/facebook-ads-from-customer-transcripts/SKILL.md)** | Turn customer transcripts into hook / body / CTA variants in the customer's own language | Running Meta ads in B2C or SMB-B2B |
| **[SEO Strategy Builder](skills/seo-strategy-builder/SKILL.md)** | Crawls your site with a real browser (Playwright MCP), researches live search results (SerpApi MCP), and returns a ranked list of pages to build — target keyword, demand graded from evidence, why you can rank, and a brief for each | Before writing for search, or when organic traffic has stalled |

The SEO workflow is adapted from [James Devonport's write-up](https://jamesdevonport.com/p/i-got-claude-code-to-build-my-entire) on building an SEO strategy with Claude Code and two free MCPs.

### Fundraising + Intros
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Venture One-Pager Builder](skills/venture-one-pager-builder/SKILL.md)** | Audits your completed venture assessment against what an angel or advisor needs to see, tells you what's missing, then builds a branded one-page PDF in your own CI plus the intro blurb that carries it | Approaching an angel, operator, advisor or design partner — or whenever someone says "send me something short" |

### Quality + Voice
| Skill | What it does | Use when |
|-------|-------------|----------|
| **[Unleash Stop Slop](skills/unleash-stop-slop/SKILL.md)** | Detects which register you're writing in, then strips the AI tells: contrast-clichés, false agency ("the market rewards"), vague attribution, invented concept labels, and the document-level dilution that only shows up at length. Scores the draft out of 50 and returns a cleaned rewrite. | Before sending or publishing anything: investor updates, decks, cold outreach, customer email, posts |

Built on **[stop-slop](https://github.com/hardikpandya/stop-slop)** by [Hardik Pandya](https://hvpandya.com) and **[slop-cop](https://github.com/awnist/slop-cop)** by [awnist](https://awnist.com/slop-cop), both MIT. Use the originals if you prefer them — they are excellent, and most of the pattern taxonomy is theirs. What we added is a register model: the same rules that sharpen a LinkedIn post will strip the warmth out of an email to a customer, so this version picks the standard based on what you're actually writing.

**Want it live instead of installed?** [slop-cop](https://awnist.com/slop-cop) is a browser editor that highlights 36 of these patterns as you type. Nothing to set up, no API key needed for the instant checks.

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
9. **Raise or recruit.** Venture One-Pager Builder turns a completed venture assessment into the one page you send an angel, advisor or operator — plus the intro message that gets it opened.

## How to Use with Claude Code

### Option A: Install the plugin (recommended)
See [Install](#install). Skills load automatically in every project and stay current once you [turn on auto-update](#turn-on-auto-update).

### Option B: Copy into a project
Copy any folder from `skills/` into your project's `.claude/skills/` (or `~/.claude/skills/` for all projects). Claude Code loads each `SKILL.md` as a skill.

### Option C: Fork this repo
Fork the repo, replace the placeholders with your venture's specifics, and add your fork as the marketplace instead: `/plugin marketplace add {your-github-user}/unleash-venture-skills-public`.

To try your changes before pushing, run these from the repo root:

```bash
claude plugin validate .         # check the manifests and skills
claude --plugin-dir .            # start a session with your working copy loaded
```

## Customisation

Each skill uses `{PLACEHOLDER}` variables and includes a Configuration Template:

- `{PRODUCT_NAME}` — your product or service
- `{COMPANY}` — your company name
- `{DOMAIN}` — your website
- `{BOOKING_LINK}` — your Calendly or scheduling link
- `{SENDER_NAME}` — person sending outbound emails

With the plugin installed, give Claude these values in conversation (or keep them in your company brain, built with the `how-to-run-a-company-brain` skill) and it fills them in as it runs. To hard-code them, fork the repo (Option C) or copy the skills into your project (Option B) and search-and-replace each `{`.

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

## Releasing (maintainers)

Installed copies only update when the version number changes. A change merged without a version bump never reaches users.

1. Bump `version` in `.claude-plugin/plugin.json` and in **every** plugin entry in `.claude-plugin/marketplace.json` (the bundle and each single-skill plugin share one version number):
   - **Patch** (1.0.**1**): wording fixes and clarifications inside a skill
   - **Minor** (1.**1**.0): a new skill, or a new step or output in an existing one
   - **Major** (**2**.0.0): a skill renamed or removed, or an output format other skills depend on changed
2. Run `claude plugin validate .`
3. Merge to `main`, then from an up-to-date `main` tag and push the release:

```bash
claude plugin tag . --push -m "Release %s"
```

This creates the tag `unleash-venture-skills--v{version}`, and fails if the two manifest versions don't match.

## License + Use

This repo is shared openly so any founder building inside the Unleash community — and beyond — can fork it, adapt it, and ship faster. Please credit Unleash if you publish derivatives.

For deeper application support and live working sessions, find Unleash at [unleash-ventures.com](https://unleash-ventures.com).
