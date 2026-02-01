# Discovery Prep

Get fully prepared for any discovery or sales call. Build a meeting brief with company research, attendee backgrounds, a prep questionnaire, and a suggested agenda — plus automate the pre-meeting email sequence.

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                      DISCOVERY PREP                              │
├─────────────────────────────────────────────────────────────────┤
│  STANDALONE (always works)                                       │
│  ✓ You tell me: company, meeting type, attendees                │
│  ✓ Web research: company info, news, leadership                 │
│  ✓ Pre-meeting email sequence drafts (3 emails)                 │
│  ✓ Prep questionnaire (7 key questions)                         │
│  ✓ Meeting brief with agenda and discovery questions            │
├─────────────────────────────────────────────────────────────────┤
│  SUPERCHARGED (when you connect your tools)                      │
│  + Calendar: Auto-detect bookings, pull attendees and time      │
│  + CRM: Pull lead history, prior interactions, pipeline data    │
│  + Email: Send confirmation, questionnaire, reminder sequence   │
│  + Transcripts: Pull prior call recordings for returning leads  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Getting Started

**Required:**
- Company or contact name
- Meeting date/time (or "tomorrow at 2pm")

**Helpful if you have it:**
- Attendee names and titles
- What you know about them so far (form submission, referral context, prior conversations)
- What you want to accomplish in the meeting

If calendar is connected, I'll find the meeting automatically and pull attendees.

---

## Connectors (Optional)

| Connector | What It Adds |
|-----------|--------------|
| **~~calendar** | Auto-detect booking, pull meeting details, attendees, description |
| **~~CRM** | Lead history, prior interactions, qualification score, form submission data |
| **~~email** | Send the 3-email pre-meeting sequence automatically |
| **~~conversation intelligence** | Pull prior call recordings if this is a returning lead |

> **No connectors?** I'll research the company and attendees via web search, draft all three emails for you to send manually, and create a complete meeting brief.

---

## Pre-Meeting Email Sequence

Three timed emails that increase show-up rates and gather intel before the call:

### Email 1: Immediate Confirmation
**When:** Right after booking
**Subject:** You're booked — here's what to expect

```
Hi [First Name],

Thanks for scheduling time with us. Here's what you can expect from our
[30-minute] discovery call on [Day, Date] at [Time]:

We'll cover:
- Your current workflows and where things get stuck
- Quick wins we've seen for companies like yours
- Whether there's a fit for working together

No hard sell — just a conversation about what's possible.

We'll send a quick questionnaire beforehand so we can skip the basics and
get straight to solutions.

Talk soon,
[Your team]
```

### Email 2: T-24 Hours — Prep Questionnaire
**When:** 24 hours before the meeting
**Subject:** Quick prep for tomorrow's call

```
Hi [First Name],

Looking forward to connecting tomorrow. To make the most of our time,
could you take 3 minutes to answer a few questions?

1. What does your company do? (1-2 sentences)
2. How many people are on your team?
3. What tools or software do you currently use?
4. What's your biggest operational bottleneck?
5. What would "success" look like for you?
6. What's your timeline for making changes?
7. Anything else you'd like us to know?

Just reply to this email with your answers — no need for a formal form.

See you tomorrow,
[Your team]
```

### Email 3: T-1 Hour — Final Reminder
**When:** 1 hour before the meeting
**Subject:** See you in 1 hour

```
Hi [First Name],

Quick reminder — we're meeting in about an hour.

Here's your link: [Meeting URL]

Agenda:
- Introductions and your current situation
- Where automation could help most
- Next steps (if there's a fit)

Looking forward to it.

[Your team]
```

---

## Meeting Brief

After research is complete, I generate a comprehensive brief:

