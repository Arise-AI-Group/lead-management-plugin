# Nurture Sequence Workflow Diagrams

## Overall Lead Flow

```mermaid
graph TD
    A[Lead Capture] --> B{Discovery Call?}
    B -->|Yes| C[Discovery Call]
    B -->|No| D[Enter Nurture Stage 1]

    C --> E{Outcome?}
    E -->|Ready to Buy| F[Proposal]
    E -->|Not Ready| D
    E -->|No Show| D

    D --> G[5-Stage Nurture Campaign]
    G --> H{Exit Trigger?}

    H -->|Reply| I[Sales Team Alert]
    H -->|Meeting Booked| J[Discovery Prep]
    H -->|Won Deal| K[Client Onboarding]
    H -->|Lost Deal| L[Quarterly Touches]
    H -->|No Response 60+ days| L

    I --> M[Active Sales Process]
    J --> M
    M --> F

    F --> N{Proposal Result}
    N -->|Won| K
    N -->|Lost| L
    N -->|Need Time| D
```

## 5-Stage Nurture Sequence Detail

```mermaid
graph LR
    subgraph "Nurture Campaign Timeline"
        A[Day 0: Enter Nurture] --> B[Day 3: Stage 1]
        B --> C[Day 7: Stage 2]
        C --> D[Day 14: Stage 3]
        D --> E[Day 30: Stage 4]
        E --> F[Day 60+: Stage 5]
    end

    B -.->|Pure Value<br/>No CTA| B1[Value Drop Email]
    C -.->|Education<br/>Soft CTA| C1[Insight Email]
    D -.->|Human Touch<br/>Easy Reply| D1[Check-in Email]
    E -.->|Direct Ask<br/>Clear CTA| E1[Re-engagement Email]
    F -.->|Quarterly<br/>High Value| F1[Long-term Touch]
```

## Exit Condition Flow

```mermaid
graph TD
    A[Lead in Nurture] --> B{Monitor Triggers}

    B --> C{Lead Replies?}
    C -->|Yes| D[Exit Nurture]
    D --> E[Alert Sales Team]

    B --> F{Meeting Booked?}
    F -->|Yes| G[Exit Nurture]
    G --> H[Start Discovery Prep]

    B --> I{Unsubscribe?}
    I -->|Yes| J[Exit Nurture]
    J --> K[Mark in CRM]

    B --> L{Email Bounces?}
    L -->|Yes| M[Pause Nurture]
    M --> N[Verify Contact Info]
    N --> O{Valid?}
    O -->|Yes| P[Resume Nurture]
    O -->|No| Q[Exit Nurture]

    B --> R{60+ Days Silent?}
    R -->|Yes| S[Move to Long-term]
    S --> T[Quarterly Touches Only]

    B --> U{Deal Status Change?}
    U -->|Won| V[Exit → Client Onboarding]
    U -->|Lost| W[Exit → Dormant Status]
```

## Daily Batch Processing Workflow

```mermaid
graph TD
    A[9:00 AM Daily Check] --> B[Run /nurture-status --due]
    B --> C[Generate Lead List]

    C --> D{Any Leads Due?}
    D -->|No| E[End]
    D -->|Yes| F[For Each Lead]

    F --> G[Pull Discovery Context]
    G --> H[Check Stage Template]
    H --> I[Personalize Content]
    I --> J[Generate Email]

    J --> K{Review Mode?}
    K -->|Auto| L[Send Email]
    K -->|Manual| M[Queue for Review]

    M --> N[Team Review]
    N --> O{Approved?}
    O -->|Yes| L
    O -->|No| P[Edit & Resend]
    P --> L

    L --> Q[Log in CRM]
    Q --> R[Update Last Contact]
    R --> S[Schedule Next Stage]

    S --> T{More Leads?}
    T -->|Yes| F
    T -->|No| U[Generate Report]
    U --> E
```

## Re-engagement Signal Detection

```mermaid
graph TD
    A[Monitor Lead Activity] --> B{Signal Detected?}

    B --> C[Website Visit]
    C --> D{Days Since Contact?}
    D -->|14+ Days| E[Flag for Re-engagement]

    B --> F[Email Open]
    F --> G{Clicked Link?}
    G -->|Yes| E
    G -->|No| H[Note Interest]

    B --> I[Content Download]
    I --> E

    B --> J[Social Engagement]
    J --> K{LinkedIn/Twitter Activity?}
    K -->|Profile View| E
    K -->|Content Like| H

    E --> L[Priority Flag in CRM]
    L --> M[Accelerate Nurture]
    M --> N[Send Personalized Touch]

    H --> O[Standard Cadence]
```

## Integration Architecture

