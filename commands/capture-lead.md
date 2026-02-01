# /capture-lead

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Quickly capture a new lead from any source — paste their info, describe how you met them, or import a batch of contacts.

## Usage

```
/capture-lead
```

Then provide the lead's information (name, email, company, context).

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                      CAPTURE LEAD                                │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ Parse lead info from whatever you provide                    │
│  ✓ AI qualification scoring (Hot / Warm / Cold)                 │
│  ✓ Structured lead card for your team                           │
│  ✓ Auto-reply email draft                                       │
│  ✓ Recommended next steps based on score                        │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + ~~CRM: Create record, check duplicates                       │
│  + ~~chat: Post lead card to team channel                       │
│  + ~~email: Send auto-reply acknowledgment                      │
└─────────────────────────────────────────────────────────────────┘
```

---

## What I Need From You

**Option 1: Quick capture**
Just tell me the basics: "Sarah Chen, sarah@acme.com, met her at TechCrunch Disrupt, she runs ops at a 50-person fintech."

**Option 2: Paste form data**
If you have form submission data, paste it and I'll parse all fields.

**Option 3: Batch import**
Paste a CSV, bullet list, or table of contacts. I'll process each one, deduplicate, and score them all.

**Option 4: Describe the interaction**
"Just got off a call with someone from Acme Corp — they're looking for automation help, seemed very interested, team of about 30 people."

---

## Output

### Lead Card

```
## New Lead: [Name] — [Company]

| Field | Value |
|-------|-------|
| Name | [Full name] |
| Email | [Email] |
| Phone | [If provided] |
| Company | [Company name] |
| Source | [Website / Event / Referral / Cold] |
| Score | [Hot / Warm / Cold] |
| Status | New Lead |

### Scoring Rationale
[Why this score — what signals were present]

### Recommended Next Steps
1. [Immediate action]
2. [Follow-up timeline]
```

### Auto-Reply Draft

```
Subject: Thanks for reaching out, [First Name]

Hi [First Name],

Thank you for [connecting at EVENT / reaching out]. We're glad
to hear from you.

[Acknowledgment of their specific situation]

Someone from our team will be in touch within 24 hours.

Talk soon,
[Your team]
```

---

## If Connectors Available

**~~CRM connected:**
- Check for existing record (by email)
- Create or update lead record
- Set pipeline status to "New Lead"

**~~chat connected:**
- Post lead card to team channel
- Tag team members based on score (Hot = immediate, Warm = same day)

**~~email connected:**
- Send auto-reply acknowledgment immediately

---

## Tips

1. **More context = better scoring** — Even a sentence about their situation helps
2. **Include the event name** for event captures — enables personalized follow-up
3. **Batch after conferences** — Paste all contacts while memory is fresh
4. **Tell me if they're a referral** — Referrals score higher and get different messaging
