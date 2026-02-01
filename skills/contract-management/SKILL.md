# Contract Management

Send contracts for e-signature, track their status in real time, and follow up on unsigned agreements — keeping every deal moving from proposal to signed.

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                   CONTRACT MANAGEMENT                            │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You tell me: client, contract details, status                │
│  ✓ Generate contract checklist and signing instructions          │
│  ✓ Track contract status manually (sent/viewed/signed)          │
│  ✓ Draft follow-up emails for unsigned contracts                │
│  ✓ Pipeline status recommendations                              │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + E-signature: Create envelope, send for signing, track events │
│  + CRM: Auto-update pipeline status per signing event           │
│  + Chat: Real-time notifications for views, signs, declines     │
│  + Email: Send gentle follow-ups for unopened contracts          │
└─────────────────────────────────────────────────────────────────┘
```

---

## Getting Started

**Required:**
- Client name and company
- What action you need (send contract, check status, follow up on unsigned)

**Helpful if you have it:**
- Proposal or contract document (PDF or link)
- Signer name and email
- Contract terms (amount, duration, payment schedule)
- When the contract was sent (if checking status)

If CRM is connected, I'll pull client data and contract history automatically.

---

## Connectors (Optional)

| Connector | What It Adds |
|-----------|--------------|
| **~~e-signature** | Create envelopes, set signature fields, send for signing, check status |
| **~~CRM** | Update pipeline status per signing event, store envelope IDs |
| **~~chat** | Real-time notifications for each contract event |
| **~~email** | Send follow-up nudges for unsigned contracts |

> **No connectors?** I'll prepare everything for you to manually create the signing envelope, track status, and draft follow-up emails when needed.

---

## Contract Lifecycle

```
Proposal Approved
       │
       ▼
  ┌─────────┐     ┌──────────┐     ┌────────┐     ┌────────┐
  │  SENT   │────▶│ DELIVERED│────▶│ VIEWED │────▶│ SIGNED │
  └─────────┘     └──────────┘     └────────┘     └────────┘
       │                                │               │
       │                                │               ▼
       │                                │          Invoice
       │                                │          (WF 06)
       │                                ▼
       │                          ┌──────────┐
       │                          │ DECLINED │
       │                          └──────────┘
       │
       ▼ (30 days, no action)
  ┌─────────┐
  │ EXPIRED │
  └─────────┘
```

### Pipeline Status Mapping

| Contract Event | CRM Status | Team Action |
|---------------|------------|-------------|
| Envelope sent | Contract Sent | Inform team |
| Email delivered | Contract Sent | No action needed |
| Recipient viewed | Contract Opened | Encouraging — hold tight |
| Recipient signed | Contract Signed | Trigger invoice workflow |
| Recipient declined | Contract Declined | Urgent — reach out immediately |
| 3+ days no open | Contract Sent (stale) | Send follow-up nudge |
| 30 days expired | Contract Expired | Re-evaluate deal |

---

## Sending a Contract

### Envelope Setup

When creating a new contract for signing:

```markdown
## Contract Ready to Send

**Client:** [Company Name]
**Signer:** [Name] — [Email]
**Document:** [Proposal PDF / Contract template]

### Envelope Configuration
- **Subject line:** "Your proposal from [Your Company] is ready to review"
- **Email message:** Personalized with company name and project reference
- **Signing order:** Single signer (or sequential if multiple)
- **Expiration:** 30 days from send date
- **Reminders:** Auto-remind at Day 3, Day 7, Day 14

### Signature Fields
- Signature (required)
- Date signed (required)
- Printed name (required)
- Title (required)
- Company name (optional, pre-filled)
- Initials (if multi-page)

### Pre-Send Checklist
- [ ] Correct signer name and email
- [ ] Document is final version (no tracked changes or comments)
- [ ] Pricing matches what was discussed
- [ ] Terms are current
- [ ] Signature fields are properly placed
```

---

## Event Tracking

When a contract event occurs, I generate the appropriate notification:

### Contract Sent
```
Contract sent to [Name] at [Company]
Document: [Contract name]
Sent: [Date/time]
Expires: [Date]
Status: Waiting for recipient
```

### Contract Viewed
```
[Name] at [Company] opened the contract
First viewed: [Date/time]
Views: [Count]
Time spent: [Duration if available]
Status: Reviewing — hold tight, don't follow up yet
```

### Contract Signed
```
CONTRACT SIGNED: [Company Name]

