# /nurture-status

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Check the status of your nurture sequences — who's being nurtured, what stage they're at, what's due next, and who's showing re-engagement signals.

## Usage

```
/nurture-status
```

Optionally ask about a specific lead: `/nurture-status` then "What's the status for Sarah at Acme?"

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                     NURTURE STATUS                               │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ Review all leads currently in nurture                        │
│  ✓ Show stage, last touch, and next action for each             │
│  ✓ Identify leads showing re-engagement signals                 │
│  ✓ Flag leads ready to exit nurture                             │
│  ✓ Draft next nurture email for any lead                        │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + ~~CRM: Pull all leads in nurture with dates and activity    │
│  + ~~chat: Post nurture review to team channel                  │
│  + ~~email: Check open rates, replies, engagement data          │
└─────────────────────────────────────────────────────────────────┘
```

---

## What I Need From You

**If CRM is connected:** Nothing — I'll pull all nurture data automatically.

**If no CRM:** Tell me about the leads you're nurturing:
- Who they are
- What stage they're at (or when you last contacted them)
- Any recent activity

---

## Output

```markdown
# Nurture Status — [Date]

## Active Nurture Pipeline

| Lead | Company | Stage | Last Touch | Next Action | Due |
|------|---------|-------|-----------|-------------|-----|
| [Name] | [Co] | Stage 1 (Day 3) | [Date] | Value-add email | [Date] |
| [Name] | [Co] | Stage 2 (Day 7) | [Date] | Deeper insight | [Date] |
| [Name] | [Co] | Stage 3 (Day 14) | [Date] | Check-in | Today |
| [Name] | [Co] | Stage 4 (Day 30) | [Date] | Re-engagement | [Date] |
| [Name] | [Co] | Stage 5 (60+) | [Date] | Quarterly touch | [Date] |

**Total in nurture:** [N] leads

---

## Needs Action Today

- **[Name]** ([Company]) — Stage 3 check-in due today
- **[Name]** ([Company]) — Stage 2 deeper insight due today

---

## Re-Engagement Signals

- **[Name]** — Opened Stage 1 email 3 times in 2 days → Consider calling
- **[Name]** — Visited website after Stage 2 email → Warm signal

---

## Ready to Exit

- **[Name]** — Replied to Stage 3 → Route to team for follow-up
- **[Name]** — Booked meeting → Move to discovery prep
- **[Name]** — No opens on 3 emails, 60+ days → Suggest moving to dormant

---

## Summary

| Metric | Count |
|--------|-------|
| Total in nurture | [N] |
| Due this week | [N] |
| Showing engagement | [N] |
| Recommend exit | [N] |
```

---

## If Connectors Available

**~~CRM connected:** Pull all leads with nurture status, dates, and stage data.
**~~email connected:** Check email open rates, click-through, and reply activity.
**~~chat connected:** Post nurture review summary to team channel.

---

## Tips

1. **Run this daily or weekly** — Prevents leads from falling through the cracks
2. **Act on re-engagement signals fast** — Multiple email opens or website visits mean they're thinking about you
3. **Exit gracefully** — When someone replies, exit nurture and respond personally
4. **Don't let leads sit in Stage 5 forever** — If there's no engagement after 90+ days, move to dormant
