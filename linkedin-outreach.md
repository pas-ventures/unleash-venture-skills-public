# LinkedIn Outreach Skill

## When to Use
- "Run LinkedIn outreach for [campaign]"
- "Send connection requests to [target list]"
- "Draft LinkedIn DMs for [audience]"
- Building a founder/prospect pipeline via LinkedIn

## Overview
Systematic LinkedIn outreach workflow: build target lists, draft personalized connection requests and DM sequences, track pipeline progress, and stay within LinkedIn's safety limits. Works with manual sends (safest) or optional automation via LinkedAPI MCP.

---

## LinkedIn Rate Limits & Safety (2026)

### Hard Limits
- **Connection requests**: ~100/week (recommended: stay under 80/week, 20/day max)
- **DMs**: ~50/day to connections, fewer to non-connections (InMail credits)
- **Profile views**: ~80-100/day
- **Searches**: ~30 commercial searches/month (free), unlimited with Sales Navigator

### Safety Rules
1. **Max 20 connection requests per day** (stay under 80/week)
2. **Max 50 DMs per day** (to existing connections only)
3. **Always personalize** — no copy-paste spam. Every message must reference something specific about the target
4. **Review and approve each batch before sending** — never auto-send
5. **Never scrape profiles at scale** — only look up targets you intend to contact
6. **Gradual warm-up** — start with 5-10/day, increase over 2 weeks to max 20/day
7. **Space actions** — minimum 2-minute gaps between actions, spread across the day
8. **Monitor for restrictions** — if LinkedIn shows any warning, stop immediately for 1 week

### TOS Risks
- LinkedIn explicitly prohibits third-party automation tools in their User Agreement
- ~23% of browser-extension automation users face restrictions within 90 days
- Cloud-browser tools are harder to detect than extensions but still violate TOS
- First offense: usually temporary restriction (1 week). Repeated: permanent ban
- **Your LinkedIn is a high-value asset** — losing it would be catastrophic for deal flow