Signer: [Name]
Signed: [Date/time]
Document: [Contract name]

Next steps:
1. Download signed copy
2. Update CRM → "Contract Signed"
3. Trigger invoice generation
4. Send welcome / onboarding email
```

### Contract Declined
```
CONTRACT DECLINED: [Company Name]

Signer: [Name]
Declined: [Date/time]
Reason: [If provided]

URGENT — Recommended actions:
1. Reach out within 1 hour
2. Ask what concerns they have
3. Offer to revise terms if applicable
4. If deal is dead, move to Lost and note reason
```

---

## Unopened Contract Follow-Up

For contracts that haven't been opened after 3+ days:

### Monitoring Rules

| Days Since Sent | Action |
|----------------|--------|
| 3 days | First gentle follow-up |
| 7 days | Second follow-up, suggest a call |
| 14 days | Direct follow-up, ask if timing is wrong |
| 21 days | Final attempt before expiry warning |
| 30 days | Expired — close or re-send |

### Follow-Up Email Templates

**Day 3 — Gentle nudge:**
```
Subject: Checking in on your proposal

Hi [First Name],

I sent over our proposal a few days ago and wanted to make sure
it landed in your inbox. Sometimes these end up in spam.

If you have any questions as you review it, I'm happy to hop on
a quick call to walk through anything.

[Your name]
```

**Day 7 — Offer help:**
```
Subject: Any questions on the proposal?

Hi [First Name],

Wanted to follow up on the proposal I sent last week. I know
things get busy — if it's easier, we could do a quick 15-minute
call to walk through it together.

Would [day] or [day] work for you? [Calendar link]

[Your name]
```

**Day 14 — Direct check-in:**
```
Subject: Still interested in moving forward?

Hi [First Name],

I wanted to check in on the proposal from a couple weeks ago.
Totally understand if the timing isn't right — just let me know
either way so I can plan accordingly.

If priorities have shifted, no hard feelings. And if you're still
interested but need something adjusted in the proposal, I'm
happy to revise.

[Your name]
```

---

## Execution Flow

### Sending a Contract

**If e-signature connected:**
```
1. Pull client data (CRM or user input)
2. Create envelope with document and signer details
3. Set signature fields and expiration
4. Send envelope
5. Store envelope ID in CRM
6. Notify team via chat
7. Update pipeline: "Contract Sent"
```

**If no e-signature:**
```
1. Generate pre-send checklist
2. Format envelope setup instructions
3. User creates envelope manually
4. Track status based on user updates
```

### Monitoring Status

**If e-signature connected:**
```
1. Check envelope status via API
2. Route events to appropriate notifications
3. Update CRM pipeline per event
4. Alert team per event type
```

**If no e-signature:**
```
1. Ask user for current status
2. Recommend next action based on timeline
3. Draft follow-up emails as needed
```

### Handling Unopened Contracts

```
1. Identify contracts sent 3+ days ago with no views
2. Draft appropriate follow-up based on days elapsed
3. Suggest channel (email, phone, chat)
4. If chat connected, alert team with suggested action
```

---

## Tips

1. **Send contracts immediately after approval** — Every day of delay reduces signing probability
2. **Personalize the envelope email** — A generic "please sign this document" converts worse than a personalized message
3. **Don't follow up too soon** — Give them at least 3 business days before the first nudge
4. **Track views carefully** — If they've viewed it 5 times without signing, they may have questions. Reach out proactively
5. **Have a plan for declines** — Don't panic. Ask what the concern is. Most declines are about specific terms, not the entire deal

---

## Related Skills

- **proposal-assembly** — Build the proposal that becomes the contract
- **invoice-tracking** — After signing, generate and track the invoice
- **nurture-sequences** — If the contract expires, consider re-entering the lead into nurture
