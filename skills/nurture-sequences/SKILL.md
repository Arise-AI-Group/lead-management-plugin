# Nurture Sequences

Keep warm and cold leads engaged with stage-based email sequences that deliver value — not sales pitches — until they're ready to move forward.

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                    NURTURE SEQUENCES                             │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You tell me: who to nurture, their context, their stage     │
│  ✓ Generate stage-appropriate email (value-first, not sales)    │
│  ✓ Content personalized to their industry and pain points       │
│  ✓ Track nurture cadence (Day 3 / 7 / 14 / 30 / 60+)          │
│  ✓ Recommend when to advance, pause, or exit a lead            │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + CRM: Query all leads in nurture, auto-advance stages        │
│  + Email: Send nurture emails automatically                     │
│  + Chat: Notify team of replies, bounces, re-engagement signals│
└─────────────────────────────────────────────────────────────────┘
```

---

## Getting Started

**Required:**
- Contact name and company
- Where they are in the nurture cadence (or "just entering nurture")

**Helpful if you have it:**
- Their industry and company size
- Pain points from discovery (if they've had a call)
- What content they've received so far
- Any recent activity (website visit, email open, social engagement)

If CRM is connected, I'll pull lead data and determine the nurture stage automatically.

---

## Connectors (Optional)

| Connector | What It Adds |
|-----------|--------------|
| **~~CRM** | Query leads by status, check activity, update nurture stage |
| **~~email** | Send nurture emails automatically on schedule |
| **~~chat** | Alert team when leads reply, bounce, or re-engage |

> **No connectors?** I'll draft the nurture email for you to send manually and track the cadence for you in conversation.

---

## Nurture Stages

Five stages designed to deliver increasing value while staying respectful of the lead's timeline:

### Stage 1: Post-Discovery Value Drop (Day 3)

**Context:** They've had a call but haven't committed.
**Goal:** Reinforce value, stay top of mind.
**Tone:** Helpful, generous, zero pressure.

**Content options (selected based on their profile):**
- Relevant case study from a similar company or industry
- Tool recommendation related to their pain point
- "Here's how [similar company] solved [their exact problem]"
- Industry-specific automation insight or stat

```
Subject: Thought you'd find this useful — [topic]

Hi [First Name],

[One sentence connecting back to your conversation]

[2-3 sentences sharing the actual value — case study summary,
tool recommendation, or insight]

[Link or attachment if applicable]

No agenda here — just thought this was relevant to what you
described about [their pain point].

[Your name]
```

**Key rule:** No CTA. Pure value, no ask.

---

### Stage 2: Deeper Insight (Day 7)

**Context:** A week has passed, they may be comparing options.
**Goal:** Position as experts, address implicit objections.
**Tone:** Educational, authoritative.

**Content options:**
- "3 things to look for in [your service category] partner"
- Process improvement tip they can implement themselves
- ROI breakdown relevant to their industry
- Resource on a topic they mentioned in discovery

```
Subject: [Topic related to their specific pain point]

Hi [First Name],

[Opening that frames the content in context of their situation]

[3-4 paragraphs of genuinely useful educational content]

If you want to explore how this applies to [their company],
happy to chat.

[Your name]
```

**Key rule:** Soft CTA only. "Happy to chat" — not "book a call now."

---

### Stage 3: Check-In (Day 14)

**Context:** Two weeks out, decision may be stalling.
**Goal:** Re-engage without being pushy.
**Tone:** Casual, human, brief.

**Content options:**
- "Checking in — any questions come up since we talked?"
- Share a quick win or tool they could try immediately
- Brief update on something relevant to their industry

```
Subject: Quick check-in

Hi [First Name],

Just wanted to check in — any questions or thoughts since
we last connected?

[Optional: one sentence sharing something new or relevant]

If the timing's better later, no worries at all. Just let
me know when makes sense.

[Your name]
```

**Key rule:** Keep it under 100 words. Easy to reply to.

---

### Stage 4: Re-Engagement (Day 30)

**Context:** A month out, they may have gone cold.
**Goal:** One clear attempt to re-engage.
**Tone:** Direct but respectful.

**Content options:**
- "Wanted to share something that reminded me of our conversation"
- New case study or result from a similar engagement
- Industry news that relates to their pain point

```
Subject: [Something specific — not "Just following up"]

