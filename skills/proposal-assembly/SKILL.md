# Proposal Assembly

Build professional proposals from discovery data — auto-populate templates, route for team review, and get from "interested" to "here's our proposal" fast.

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                    PROPOSAL ASSEMBLY                             │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You tell me: client, their needs, your services, pricing    │
│  ✓ Generate structured proposal with all standard sections      │
│  ✓ Personalized approach section referencing discovery data     │
│  ✓ Pricing table with clear deliverables and timeline           │
│  ✓ Output: ready-to-send proposal document                     │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + CRM: Pull client data, discovery notes, pain points auto    │
│  + Chat: Route for team review with SLA tracking                │
│  + Email: Send proposal directly to client                      │
│  + E-signature: Generate PDF and create signing envelope        │
└─────────────────────────────────────────────────────────────────┘
```

---

## Getting Started

**Required:**
- Client name and company
- What services you're proposing
- Pricing (or "help me figure out pricing")

**Helpful if you have it:**
- Discovery call notes or transcript summary
- Pain points they mentioned
- Their timeline and budget range
- Decision makers and their priorities
- Any specific requests or constraints they mentioned

If CRM is connected, I'll pull discovery notes and client data automatically.

---

## Connectors (Optional)

| Connector | What It Adds |
|-----------|--------------|
| **~~CRM** | Pull client data, discovery notes, pain points, prior proposals |
| **~~chat** | Route proposal for team review with SLA reminders |
| **~~email** | Send completed proposal to client |
| **~~e-signature** | Generate PDF, create signing envelope, send for signature |

> **No connectors?** I'll build the proposal from what you give me and output it as a formatted document you can export to PDF and send manually.

---

## Proposal Structure

Every proposal follows a modular template system:

### Base Sections (always included)

1. **Cover / Introduction**
   - Client name and company
   - Date and proposal number
   - Your company name and logo placement
   - Executive summary (2-3 sentences)

2. **Understanding Your Needs**
   - Paraphrase their pain points from discovery
   - Show you listened — reference specific things they said
   - Frame the problem in business impact terms

3. **Our Approach**
   - How you'll solve their specific problems
   - Methodology overview
   - Why this approach vs. alternatives
   - Timeline with milestones

4. **Deliverables & Pricing**
   - Clear line items with descriptions
   - Pricing per deliverable or phase
   - Total investment
   - Payment terms

5. **About Us / Why Us**
   - Relevant experience
   - Case study or social proof relevant to their industry
   - Team members who'll be involved

6. **Terms & Next Steps**
   - Engagement terms
   - How to proceed (sign, schedule kickoff, etc.)
   - Proposal validity period
   - Contact information

### Service Blocks (modular — include based on what you're proposing)

Service blocks are plug-and-play sections describing specific offerings. Examples:
- Process automation
- AI/ML implementation
- Systems integration
- Data migration
- Consulting / strategy
- Ongoing support / retainer

Each block includes: description, typical deliverables, timeline range, and pricing framework.

---

## Output Format

```markdown
# Proposal: [Service/Project Name]
## Prepared for [Client Name], [Company]
### [Date] | Proposal #[Number]

---

## Executive Summary

[2-3 sentences: who you are, what you're proposing, the expected impact]

---

## Understanding Your Needs

[Company] is facing challenges with [pain point 1], [pain point 2], and [pain point 3].

During our discovery conversation on [date], you mentioned:
- "[Specific quote or paraphrase from discovery]"
- "[Another specific point they raised]"
- "[Third point demonstrating you listened]"

The business impact of these challenges includes [cost, time loss, risk, opportunity cost].

---

## Our Approach

### Phase 1: [Name] — [Timeline]
[What you'll do, why, and what the client gets]

### Phase 2: [Name] — [Timeline]
[What you'll do, why, and what the client gets]

### Phase 3: [Name] — [Timeline]
[What you'll do, why, and what the client gets]

---

## Deliverables & Investment

| Deliverable | Description | Timeline | Investment |
|-------------|-------------|----------|------------|
| [Item 1] | [What it includes] | [Weeks] | $[Amount] |
| [Item 2] | [What it includes] | [Weeks] | $[Amount] |
| [Item 3] | [What it includes] | [Weeks] | $[Amount] |
| | | **Total** | **$[Total]** |

**Payment terms:** [e.g., 50% upfront, 50% on completion]

---

## Why [Your Company]

[Relevant experience paragraph]

**Relevant work:**
- [Case study or client example relevant to their industry/problem]

**Your team:**
- [Name] — [Role and relevant expertise]
- [Name] — [Role and relevant expertise]

---

## Next Steps

1. Review this proposal and share any questions
2. Sign the engagement letter (attached / linked)
3. Schedule kickoff call for [suggested date]

This proposal is valid for 30 days from [date].

Questions? Reach out to [contact name] at [email].
```

---

## Merge Fields

The proposal system uses dynamic fields that get populated from client data:

| Field | Source | Example |
|-------|--------|---------|
| `[Client Name]` | CRM or user input | Sarah Chen |
| `[Company]` | CRM or user input | Acme Corp |
| `[Pain Point 1-3]` | Discovery notes | Manual data entry taking 20 hrs/week |
| `[Quote]` | Transcript or notes | "We're drowning in spreadsheets" |
| `[Timeline]` | Discovery discussion | 6 weeks |
| `[Total]` | Pricing calculation | $15,000 |
| `[Date]` | Generated | February 1, 2026 |

---

## Review Workflow

When the proposal is ready for team review:

```
1. Draft generated → Post to review channel
2. Reviewer 1 assigned (4-hour SLA)
   - Approve / Request changes
3. Reviewer 2 assigned (4-hour SLA)
   - Approve / Request changes
4. Both approved → Ready to send
5. Send to client (email or e-signature)
```

If chat is connected, I'll post the draft with review buttons and send SLA reminders if reviews are overdue.

---

## Execution Flow

### Step 1: Gather Client Data

**If CRM connected:**
```
1. Pull lead record: name, company, contact info
2. Pull discovery notes: pain points, budget, timeline
3. Pull call summary: key discussion points, enthusiasm level
4. Check for prior proposals (don't duplicate)
```

**If no CRM:**
```
1. Ask user for client details and discovery context
2. Pull from conversation history if available
```

### Step 2: Build Proposal

```
1. Select base template
2. Map pain points to "Understanding Your Needs" section
3. Design approach based on services discussed
4. Build deliverables table with pricing
5. Select relevant case study / social proof
6. Populate all merge fields
7. Generate executive summary
```

### Step 3: Review & Send

**If chat connected:**
```
1. Post draft to review channel
2. Assign reviewers with SLA timers
3. Collect approvals
4. On final approval → proceed to send
```

**If e-signature connected:**
```
1. Generate PDF from proposal
2. Create signing envelope
3. Set signature fields
4. Send for e-signature
```

**If no connectors:**
```
1. Output complete proposal as formatted markdown
2. User exports to PDF and sends manually
```

---

## Tips

1. **Include discovery quotes** — Nothing personalizes a proposal better than referencing exactly what the client said
2. **Keep pricing clear** — Ambiguous pricing kills deals. Every line item should be understandable without explanation
3. **Speed matters** — Sending the proposal within 24 hours of discovery dramatically improves close rates
4. **Don't over-scope** — Propose what they need, not everything you can do. You can always expand later
5. **Match their language** — If they said "workflow automation", don't write "business process optimization"

---

## Related Skills

- **post-call-followup** — Run this first to extract discovery insights for the proposal
- **contract-management** — After proposal approval, send the contract for signature
- **invoice-tracking** — After contract signing, generate the invoice
