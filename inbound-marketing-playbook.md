# Inbound Marketing Playbook

## Overview

Thin orchestrator for building a **landing page + drip campaign as ONE connected funnel**, not two separate assets. The actual production work happens in the upstream skills — this skill adds only the alignment + sequencing logic that's invisible when the two skills run in isolation.

## When to Use
- "Build a landing page and drip campaign for {target group}"
- "Create an inbound funnel for {product/service}"
- "Build a single connected lead-capture-to-nurture flow"

If you only need ONE of the two assets, use that skill directly. This playbook adds value only when both are shipped together.

## Step 1 — Run Asset Foundation Builder (if not done)

The 13-row CSV + niche-brief is the upstream contract for both downstream skills.
→ See `asset-foundation-builder.md`

## Step 2 — Run Landing Page Builder

The funnel's entry point. Captures email + minimum qualifying data.
→ See `landing-page-builder.md`

## Step 3 — Run Drip Campaign Builder

12-email / 25-day post-opt-in nurture sequence.
→ See `drip-campaign-builder.md`

## Step 4 — Alignment work (UNIQUE to this skill)

This is the section the upstream skills can't deliver on their own.

### 4a. Form-to-drip data contract

Define exactly which fields the LP signup form captures and how the drip references them. At minimum:

| Field | LP form captures | Drip uses for |
|---|---|---|
| `{first_name}` | Email step 1 | Email salutation in every drip mail |
| `{role}` | Step 2 dropdown | Email 2 + 4 ICP-resonance lines |
| `{primary_pain}` | Step 2-3 multi-select | Email 3 false-belief teardown + Email 7 case-study match |
| `{company_size}` | Step 3 numeric range | Email 5 social-proof matching, Email 9 ROI math |
| `{language}` | Inferred from page (`EN`/`DE`) | Drip language locked end-to-end |
| `{ansprache}` (DE) | Inherited from LP `{DU_OR_SIE}` | Drip respects same register, never switches |

Document the contract before either asset is built. Mismatched field names break the handoff silently.

### 4b. Voice handoff

Drip Email 1 must echo the LP hero language so the prospect feels continuity, not a context switch:

- LP hero pull-quote → quoted (or paraphrased) in Email 1's first paragraph
- LP "Bodacious Claim" (Foundation Row 10) → reframed as Email 1's CTA promise
- LP day-in-life narrative (e.g. "Tuesday, 6:42 AM…") → optional callback in Email 1 or Email 3

If the prospect can't tell that the LP and Email 1 came from the same brain in the same hour, the funnel feels stitched-together.

### 4c. Timing alignment

| Trigger | Default timing | Why |
|---|---|---|
| Email 1 (welcome + problem confirm) | **Immediate** (≤2 min after opt-in) | Recency-boost — they're still on the page mentally |
| Email 2 (CTA reminder if LP CTA not taken) | **+24 h** if `booked_call ≠ true` | Still warm, not yet sceptical |
| Email 3 (false-belief teardown) | **+3 days** | Time for the first emotional reaction to settle |
| Email 9 (ROI math) | **+16 days** | After they've seen 8 different angles |

Hard rule: if `booked_call = true` at any point, **stop the drip**. Continuing post-conversion damages trust.

### 4d. Single-funnel measurement

Track the combined funnel as ONE pipe, not two:

```
LP visit → opt-in → drip-engaged (≥3 opens) → call-booked → showed → closed
```

Per-stage benchmark to watch:
- LP visit → opt-in: 5-15 % (b2b SMB cold traffic)
- Opt-in → drip-engaged (≥3 opens of 12): 35-55 %
- Drip-engaged → call-booked: 8-18 %
- Call-booked → showed: 60-75 %
- Showed → closed: 15-30 %

If LP→opt-in is <3 % the LP is wrong (foundation issue). If opt-in→drip-engaged is <30 % the voice handoff (4b) is broken.

### 4e. Failure modes (catch in QC, not in production)

- **Register switch** — LP says "Du", drip Email 1 switches to "Sie" (or vice versa). Common when two different writers or two different fork sessions produced the assets.
- **Promise unkept** — LP CTA says "free benchmark guide", drip never sends it. Always send the LP-promised asset in Email 1, even if it's a one-pager.
- **Foundation drift** — LP and drip drew from different versions of the foundation CSV. Lock to one version + cite the version timestamp in both files' headers.
- **Tracking fragmentation** — LP analytics in tool A, drip analytics in tool B, no joined view. Define the joined funnel before launch.

## Step 5 — Pre-launch checklist

- [ ] Form-to-drip data contract documented + matches both asset specs
- [ ] LP hero pull-quote echoes inside drip Email 1
- [ ] LP CTA promise (e.g. free guide) is actually delivered in drip Email 1
- [ ] LP `{DU_OR_SIE}` register matches drip throughout (no mid-funnel switch)
- [ ] `booked_call = true` triggers drip-stop (mechanical, not manual)
- [ ] Joined funnel-stage tracking live before traffic hits the LP

## Final Quality Check (run before delivering output)

- [ ] **Language consistency** — every cell/section uses the operator's specified `{LANGUAGE}` (no mixing).
- [ ] **Umlaut integrity (German output only)** — verify zero ASCII-substitutions of umlauts. Run:
      `grep -c "ä\|ö\|ü\|ß" output.md` (should be > 0 for any non-trivial DE output)
      `grep -cE "(fuer|ueber|muessen|koennen|haette|wuerde|aendern|groesse|Geschaefts|Auftraege|Beschaeftigte)" output.md` (should be 0)
- [ ] **Voice consistency** — direct quotes in pain rows are tagged with source. Zero invented quotes.
- [ ] **Ansprache lock (DE)** — Du or Sie chosen explicitly and applied throughout. Mixed register kills credibility.
- [ ] **No GPT-language** — strip "leverage", "synergize", "unlock", "streamline", "delve", "ecosystem", "skalieren".
- [ ] **No fabricated stats** — every number has a source citation; if unverifiable, mark `[needs validation]`.