Hi [First Name],

It's been a few weeks since we connected. [One sentence
about why you're reaching out — a new result, news item,
or insight relevant to them]

[2-3 sentences of actual content]

If your priorities have shifted, totally understand.
If [their pain point] is still on your radar, I'd love to
pick up where we left off: [calendar link]

[Your name]
```

**Key rule:** Reference something specific. Never send a content-free "just following up" email.

---

### Stage 5: Long-Term Nurture (Day 60+)

**Context:** Extended timeline, not ready now.
**Goal:** Stay on their radar without being annoying.
**Tone:** Light-touch, quarterly.
**Frequency:** Every 30-60 days.

**Content options:**
- Major company update or case study
- Quarterly industry roundup
- "We just launched [something relevant to them]"
- Event invite or resource they'd genuinely find useful

```
Subject: [Value-forward subject — news, resource, or insight]

Hi [First Name],

[Brief, valuable content — 2-3 sentences max]

[Link if applicable]

Hope things are going well at [Company].

[Your name]
```

**Key rule:** Frequency drops dramatically. Quality over quantity.

---

## Exit Conditions

A lead should exit nurture when any of these occur:

| Trigger | Action |
|---------|--------|
| **Lead replies** | Exit nurture → Alert team → Route for follow-up |
| **Meeting booked** | Exit nurture → Enter discovery-prep workflow |
| **Unsubscribe / opt out** | Exit nurture → Mark in CRM → Never email again |
| **Deal closed (won)** | Exit nurture → Move to client onboarding |
| **Deal closed (lost)** | Exit nurture → Move to lost/dormant |
| **Email bounces** | Pause nurture → Verify email → Resume or exit |

---

## Batch Processing

For reviewing all leads in nurture at once:

```markdown
## Nurture Pipeline Review — [Date]

### Due for Action Today
| Lead | Company | Stage | Days Since Last Touch | Action |
|------|---------|-------|----------------------|--------|
| [Name] | [Co] | Stage 2 (Day 7) | 4 | Send deeper insight email |
| [Name] | [Co] | Stage 4 (Day 30) | 2 | Send re-engagement |

### Recent Activity
- [Name] opened Stage 1 email (3 opens in 2 days) → Consider advancing
- [Name] replied to Stage 3 check-in → EXIT nurture, route to team

### Upcoming
- [Name] → Stage 2 due in 3 days
- [Name] → Stage 3 due tomorrow

### Recommended Exits
- [Name] — No opens on any email, 60+ days → Suggest moving to dormant
```

---

## Execution Flow

### Step 1: Identify Leads in Nurture

**If CRM connected:**
```
1. Query leads where status = "Discovery Complete" and
   NOT moved to "Proposal Sent" or "Won" or "Lost"
2. Check last email sent date and nurture stage
3. Identify leads due for next stage
```

**If no CRM:**
```
1. User tells me who to nurture and their current stage
2. Track in conversation context
```

### Step 2: Generate Content

```
1. Determine which stage email to write
2. Pull lead context: industry, pain points, discovery notes
3. Select content type (case study, tip, check-in, etc.)
4. Personalize based on their specific situation
5. Draft email following stage guidelines
```

### Step 3: Send or Queue

**If email connected:**
```
1. Send email directly
2. Update CRM with send date and stage
```

**If chat connected:**
```
1. Post draft to team channel for optional review
2. One-click send or edit
```

**If no connectors:**
```
1. Present email draft for manual sending
2. Remind user to update their tracking
```

---

## Tips

1. **Value first, always** — Every nurture email should be worth reading even if the lead never becomes a customer
2. **Don't skip stages** — The cadence builds trust. Jumping from "nice to meet you" to "buy now" kills deals
3. **Personalize with discovery data** — A generic nurture email performs 10x worse than one that references their specific pain point
4. **Respect the exit** — When someone opts out, they're gone. Continuing to email damages your brand
5. **Watch for signals** — Multiple email opens, website visits, or social engagement may mean they're ready before the cadence suggests

---

## Related Skills

- **lead-capture** — Leads enter nurture after being captured and scored as Warm or Cold
- **post-call-followup** — Discovery data from calls enriches nurture personalization
- **discovery-prep** — When a nurtured lead books a call, switch to discovery prep