```markdown
# Meeting Brief: [Company Name]

**Meeting:** Discovery Call — [Date] at [Time]
**Attendees:** [Names with titles]
**Your Goal:** [Qualify the opportunity and identify quick wins]

---

## Company Snapshot

| Field | Value |
|-------|-------|
| **Company** | [Name] |
| **Industry** | [Industry] |
| **Size** | [Employees / revenue if known] |
| **Founded** | [Year] |
| **Location** | [City, State] |
| **Website** | [URL] |

---

## What We Know So Far

**From lead capture:**
- Source: [How they found us]
- Score: [Hot / Warm / Cold]
- Message: "[Their original message or context]"

**From questionnaire (if completed):**
- Team size: [Answer]
- Current tools: [Answer]
- Biggest bottleneck: [Answer]
- Success criteria: [Answer]
- Timeline: [Answer]

**From web research:**
- [Recent news item — why it matters]
- [Funding or growth signals]
- [Technology stack clues]

---

## Who You're Meeting

### [Name] — [Title]
- **Background:** [Career summary from LinkedIn]
- **Role in decision:** [Decision maker / Influencer / Evaluator]
- **Talking point:** [Something personal or professional to reference]

---

## Suggested Agenda

1. **Open (5 min)** — Introductions, reference how they found you
2. **Their world (10 min)** — Current workflows, team structure, pain points
3. **Bottlenecks (10 min)** — Dig into their biggest operational challenge
4. **Quick wins (5 min)** — Share 1-2 automation ideas specific to their situation
5. **Next steps (5 min)** — Propose clear follow-up if there's a fit

---

## Discovery Questions

1. Walk me through your current process for [their main workflow] — where does it break down?
2. What happens when [their bottleneck] occurs? What's the downstream impact?
3. How much time does your team spend on [manual task they likely have]?
4. Have you tried to solve this before? What happened?
5. If we could fix [their main pain point], what would that mean for your business?
6. Who else would be involved in a decision to move forward?
7. What's your ideal timeline for getting this solved?

---

## Potential Objections

| Objection | Suggested Response |
|-----------|-------------------|
| "We're not sure about the budget" | Focus on ROI and time savings. Offer to scope a quick-win project first. |
| "We've tried automation before and it didn't work" | Ask what went wrong. Differentiate your approach. |
| "We need to talk to our team" | Offer to include them in a follow-up call. |

---

## After the Call

Run **post-call-followup** to:
- Process the transcript
- Draft personalized follow-up email
- Update the CRM record
- Route for team review
```

---

## Execution Flow

### Step 1: Gather Context

**If connectors available:**
```
1. Calendar → Find meeting matching company/contact
   - Pull: time, attendees, description, meeting link

2. CRM → Query lead record
   - Pull: lead score, source, form submission, prior interactions
   - Pull: questionnaire responses if submitted

3. Conversation intelligence → Check for prior calls
   - Pull: past recordings, topics covered
```

**If no connectors:**
```
1. Ask user for: company, meeting date, attendees
2. Accept whatever context they provide
```

### Step 2: Research

**Always run (web search):**
```
1. "[Company] + what they do" — core business
2. "[Company] + news" — recent developments
3. "[Company] + funding" — growth signals
4. "[Company] + team size" — company scale
5. Attendee LinkedIn profiles — background research
```

### Step 3: Generate Outputs

```
1. Compile all sources into meeting brief
2. Draft 3-email pre-meeting sequence (personalized with company/contact data)
3. Generate discovery questions tailored to their industry and situation
4. Anticipate objections based on lead score and source
```

### Step 4: Deliver

**If email connected:** Send Email 1 immediately, schedule Emails 2 and 3.
**If no email:** Present all three drafts for manual sending.

---

## Tips

1. **Run this as soon as the meeting is booked** — The sooner the confirmation email goes out, the better the show-up rate
2. **Include what you already know** — Prior emails, form submissions, referral context all make the brief better
3. **Review the questionnaire responses** before the call — They're gold for personalization
4. **Customize the agenda** for returning leads or different meeting types (demo, proposal review, etc.)

---

## Related Skills

- **lead-capture** — If you haven't captured this lead yet, start there
- **post-call-followup** — After the discovery call, process transcript and draft follow-up
- **proposal-assembly** — If the call goes well, move to proposal generation
