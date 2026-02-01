# Lead Capture

Capture leads from any source — web forms, events, referrals, CSV imports, or manual entry — and route them into your pipeline with AI-powered qualification scoring.

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                       LEAD CAPTURE                               │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You tell me: name, company, email, how you met them         │
│  ✓ AI qualification scoring (Hot / Warm / Cold)                 │
│  ✓ Structured lead record with all captured data                │
│  ✓ Auto-reply email draft for immediate acknowledgment          │
│  ✓ Team notification summary with recommended next steps        │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + CRM: Auto-create lead record, check for duplicates           │
│  + Chat: Post lead card to team channel with action buttons     │
│  + Email: Send auto-reply acknowledgment immediately            │
│  + Data enrichment: Pull company info, LinkedIn, funding data   │
└─────────────────────────────────────────────────────────────────┘
```

---

## Getting Started

When this skill activates, I'll ask for what I need:

**Required:**
- Contact name
- Email address

**Helpful if you have it:**
- Company name
- Phone number
- How you met them (web form, event, referral, cold outreach)
- Their message or what they said
- Any urgency signals ("need this ASAP", "evaluating vendors this week")

If you've connected your CRM, I'll check for duplicate records before creating a new entry.

---

## Connectors (Optional)

| Connector | What It Adds |
|-----------|--------------|
| **~~CRM** | Create lead record, check duplicates, enrich with existing account data |
| **~~chat** | Post structured lead card to team channel (#leads or equivalent) |
| **~~email** | Send auto-reply acknowledgment to the lead |

> **No connectors?** No problem. I'll create a structured lead profile you can copy into your CRM manually, draft the auto-reply for you to send, and format a team notification you can paste into your chat.

---

## Lead Capture Sources

This skill handles multiple capture methods:

### 1. Manual Entry
You tell me about someone you met. I structure the data and score them.

### 2. Event / Meetup Capture
Quick capture at networking events. Provide minimal info (name + company or name + email) and I'll enrich the rest. Include the event name for personalized follow-up.

### 3. Batch Import
Paste a list of contacts (CSV format, bullet list, or even a photo of business cards) and I'll parse, deduplicate, and score each one. Especially useful after conferences or networking events.

### 4. Web Form Submission
If your form data is available (pasted or from a connected tool), I'll parse all fields automatically.

---

## AI Lead Scoring

Every captured lead gets a qualification score based on multiple factors:

| Factor | Hot Signal | Warm Signal | Cold Signal |
|--------|-----------|-------------|-------------|
| **Urgency** | "ASAP", "this week", "evaluating now" | "next quarter", "exploring" | No timeline mentioned |
| **Company size** | 10-500 employees (sweet spot for services) | 1-10 or 500+ | Unknown |
| **Source quality** | Referral, inbound form, returning lead | Event, conference | Cold list, unknown |
| **Service interest** | Specific need mentioned | General interest | Vague or no interest |
| **Budget signals** | Budget mentioned or implied | "Need to check budget" | "Not sure about budget" |
| **Engagement** | Asked questions, requested follow-up | Exchanged cards, brief chat | Passive interaction |

**Scoring output:**
- **Hot** — High urgency + clear need + good fit. Route for immediate follow-up.
- **Warm** — Interest present but timing or fit unclear. Schedule follow-up within a week.
- **Cold** — Low signals. Enter nurture sequence.

---

## Output Format

### Lead Card (for team notification)

```markdown
## New Lead: [Name] — [Company]

| Field | Value |
|-------|-------|
| **Name** | [Full name] |
| **Email** | [Email] |
| **Phone** | [Phone if provided] |
| **Company** | [Company name] |
| **Source** | [How captured: Website / Event / Referral / Cold] |
| **Event** | [Event name if applicable] |
| **Score** | [Hot / Warm / Cold] |
| **Status** | New Lead |
| **First Contact** | [Today's date] |

### Scoring Rationale
[2-3 sentences explaining the score — what signals were present or absent]

### Message / Context
> [Their message, what they said, or context from the interaction]

### Recommended Next Steps
1. [Immediate action based on score]
2. [Follow-up timeline]
3. [What to prepare]
```

### Auto-Reply Email Draft

```
Subject: Thanks for reaching out, [First Name]

Hi [First Name],

Thank you for [connecting at EVENT / reaching out through our website / the referral from PERSON]. We're glad to hear from you.

[1-2 sentences acknowledging their specific interest or situation]

Someone from our team will be in touch within 24 hours to learn more about what you're looking for and see how we can help.

In the meantime, feel free to reply to this email with any questions.

Talk soon,
[Your team]
```

---

## Execution Flow

### Step 1: Parse Input

**Manual capture:**
```
1. Extract: name, email, phone, company from what user provides
2. Identify source type (event, referral, form, cold)
3. Note any context or messages
```

**Batch import:**
```
1. Parse CSV, bullet list, or unstructured text
2. Identify columns / fields: name, email, company, phone, notes
3. Deduplicate within batch (by email)
4. Count total and flag any parsing issues
```

### Step 2: Enrich & Score

```
1. Web search: "[Company] + industry / funding / size" for context
2. Check for urgency signals in message or notes
3. Evaluate all scoring factors
4. Assign Hot / Warm / Cold
5. Generate scoring rationale
```

### Step 3: Create Records

**If CRM connected:**
```
1. Check for existing record (search by email)
2. If exists: update with new interaction, flag as returning lead
3. If new: create record with all fields
4. Set status: "New Lead"
5. Set first contact date
```

**If no CRM:**
```
1. Format structured lead card (markdown)
2. Present for manual entry
```

### Step 4: Notify & Follow Up

**If chat connected:**
```
1. Post lead card to team channel
2. Include score, context, and recommended next steps
3. Tag relevant team members based on score
   - Hot → tag owner/closer immediately
   - Warm → tag for next-day follow-up
   - Cold → auto-enter nurture (if connected)
```

**If email connected:**
```
1. Send auto-reply acknowledgment
2. Personalize based on source (event name, referral name, etc.)
```

**If no connectors:**
```
1. Present lead card for manual copy
2. Present auto-reply draft for manual send
3. Suggest posting to team channel
```

---

## Tips

1. **More context = better scoring** — "Met Sarah at TechCrunch Disrupt, she runs ops at a 50-person fintech and needs help with onboarding automation" scores much better than just "Sarah, sarah@company.com"
2. **Include the event name** — For event captures, this enables personalized follow-up ("Great meeting you at [event]")
3. **Batch early** — After a conference, paste your contacts while context is fresh. Notes like "interested in API integrations" dramatically improve scoring
4. **Check for duplicates** — If CRM is connected, I'll check automatically. Otherwise, mention if you think you've captured this person before

---

## Related Skills

- **discovery-prep** — After capturing a hot lead and booking a call, prepare for the meeting
- **post-call-followup** — After the discovery call, process the transcript and draft follow-up
- **nurture-sequences** — Cold and warm leads enter automated nurture cadences
