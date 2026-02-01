# /prep-call

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Prepare for an upcoming discovery or sales call with company research, attendee backgrounds, a suggested agenda, and discovery questions.

## Usage

```
/prep-call
```

Then tell me who you're meeting with, or I'll check your calendar.

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                        PREP CALL                                 │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You tell me: company, meeting type, attendees                │
│  ✓ Web research: company info, news, leadership                 │
│  ✓ Meeting brief with agenda and discovery questions            │
│  ✓ Objection anticipation based on context                      │
│  ✓ Pre-meeting email sequence drafts                            │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + ~~calendar: Auto-find meeting, pull attendees                │
│  + ~~CRM: Lead history, prior interactions, score               │
│  + ~~email: Send confirmation + questionnaire + reminder        │
│  + ~~conversation intelligence: Pull prior call recordings      │
└─────────────────────────────────────────────────────────────────┘
```

---

## What I Need From You

**Required:**
- Company or contact name
- When the meeting is (or "tomorrow at 2pm")

**Helpful but optional:**
- Attendee names and titles
- What you know about them so far
- What you want to accomplish in the meeting

**If calendar is connected:** I'll find the meeting and pull attendees automatically.

---

## Output

### Meeting Brief

```markdown
# Call Prep: [Company Name]

**Meeting:** [Type] — [Date] at [Time]
**Attendees:** [Names with titles]
**Your Goal:** [What you want to accomplish]

## Company Snapshot
| Field | Value |
|-------|-------|
| Company | [Name] |
| Industry | [Industry] |
| Size | [Employees] |
| What they do | [1-2 sentences] |

## Who You're Meeting
### [Name] — [Title]
- Background: [Career summary]
- Role in decision: [Decision maker / Influencer / Evaluator]
- Talking point: [Something to reference in conversation]

## What We Know
- Source: [How they found us]
- Score: [Hot / Warm / Cold]
- Key context: [Form message, prior interactions, referral info]

## Suggested Agenda
1. Open (5 min) — [Reference point]
2. Their world (10 min) — [What to explore]
3. Bottlenecks (10 min) — [Where to dig]
4. Quick wins (5 min) — [What to share]
5. Next steps (5 min) — [What to propose]

## Discovery Questions
1. [Tailored to their situation]
2. [Based on their industry]
3. [Focused on their likely pain points]

## Potential Objections
| Objection | Response |
|-----------|----------|
| [Likely concern] | [How to address it] |
```

### Pre-Meeting Email Sequence
- **Email 1 (now):** Confirmation + "what to expect"
- **Email 2 (T-24h):** Prep questionnaire (7 key questions)
- **Email 3 (T-1h):** Reminder + meeting link + agenda

---

## If Connectors Available

**~~calendar connected:** Auto-find the meeting, pull attendees and description.
**~~CRM connected:** Pull lead record, score, form submission, prior interactions.
**~~email connected:** Send the 3-email pre-meeting sequence automatically.
**~~conversation intelligence connected:** Pull prior call recordings for returning leads.

---

## Tips

1. **Run this as soon as the meeting is booked** — The confirmation email should go out immediately
2. **Include any context you have** — Prior emails, form data, referral info all improve the brief
3. **Review questionnaire responses** before the call — They're your best prep material
4. **Adapt the agenda** for returning leads — Skip basics, go deeper on their specific needs