```mermaid
graph LR
    subgraph "Input Sources"
        A1[Lead Capture Form]
        A2[Discovery No-shows]
        A3[Lost Deals]
        A4[Cold Outreach]
    end

    subgraph "Nurture System Core"
        B[Lead Queue] --> C[Stage Manager]
        C --> D[Template Engine]
        D --> E[Personalization Layer]
        E --> F[Send Queue]
    end

    subgraph "Integrations"
        G[CRM<br/>HubSpot/Notion]
        H[Email<br/>M365/Gmail]
        I[Calendar<br/>Calendly]
        J[Analytics<br/>Tracking]
        K[Slack<br/>Notifications]
    end

    A1 --> B
    A2 --> B
    A3 --> B
    A4 --> B

    C <--> G
    F --> H
    F --> J
    C <--> I
    F --> K

    subgraph "Outputs"
        L[Email Campaigns]
        M[Meeting Bookings]
        N[Team Alerts]
        O[Reports]
    end

    H --> L
    I --> M
    K --> N
    J --> O
```

## Performance Optimization Flow

```mermaid
graph TD
    A[Monitor Metrics] --> B{Open Rate < 25%?}
    B -->|Yes| C[Review Subject Lines]
    C --> D[A/B Test New Versions]

    A --> E{Reply Rate < 5%?}
    E -->|Yes| F[Check Email Content]
    F --> G[Simplify CTAs]
    G --> H[Make Easier to Reply]

    A --> I{Bounce Rate > 5%?}
    I -->|Yes| J[Email Verification]
    J --> K[Update Contact Info]

    A --> L{Unsubscribe > 5%?}
    L -->|Yes| M[Review Frequency]
    M --> N[Check Relevance]
    N --> O[Adjust Targeting]

    D --> P[Implement Winners]
    H --> P
    K --> P
    O --> P

    P --> Q[Continue Monitoring]
    Q --> A
```

## Decision Tree for Stage Selection

```mermaid
graph TD
    A[Lead Enters Nurture] --> B{Source?}

    B -->|Discovery No-show| C[Start Stage 1]
    B -->|Cold Lead| D[Start Stage 1]
    B -->|Lost Deal| E{Reason Lost?}

    E -->|Budget| F[Start Stage 4]
    E -->|Timing| G[Start Stage 3]
    E -->|Competitor| H[Start Stage 2]
    E -->|Not a Fit| I[Move to Quarterly]

    C --> J{Has Context?}
    J -->|Yes| K[Personalized Stage 1]
    J -->|No| L[Generic Stage 1]

    D --> M{Engagement Level?}
    M -->|Downloaded Content| N[Start Stage 2]
    M -->|Just Subscribe| L
    M -->|Multiple Touches| O[Start Stage 3]
```

## Email Template Selection Logic

```mermaid
graph TD
    A[Select Template] --> B{Industry?}

    B -->|SaaS| C[SaaS Templates]
    B -->|E-commerce| D[E-commerce Templates]
    B -->|Services| E[Service Templates]
    B -->|Other| F[Generic Templates]

    C --> G{Company Size?}
    D --> G
    E --> G
    F --> G

    G -->|Startup| H[Agility Focus]
    G -->|SMB| I[Efficiency Focus]
    G -->|Enterprise| J[Scale Focus]

    H --> K{Pain Point?}
    I --> K
    J --> K

    K -->|Growth| L[Growth Templates]
    K -->|Efficiency| M[Efficiency Templates]
    K -->|Compliance| N[Compliance Templates]
    K -->|Innovation| O[Innovation Templates]

    L --> P[Final Template]
    M --> P
    N --> P
    O --> P

    P --> Q[Apply Personalization]
    Q --> R[Ready to Send]
```

---

## How to Use These Diagrams

1. **Overall Lead Flow**: Reference this when explaining the nurture system to team members or planning lead routing.

2. **5-Stage Detail**: Use this to understand the timing and purpose of each nurture stage.

3. **Exit Conditions**: Consult when setting up automation rules or training team on lead handling.

4. **Batch Processing**: Follow this workflow for daily nurture operations.

5. **Re-engagement Signals**: Use to identify when leads show renewed interest.

6. **Integration Architecture**: Reference when setting up or troubleshooting integrations.

7. **Performance Optimization**: Follow this flow when metrics drop below targets.

8. **Stage Selection**: Use this decision tree when manually placing leads into nurture.

9. **Template Selection**: Follow this logic for choosing the most relevant email templates.

---

*Note: These diagrams are rendered using Mermaid markdown. They can be viewed in any markdown viewer that supports Mermaid, including GitHub, GitLab, and many documentation tools.*