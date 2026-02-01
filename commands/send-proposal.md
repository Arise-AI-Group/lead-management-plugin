# /send-proposal

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Assemble a proposal from discovery data, populate templates, and route for review — from client needs to ready-to-send document.

## Usage

```
/send-proposal
```

Then tell me who the proposal is for and what services you're proposing.

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                      SEND PROPOSAL                               │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You tell me: client, services, pricing, context              │
│  ✓ Generate full proposal with all standard sections            │
│  ✓ Personalized based on discovery data and pain points         │
│  ✓ Pricing table with deliverables and timeline                 │
│  ✓ Output: formatted document ready for PDF export              │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + ~~CRM: Pull client data and discovery notes automatically   │
│  + ~~chat: Route for team review with SLA tracking              │
│  + ~~email: Send proposal to client                             │
│  + ~~e-signature: Generate PDF, create signing envelope         │
└─────────────────────────────────────────────────────────────────┘
```

---

## What I Need From You

**Required:**
- Client name and company
- What services you're proposing
- Pricing (or "help me figure out pricing")

**Helpful if you have it:**
- Discovery call notes or summary
- Their pain points and priorities
- Timeline and budget range
- Decision makers and their concerns

If CRM is connected, I'll pull discovery notes automatically.

---

## Output

### Full Proposal Document

```markdown
# Proposal: [Project/Service Name]
## Prepared for [Client], [Company]
### [Date] | Proposal #[Number]

## Executive Summary
[2-3 sentences: who you are, what you're proposing, expected impact]

## Understanding Your Needs
[Paraphrase their pain points. Reference specific things from discovery.]

## Our Approach
### Phase 1: [Name] — [Timeline]
[Description and deliverables]

### Phase 2: [Name] — [Timeline]
[Description and deliverables]

## Deliverables & Investment
| Deliverable | Timeline | Investment |
|-------------|----------|------------|
| [Item] | [Weeks] | $[Amount] |
| | **Total** | **$[Total]** |

**Payment terms:** [Terms]

## Why Us
[Relevant experience, case study, team]

## Next Steps
1. Review and share questions
2. Sign engagement letter
3. Schedule kickoff

Valid for 30 days.
```

---

## Review Workflow

```
Draft generated → Reviewer 1 (4h SLA) → Reviewer 2 (4h SLA) → Send to client
```

If ~~chat is connected, I'll post the draft with review buttons and send SLA reminders.

---

## If Connectors Available

**~~CRM connected:** Pull client data, discovery notes, and prior proposals.
**~~chat connected:** Route for review with SLA tracking. Notify on approval.
**~~email connected:** Send approved proposal to client.
**~~e-signature connected:** Generate PDF, create signing envelope, send for signature.

---

## Tips

1. **Include discovery quotes** — Referencing what the client said personalizes the proposal
2. **Send within 24 hours of discovery** — Momentum matters
3. **Keep pricing clear** — Every line item should make sense without explanation
4. **Don't over-scope** — Propose what they need now. You can expand later
