# /pipeline-review

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Get a snapshot of your sales pipeline — deals by stage, stalled leads, conversion metrics, and action items.

## Usage

```
/pipeline-review
```

Optionally specify a time range: `/pipeline-review` for current state, or "pipeline review for January" for a specific period.

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                     PIPELINE REVIEW                              │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You describe your current deals, I analyze the pipeline      │
│  ✓ Stage distribution and bottleneck identification             │
│  ✓ Stalled deal detection with follow-up suggestions            │
│  ✓ Conversion rate analysis                                     │
│  ✓ Prioritized action items for the week                        │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + ~~CRM: Pull all deals, stages, dates, amounts automatically │
│  + ~~chat: Post review summary to team channel                  │
│  + ~~email: Check for recent lead replies or engagement         │
└─────────────────────────────────────────────────────────────────┘
```

---

## What I Need From You

**If CRM is connected:** Nothing — I'll pull everything automatically.

**If no CRM:** Tell me about your current deals:
- Who's in the pipeline
- What stage each deal is at
- How long they've been at that stage
- Any notable activity or blockers

---

## Output

```markdown
# Pipeline Review — [Date]

## Pipeline Snapshot

| Stage | Count | Total Value | Avg Days in Stage |
|-------|-------|-------------|-------------------|
| New Lead | [N] | — | [N] |
| Contacted | [N] | — | [N] |
| Discovery Scheduled | [N] | $[Value] | [N] |
| Discovery Complete | [N] | $[Value] | [N] |
| Proposal Sent | [N] | $[Value] | [N] |
| Contract Sent | [N] | $[Value] | [N] |
| Contract Signed | [N] | $[Value] | [N] |
| Paid | [N] | $[Value] | — |

**Total pipeline value:** $[Sum of active deals]
**Weighted forecast:** $[Probability-adjusted value]

---

## Stalled Deals (Needs Attention)

| Lead | Company | Stage | Days Stalled | Suggested Action |
|------|---------|-------|-------------|------------------|
| [Name] | [Co] | Discovery Complete | 12 days | Send proposal or re-engage |
| [Name] | [Co] | Contract Sent | 8 days | Check if contract was opened |
| [Name] | [Co] | New Lead | 5 days | First contact overdue |

---

## Conversion Metrics

| Transition | Rate | Avg Time |
|-----------|------|----------|
| Lead → Contacted | [%] | [N] days |
| Contacted → Discovery | [%] | [N] days |
| Discovery → Proposal | [%] | [N] days |
| Proposal → Contract | [%] | [N] days |
| Contract → Signed | [%] | [N] days |
| Signed → Paid | [%] | [N] days |
| **Overall: Lead → Paid** | **[%]** | **[N] days** |

---

## This Week's Action Items

1. **[Priority]** [Action] — [Lead/Company] — [Why now]
2. **[Priority]** [Action] — [Lead/Company] — [Why now]
3. **[Priority]** [Action] — [Lead/Company] — [Why now]
4. **[Priority]** [Action] — [Lead/Company] — [Why now]
5. **[Priority]** [Action] — [Lead/Company] — [Why now]

---

## Revenue Summary

| Metric | This Month | Last Month | Trend |
|--------|-----------|------------|-------|
| Deals closed | [N] | [N] | [↑/↓/→] |
| Revenue collected | $[Amt] | $[Amt] | [↑/↓/→] |
| New leads captured | [N] | [N] | [↑/↓/→] |
| Proposals sent | [N] | [N] | [↑/↓/→] |
```

---

## If Connectors Available

**~~CRM connected:**
- Pull all leads with current status, dates, and deal values
- Calculate conversion rates from historical data
- Identify stalled deals automatically (no activity for X days)

**~~chat connected:**
- Post review summary to team channel
- Tag team members next to their action items

---

## Tips

1. **Run this weekly** — A regular pipeline review prevents deals from going stale
2. **Focus on stalled deals first** — The deals closest to closing but not moving are your highest-leverage actions
3. **Track velocity** — If your average time from discovery to proposal is increasing, that's a signal to investigate
4. **Use the action items** — The review is only useful if you act on it. Pick the top 3 actions and do them today
