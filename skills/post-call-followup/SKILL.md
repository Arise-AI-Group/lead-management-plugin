# Post-Call Follow-Up

Process call notes or transcripts to extract key insights, draft a personalized follow-up email, and update your pipeline — all within minutes of hanging up.

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                   POST-CALL FOLLOW-UP                            │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ Paste call notes, transcript, or describe what happened      │
│  ✓ Extract: pain points, objections, next steps, budget signals │
│  ✓ Draft personalized follow-up email (150-250 words)           │
│  ✓ Generate internal team summary with deal impact              │
│  ✓ Recommend pipeline stage update                              │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + Transcripts: Pull recording automatically from Fireflies/Gong│
│  + CRM: Update lead record, log activity, advance pipeline      │
│  + Chat: Route follow-up for team review with approve/send      │
│  + Email: Send approved follow-up directly                      │
└─────────────────────────────────────────────────────────────────┘
```

---

## Getting Started

**Option 1: Paste a transcript**
If you have a full transcript from Fireflies, Gong, Zoom, or any other tool, paste it. I'll extract everything.

**Option 2: Paste your notes**
Bullet points, rough notes, stream of consciousness — whatever you have. I'll structure it.

**Option 3: Describe the call**
Tell me what happened: "Had a discovery call with Acme Corp. Met with their VP Ops. They're drowning in manual data entry, team of 30, looking to automate onboarding. Budget is ~$5k/month. Want to move fast."

**Helpful context:**
- Who attended (names and titles)
- What type of call (discovery, demo, follow-up, proposal review)
- What you want the follow-up to accomplish

---

## Connectors (Optional)

| Connector | What It Adds |
|-----------|--------------|
| **~~conversation intelligence** | Pull transcript automatically — no pasting needed |
| **~~CRM** | Update lead record, log activity, advance pipeline stage |
| **~~chat** | Route follow-up draft for team review with approve/edit/send buttons |
| **~~email** | Send approved follow-up email directly |

> **No connectors?** I'll analyze whatever you provide, draft the follow-up email and internal summary for you to copy/paste, and tell you what to update in your CRM.

---

## Output Format

### Internal Team Summary

```markdown
## Call Summary: [Company Name] — [Date]

**Attendees:** [Names and titles]
**Call Type:** [Discovery / Demo / Follow-up / Proposal Review]
**Duration:** [If known]

### Key Discussion Points
1. [Topic] — [What was discussed, decisions made]
2. [Topic] — [Summary]
3. [Topic] — [Summary]

### Pain Points Identified
- [Pain point 1] — [How severe, what it costs them]
- [Pain point 2] — [Context]
- [Pain point 3] — [Context]

### Budget & Timeline
- **Budget signals:** [What was said or implied about budget]
- **Timeline:** [Their urgency level and desired start date]
- **Decision process:** [Who decides, how long it takes]

### Objections / Concerns
- [Concern] — [How you addressed it / still open]

### Competitive Intel
- [Any competitor mentions, what was said, how they compare]

### Enthusiasm Level: [High / Medium / Low]
[1-2 sentences explaining the read]

### Action Items
| Owner | Action | Due |
|-------|--------|-----|
| [You/team] | [Task] | [Date] |
| [Client] | [Task] | [Date] |

### Recommended Next Steps
- [What to do next and when]
- Pipeline stage: [Current] → [Recommended]

### Deal Impact
[How this call affects the opportunity — advance, stall, or close risk]
```

### Customer Follow-Up Email

```
Subject: [Great connecting today / Following up on our conversation / Next steps for PROJECT]

Hi [First Name],

[Opening that references something specific from the call — NOT "I hope this finds you well"]

[1-2 sentences summarizing what you discussed and what resonated]

[Key commitments you made — what you're sending, what you'll prepare, timeline]

[Clear next step with a specific ask — calendar link, review request, decision point]

[Warm close]

[Your name]
```

---

## Email Style Guidelines

When drafting follow-up emails:

1. **Reference the actual conversation** — Mention specific things they said, problems they described, or examples they gave. This proves you listened.
2. **Be concise** — 150-250 words. Get to the point. They're busy.
3. **No markdown formatting** — Plain text that looks natural in any email client. No asterisks, bold, or headers.
4. **One clear CTA** — Don't ask for three things. Ask for one thing.
5. **Match their energy** — If they were casual, be casual. If they were formal, be formal.
6. **Send fast** — The follow-up loses impact after 15 minutes. Speed matters.

---

## Transcript Analysis

When processing a full transcript, I extract:

| Category | What I Look For |
|----------|----------------|
| **Pain points** | Problems they described, frustrations expressed, "we struggle with..." |
| **Budget signals** | Dollar amounts, "we spend X on...", budget holder mentions |
| **Timeline** | Urgency cues, deadlines mentioned, "we need this by..." |
| **Decision criteria** | What matters to them, how they'll evaluate options |
| **Objections** | Concerns, hesitations, "but what about...", competitor comparisons |
| **Champions** | Who seemed most enthusiastic, who drove the conversation |
| **Quotable moments** | Phrases that reveal pain — useful for proposals and case studies |
| **Competitive mentions** | Other vendors, current tools, past attempts |
| **Next steps** | What was agreed, who committed to what |

---

## Execution Flow

### Step 1: Gather Call Data

**If transcription service connected:**
```
1. Search for most recent call matching company/contact
2. Pull full transcript
3. Pull attendees, duration, any flagged moments
```

**If no transcription:**
```
1. Accept whatever user provides (transcript, notes, description)
2. Ask clarifying questions only if critical context is missing
```

### Step 2: Analyze

```
1. Process transcript/notes through extraction framework
2. Identify all pain points, signals, and action items
3. Assess enthusiasm level and deal trajectory
4. Determine appropriate pipeline stage
```

### Step 3: Generate Outputs

```
1. Internal team summary (structured markdown)
2. Customer follow-up email (personalized, references specific conversation points)
3. CRM update recommendations (fields to change, notes to add)
```

### Step 4: Route for Review

**If chat connected:**
```
1. Post summary + email draft to team channel
2. Include approve / edit / send buttons
3. Tag the person who ran the call
4. On approval → send email (if email connected)
```

**If CRM connected:**
```
1. Offer to update lead record
2. Advance pipeline stage
3. Log the call as an activity
4. Add extracted pain points and notes
```

**If no connectors:**
```
1. Present email draft for manual send
2. Present summary for team sharing
3. List CRM updates to make manually
```

---

## Tips

1. **Speed is everything** — Run this skill immediately after hanging up. A follow-up sent within 15 minutes dramatically increases close rates.
2. **More context = better follow-up** — Full transcripts produce the best results, but even rough notes work.
3. **Name the attendees** — Helps structure the summary and personalize the email.
4. **Tell me the deal stage** — Helps me tailor the follow-up tone (discovery vs. negotiation vs. check-in).
5. **Flag what mattered** — "The big thing was they need this done before Q3" helps me emphasize the right points.

---

## Related Skills

- **discovery-prep** — Run this before the call to prepare
- **proposal-assembly** — If the call went well and they want a proposal
- **nurture-sequences** — If the lead needs more time, enter them into nurture
- **content-engine** — Repurpose call insights into marketing content
