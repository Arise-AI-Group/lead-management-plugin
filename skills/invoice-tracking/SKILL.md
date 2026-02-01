# Invoice Tracking

Generate invoices, track payments, send reminders, and keep revenue flowing — from contract signature to cash in the bank.

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                     INVOICE TRACKING                             │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You tell me: client, amount, terms, what to invoice for     │
│  ✓ Generate formatted invoice with all required fields          │
│  ✓ Payment reminder drafts at Day 7 / 14 / 30                  │
│  ✓ Revenue tracking and outstanding balance summary             │
│  ✓ Pipeline status recommendations                              │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + Payments: Create invoice, send to client, track payment      │
│  + CRM: Update client status, log revenue, track balances       │
│  + Chat: Notify team on payment received or overdue             │
│  + Email: Send invoice and payment reminders automatically      │
└─────────────────────────────────────────────────────────────────┘
```

---

## Getting Started

**Required:**
- Client name and company
- Invoice amount
- What the invoice is for (services, milestone, retainer)

**Helpful if you have it:**
- Payment terms (Net 15, Net 30, 50/50 split, milestone-based)
- Client billing email (may differ from primary contact)
- Contract reference or proposal number
- Payment method preferences (bank transfer, credit card, etc.)
- Tax requirements (tax ID, applicable rates)

If CRM is connected, I'll pull client data, contract details, and prior invoice history automatically.

---

## Connectors (Optional)

| Connector | What It Adds |
|-----------|--------------|
| **~~payments** | Create invoice, send to client, process payment, track status |
| **~~CRM** | Update client record, log revenue, track outstanding balances |
| **~~chat** | Notify team when payments are received or become overdue |
| **~~email** | Send invoice and payment reminder emails |

> **No connectors?** I'll generate a formatted invoice you can enter into your billing system, draft reminder emails, and track payment status in conversation.

---

## Invoice Lifecycle

```
Contract Signed
       │
       ▼
  ┌──────────┐     ┌──────────┐     ┌────────┐
  │  DRAFT   │────▶│   SENT   │────▶│  PAID  │
  └──────────┘     └──────────┘     └────────┘
                        │
                        ▼ (past due date)
                   ┌──────────┐
                   │ OVERDUE  │
                   └──────────┘
                        │
                   Reminder escalation:
                   Day 7 → Day 14 → Day 30
```

---

## Invoice Format

```markdown
## INVOICE

**Invoice #:** [INV-YYYY-NNN]
**Date:** [Issue date]
**Due Date:** [Payment due date]

---

**From:**
[Your Company Name]
[Address]
[Tax ID if applicable]

**To:**
[Client Name]
[Company Name]
[Billing address]
[Billing email]

---

### Services

| Description | Quantity | Rate | Amount |
|-------------|----------|------|--------|
| [Service / deliverable 1] | [Qty] | $[Rate] | $[Amount] |
| [Service / deliverable 2] | [Qty] | $[Rate] | $[Amount] |
| [Service / deliverable 3] | [Qty] | $[Rate] | $[Amount] |

| | | **Subtotal** | $[Subtotal] |
| | | **Tax ([Rate]%)** | $[Tax] |
| | | **Total Due** | **$[Total]** |

---

### Payment Details

**Terms:** [Net 30 / Due on receipt / etc.]
**Methods accepted:** [Bank transfer / Credit card / etc.]

**Bank transfer details:**
[Account name]
[Bank name]
[Account number]
[Routing number]

---

### Notes
[Any additional terms, project reference, or thank-you message]
```

---

## Payment Billing Models

### Single Invoice
Full amount billed at once. Best for small engagements.

### Split Invoicing (Milestone-Based)
```
Invoice 1: 50% upfront — Due on contract signing
Invoice 2: 25% at midpoint — Due on [milestone]
Invoice 3: 25% on completion — Due on final delivery
```

### Retainer
```
Monthly invoice: $[Amount]/month
Billing date: 1st of each month
Auto-send on schedule
```

### Phased
```
Phase 1 invoice: $[Amount] — Due on Phase 1 kickoff
Phase 2 invoice: $[Amount] — Due on Phase 2 kickoff
Phase 3 invoice: $[Amount] — Due on Phase 3 kickoff
```

---

## Payment Reminder Escalation

Automated reminders for overdue invoices:

### Day 7 — Friendly Reminder
```
Subject: Friendly reminder — Invoice #[Number] due [Date]