### Mitigation
- Keep daily volumes LOW (15-20 connection requests, not 50+)
- Always personalize messages (no identical copy-paste)
- Warm up gradually (don't go from 0 to 20/day overnight)
- Space actions throughout the day (not 20 requests in 5 minutes)
- Review every batch before sending

---

## Outreach Workflow

### Step 0: Build Your Target List
Before starting outreach, you need a target list. Ways to build one:
- **Sales Navigator** (best): Filter by industry, company size, role, geography. Export to CSV.
- **LinkedIn Search** (free): Search `"{role}" "{industry}" "{city/region}"`, manually compile top results.
- **Event attendees**: Conference speaker lists, webinar registrants, industry association member directories.
- **Competitor followers**: Check who follows/engages with competitors' LinkedIn pages.
- **CRM enrichment**: Pull existing contacts who match your ICP but aren't connected on LinkedIn.

Aim for 50-100 targets per campaign wave. Prioritize quality over volume.

### Prerequisites
- Target list in CSV or project management tool (ClickUp, Linear, Notion, etc.)
- Message templates drafted and approved
- If using automation: LinkedAPI account configured (see Automation section below)

### Step 1: Prepare Batch
1. Pull next batch of targets (max 15-20 per day)
2. For each target, research their profile (name, company, role, recent activity)
3. Draft personalized connection request note (max 300 chars on LinkedIn)
4. Present batch for review and approval

### Step 2: Send Connection Requests
- **Manual (recommended)**: Present copy-paste-ready messages, send from LinkedIn
- **With LinkedAPI MCP**: Use `send_connection_request` tool for each approved target
- Log each send with timestamp in your tracking system

### Step 3: Track Accepts (daily/weekly check)
- **With LinkedAPI MCP**: Use `check_connection_status` for pending requests
- **Manual**: Check LinkedIn notifications, report accepts
- Update tracking (status: sent / accepted / declined / no response)

### Step 4: Follow-Up DM Sequence (after accept)
3-message sequence over 2 weeks:

**DM 1 (Day 0 — immediately after accept):**
Thank them for connecting. Reference something specific from their profile. Ask a genuine question about their work. No pitch.

**DM 2 (Day 5-7):**
Share something relevant (article, insight, case study). Build credibility. Mention what you're working on casually. Still no ask.

**DM 3 (Day 12-14):**
Suggest a quick call. Be specific about what you'd like to discuss. Make it easy to say yes (offer 2-3 time slots).

**No-Reply Handling:**
- If no reply to DM 1 after 7 days → send DM 2 anyway (they may have seen it but not responded)
- If no reply to DM 2 after 7 days → send a short final message: "Kein Stress — wollte nur sichergehen, dass es nicht untergegangen ist. Falls Timing gerade nicht passt, melde dich gern wenn's soweit ist." Then move to "parked" status.
- If no reply to DM 3 → move to "closed - no response". Do NOT send more messages.
- **Never send more than 4 total DMs without a reply.** Respect silence.

### Step 5: Sync to Pipeline
Update your CRM / pipeline tasks:
- Connection request sent date
- Accept date
- DM sequence progress (DM1 sent, DM2 sent, DM3 sent)
- Call scheduled / completed
- Outcome (interested, not now, declined, parked, closed - no response)

### Campaign Metrics (track weekly)
| Metric | Formula | Healthy Benchmark |
|--------|---------|-------------------|
| Accept rate | Accepts / Requests sent | 25-40% |
| DM1 reply rate | DM1 replies / DMs sent | 15-25% |
| Call conversion | Calls booked / DM3 sent | 5-15% |
| Overall pipeline | Calls booked / Requests sent | 2-5% |

---

## Automation Options (Optional)

### Option 1: LinkedAPI.io MCP (Best for outreach automation)
- Cloud-browser-based LinkedIn automation exposed via MCP
- Tools: `send_connection_request`, `send_message`, `get_conversation`, `check_connection_status`, `withdraw_connection_request`
- Pricing: Core $69/seat/month ($49 annual)
- MCP setup: Remote MCP server via URL — no npm install needed
- **Pros**: Purpose-built for outreach, supports connection requests + DMs
- **Cons**: Monthly cost, third-party holds your LinkedIn session, TOS risk

### Option 2: Read-Only MCP (Research only)
- `stickerdaniel/linkedin-mcp-server` — scrape profiles and companies via browser automation
- Good for researching targets, NOT for sending messages
- Tools: Get person profile, get company profile, search jobs

### Option 3: Manual + CRM Tracking (Safest)
- No MCP needed. Send connection requests and DMs manually from LinkedIn
- AI drafts personalized messages for copy-paste
- Track everything in your project management tool
- Zero TOS risk, zero cost

**Recommendation**: Start with Option 3 (manual + tracking). Only move to LinkedAPI if you need volume > 10/day consistently and accept the TOS risk.

---

## Connection Request Templates

### Template A: Peer / Founder Angle
```
Hi {first_name}, ich sehe dass du {company} aufbaust — spannend!
Ich arbeite an ähnlichen Themen im {industry} Bereich.
Würde mich freuen, mich zu vernetzen. {your_name}
```

### Template B: Mutual Interest Angle
```
{first_name}, dein Beitrag zu {topic} hat mich angesprochen.
Bin selbst im Bereich {your_area} unterwegs und sehe
viele Parallelen. Vernetzen wir uns? {your_name}
```

### Template C: Event / Content Angle
```
Hi {first_name}, habe deinen Talk bei {event} / deinen Post
zu {topic} gesehen — starke Insights. Würde mich freuen,
mich auszutauschen. {your_name}
```

**Rules for connection requests:**
- Max 300 characters (German runs long — draft, then trim. Aim for 250 chars to leave margin)
- Always personalize (reference their content, company, or mutual interest)
- Never pitch in the connection request
- Sign with first name only

---

## Quality Checklist
- [ ] Every message references something specific about the target
- [ ] No copy-paste spam — each message is personalized
- [ ] Daily volume under 20 connection requests
- [ ] Batch approved before sending
- [ ] Pipeline tracking updated after each action
- [ ] DM sequence follows 3-message cadence (no pitch until DM3)
- [ ] Templates adapted to the specific campaign angle

## Customization Checklist
Before using, replace these placeholders:
- `{your_name}` — Your first name
- `{your_area}` — Your domain/industry
- `{company}` — Target's company (personalized per message)
- `{TRACKING_TOOL}` — Your CRM or project management tool (ClickUp, Linear, Notion, etc.)

## Hand-off — what to consume from upstream
- **Connection request** ← Asset Foundation Row 1 (Position) + Row 2 (Deepest Desires) — keep it 250 chars
- **DM 1 (warmth)** ← Row 6 (Tried-but-failed) + Row 11 (peer reference)
- **DM 2 (insight)** ← Row 7 (Trends) + Row 12 (Auxiliary)
- **DM 3 (CTA)** ← Row 9 (Solution) + Row 10 (Bodacious Claim, framed as low-commitment ask)

Run `asset-foundation-builder.md` first.