Hi [First Name],

Just a quick reminder that Invoice #[Number] for $[Amount] was
due on [Date]. I've attached a copy for your reference.

If this has already been processed, please disregard. Payment
processing can sometimes take a few days to clear.

If you have any questions about the invoice, feel free to
reach out.

[Your name]
```

### Day 14 — Firm Follow-Up
```
Subject: Invoice #[Number] — 14 days past due

Hi [First Name],

Following up on Invoice #[Number] for $[Amount], which was due
on [Date]. This is now 14 days past due.

Could you let me know the expected payment date? If there's an
issue with the invoice or payment process, I'm happy to help
resolve it.

[Your name]
```

### Day 30 — Escalation
```
Subject: Overdue invoice requires attention — #[Number]

Hi [First Name],

Invoice #[Number] for $[Amount] is now 30 days past due
(original due date: [Date]).

I'd like to resolve this as soon as possible. Could you please
confirm when we can expect payment, or let me know if there's
anything that needs to be addressed on our end?

If it's easier, I'm available for a quick call: [calendar link]

[Your name]
```

---

## Revenue Dashboard

Track payments and outstanding balances across all clients:

```markdown
## Revenue Summary — [Month/Quarter]

### Overview
| Metric | Amount |
|--------|--------|
| **Total Invoiced** | $[Sum of all invoices] |
| **Total Paid** | $[Sum of paid invoices] |
| **Outstanding** | $[Invoiced - Paid] |
| **Overdue** | $[Past due amount] |

### By Client
| Client | Invoiced | Paid | Outstanding | Status |
|--------|----------|------|-------------|--------|
| [Company 1] | $[Amt] | $[Amt] | $[Amt] | Paid |
| [Company 2] | $[Amt] | $[Amt] | $[Amt] | Due in 5 days |
| [Company 3] | $[Amt] | $0 | $[Amt] | 7 days overdue |

### Recent Activity
- [Date]: Payment received from [Company] — $[Amount]
- [Date]: Invoice #[Num] sent to [Company] — $[Amount]
- [Date]: Reminder sent to [Company] — Invoice #[Num] overdue

### Action Items
- [ ] Follow up with [Company] — 14 days overdue
- [ ] Send Invoice #[Num] to [Company] — contract signed yesterday
- [ ] Review [Company] payment plan — partial payment received
```

---

## Execution Flow

### Creating an Invoice

**If payments connector available:**
```
1. Pull client data from CRM
2. Create invoice in payment system
3. Set line items, tax, payment terms
4. Send invoice to client
5. Store invoice reference in CRM
6. Notify team via chat
```

**If no payments connector:**
```
1. Generate formatted invoice (markdown)
2. User enters into their billing system
3. User sends to client manually
```

### Tracking Payments

**If payments connector available:**
```
1. Check invoice status via API
2. On payment received:
   - Update CRM: status → "Paid" or "Client Acquired"
   - Notify team via chat
   - Log payment date and method
3. On overdue:
   - Send appropriate reminder (Day 7/14/30)
   - Alert team if 30+ days
```

**If no payments connector:**
```
1. User reports payment status
2. Draft reminder emails as needed
3. Maintain running balance in conversation
```

### Pipeline Completion

When final payment is received:
```
1. CRM status → "Client Acquired" or "Paid"
2. Team notification: "Deal closed — [Company] — $[Amount]"
3. Log total revenue for the deal
4. Suggest: onboarding, case study creation, referral ask
```

---

## Tips

1. **Send invoices within 24 hours of contract signing** — Momentum matters for payments too
2. **Match the terms to the client** — Enterprise clients may need Net 45-60. Small businesses can do Net 15 or due on receipt
3. **Split large invoices** — Milestone billing reduces risk for both parties and improves cash flow
4. **Automate reminders** — Manual follow-up on overdue invoices is awkward. Automated reminders feel professional
5. **Track everything** — Revenue visibility prevents surprises. Know your outstanding balance at all times

---

## Related Skills

- **contract-management** — Invoice generation typically follows contract signing
- **proposal-assembly** — Proposal pricing feeds directly into invoice amounts
- **lead-capture** — Full-cycle tracking: captured → closed → paid
