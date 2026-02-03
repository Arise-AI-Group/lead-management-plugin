# Nurture Sequence Documentation

## Overview

The Nurture Sequence system is a comprehensive lead nurturing framework designed to automatically engage leads through a 5-stage email campaign. It provides both manual and automated modes, integrating with popular CRM and email systems to maintain consistent communication with prospects.

## Table of Contents
1. [Quick Start](#quick-start)
2. [System Architecture](#system-architecture)
3. [The 5 Nurture Stages](#the-5-nurture-stages)
4. [Configuration](#configuration)
5. [Usage Modes](#usage-modes)
6. [Exit Conditions](#exit-conditions)
7. [Batch Processing](#batch-processing)
8. [Integration Points](#integration-points)
9. [Commands Reference](#commands-reference)
10. [Best Practices](#best-practices)
11. [Troubleshooting](#troubleshooting)

## Quick Start

### Basic Setup
1. **Install the lead management plugin**
   ```bash
   npm install @claude-plugins/lead-management
   ```

2. **Configure your settings** (`lead-management/.claude/settings.local.json`):
   ```json
   {
     "nurture_cadence": "standard",
     "company": "Your Company",
     "services": ["Service 1", "Service 2"],
     "brand_voice": "professional yet friendly"
   }
   ```

3. **Start nurturing leads**:
   ```
   /nurture-sequences
   ```

### Check Nurture Pipeline Status
```
/nurture-status
```

## System Architecture

```
Lead Capture → Discovery Call → Nurture Sequence → Conversion
                     ↓              ↓
                [No Show]    [5-Stage Campaign]
                     ↓              ↓
              [Enter Nurture]  [Exit Conditions]
```

### Components
- **Skills**: `nurture-sequences` (main skill)
- **Commands**: `/nurture-sequences`, `/nurture-status`
- **Integrations**: CRM (HubSpot/Notion), Email (Microsoft 365/Gmail), Slack
- **Templates**: 5 stage-specific email templates
- **Tracking**: Cadence management, engagement metrics

## The 5 Nurture Stages

### Stage 1: Post-Discovery Value Drop (Day 3)
**Purpose**: Pure value delivery with no CTA
**Content Types**:
- Relevant case study
- Free tool recommendation
- Industry insight or trend

**Template Structure**:
```
Subject: Thought you'd find this useful — [specific topic]

Hi [First Name],

Was thinking about our conversation on [specific topic] and came across this [resource type] that directly addresses [their challenge].

[Main value content - 2-3 paragraphs]

Hope this helps!
[Your name]
```

### Stage 2: Deeper Insight (Day 7)
**Purpose**: Educational content with soft CTA
**Content Options**:
- "3 things to look for when..."
- Process improvement guide
- ROI breakdown or calculator

**Template Structure**:
```
Subject: [Topic directly related to their pain point]

Hi [First Name],

After our discussion about [challenge], I wanted to share something we've learned from helping [similar companies].

[Educational content - 3-4 paragraphs]

[Soft CTA: "If you'd like to discuss how this applies to your situation..."]

Best,
[Your name]
```

### Stage 3: Check-In (Day 14)
**Purpose**: Brief, human touch point
**Characteristics**:
- Under 100 words
- Easy to reply to
- Casual, conversational

**Template Structure**:
```
Subject: Quick check-in

Hi [First Name],

Hope things are going well with [their project/initiative].

I know you mentioned [timeline/priority]. Just wanted to check if anything's changed or if there's anything I can help with in the meantime?

No pressure at all — just didn't want to leave you hanging if you needed anything.

[Your name]
```

### Stage 4: Re-Engagement (Day 30)
**Purpose**: Direct but respectful re-approach
**Elements**:
- Acknowledge time passed
- Reference specific value
- One clear CTA

**Template Structure**:
```
Subject: [Specific reference, not generic]

Hi [First Name],

I realize it's been a few weeks since we spoke about [specific challenge].

[Brief value reminder or new insight]

Would it make sense to reconnect for 15 minutes to see if this is still a priority? [Calendar link if appropriate]

If not, no worries — I'll check back in a few months.

Best,
[Your name]
```

### Stage 5: Long-Term Nurture (Day 60+)
**Purpose**: Quarterly touch with high value
**Content Types**:
- Major company updates
- Significant case studies
- Event invitations
- Market insights

**Template Structure**:
```
Subject: [Value-forward subject]

Hi [First Name],

[High-value content or update]

Thought you might find this interesting given [their situation].

Hope all is well!
[Your name]
```

## Configuration

### Required Settings

#### CRM Configuration
**HubSpot** (`.mcp.json`):
```json
{
  "mcpServers": {
    "hubspot": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-hubspot"],
      "env": {
        "HUBSPOT_ACCESS_TOKEN": "your-token"
      }
    }
  }
}
```

**Notion** (`.mcp.json`):
```json
{
  "mcpServers": {
    "notion": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-notion"],
      "env": {
        "NOTION_API_KEY": "your-key"
      }
    }
  }
}
```

#### Email Configuration
**Microsoft 365**:
```json
{
  "microsoft365": {
    "client_id": "your-client-id",
    "client_secret": "your-secret",
    "tenant_id": "your-tenant"
  }
}
```

### Optional Settings

#### Nurture Cadence
- `"standard"`: Days 3, 7, 14, 30, 60+
- `"accelerated"`: Days 2, 4, 7, 14, 30
- `"patient"`: Days 7, 14, 30, 60, 90+

#### Brand Voice
Configure in `settings.local.json`:
```json
{
  "brand_voice": "professional yet friendly",
  "industry_focus": ["SaaS", "Professional Services"],
  "value_props": ["efficiency", "scalability", "ROI"]
}
```

## Usage Modes

### Standalone Mode (No Integrations)
**Capabilities**:
- Manual email drafting
- Template suggestions
- Cadence tracking via conversation
- Manual CRM updates

**Workflow**:
1. Run `/nurture-sequences`
2. Provide lead information
3. Review generated email
4. Copy and send manually
5. Update tracking manually

### Supercharged Mode (With Integrations)
**Capabilities**:
- Automatic lead querying from CRM
- Scheduled email sending
- Reply detection and routing
- Automatic exit condition handling
- Engagement tracking

**Workflow**:
1. System queries CRM for nurture-stage leads
2. Generates personalized emails per template
3. Sends or queues for review
4. Monitors replies and engagement
5. Auto-exits on trigger conditions

## Exit Conditions

The system automatically removes leads from nurture when:

| Condition | Action | Next Step |
|-----------|--------|-----------|
| **Lead replies** | Exit nurture | Alert sales team |
| **Meeting booked** | Exit nurture | Enter discovery prep |
| **Unsubscribe** | Mark in CRM | No further contact |
| **Deal won** | Move to onboarding | Client success flow |
| **Deal lost** | Mark as lost | Quarterly check-ins only |
| **Email bounces** | Pause sequence | Verify contact info |
| **60+ days no engagement** | Move to long-term | Quarterly touches only |

## Batch Processing

### Pipeline Review
Run `/nurture-status` to see:
```
┌─────────────┬──────────────┬────────────┬──────────────┬─────────────┐
│ Lead Name   │ Company      │ Stage      │ Last Contact │ Next Action │
├─────────────┼──────────────┼────────────┼──────────────┼─────────────┤
│ John Smith  │ Acme Corp    │ Stage 2    │ 5 days ago   │ Day 7 email │
│ Jane Doe    │ Tech Co      │ Stage 3    │ 12 days ago  │ Check-in    │
│ Bob Johnson │ StartupXYZ   │ Stage 4    │ 28 days ago  │ Re-engage   │
└─────────────┴──────────────┴────────────┴──────────────┴─────────────┘
```

### Bulk Actions
- **Send all due**: Process all leads ready for next stage
- **Pause group**: Temporarily halt nurture for selected leads
- **Skip stage**: Move specific leads to next stage
- **Export list**: Generate CSV of nurture pipeline

### Re-engagement Signals
System detects and flags:
- Website visits after 14+ days silence
- Content downloads
- Email opens without replies
- Social media engagement

## Integration Points

### Upstream Integrations
**From Lead Capture**:
- Cold/Warm leads → Stage 1
- Discovery no-shows → Stage 1
- Lost deals → Stage 5

**From Post-Call Follow-up**:
- Not ready to buy → Stage 1
- Need more info → Stage 2
- Budget next quarter → Stage 4

### Downstream Integrations
**To Discovery Prep**:
- Meeting booked → Exit nurture
- Re-engaged lead → Prep with context

**To Proposal Assembly**:
- Ready to buy signal → Fast track
- RFP received → Immediate response

### Notification Channels
**Slack Integration**:
```json
{
  "channels": {
    "nurture_replies": "#leads",
    "meetings_booked": "#revenue",
    "re_engagement": "#opportunities"
  }
}
```

## Commands Reference

### `/nurture-sequences`
**Purpose**: Main nurture sequence skill
**Usage**:
```
/nurture-sequences
```
**Options**:
- Review pipeline
- Generate next batch
- Check individual lead
- Bulk process

### `/nurture-status`
**Purpose**: View nurture pipeline status
**Usage**:
```
/nurture-status [options]
```
**Options**:
- `--all`: Show all leads in nurture
- `--due`: Show only leads due for action
- `--stage [1-5]`: Filter by stage
- `--days [N]`: Show leads inactive for N+ days

## Best Practices

### Content Personalization
1. **Reference specific pain points** from discovery calls
2. **Use industry-specific examples** and case studies
3. **Mention company-specific details** (size, tools, challenges)
4. **Vary content types** across stages

### Timing Optimization
- **Send Tuesday-Thursday** for best open rates
- **10-11 AM or 2-3 PM** recipient's time zone
- **Avoid Mondays and Fridays** for initial touches
- **Respect holidays** and out-of-office replies

### Subject Line Strategy
- **Stage 1**: Curiosity + value ("Thought you'd find this useful")
- **Stage 2**: Specific benefit ("Reduce onboarding time by 50%")
- **Stage 3**: Personal ("Quick check-in")
- **Stage 4**: Urgency + value ("Last check on [specific opportunity]")
- **Stage 5**: Pure value ("New case study: [relevant industry]")

### Segmentation Tips
Segment nurture sequences by:
- **Industry vertical** (different pain points)
- **Company size** (different decision processes)
- **Engagement level** (hot, warm, cold)
- **Discovery stage** reached

## Troubleshooting

### Common Issues

#### Emails Not Sending
**Check**:
1. Email integration configured correctly
2. API tokens are valid
3. Send limits not exceeded
4. Email addresses are valid

**Solution**:
```bash
# Test email configuration
npm run test:email

# Verify tokens
npm run verify:tokens
```

#### CRM Sync Issues
**Check**:
1. CRM API connection
2. Field mappings correct
3. Permissions adequate
4. Rate limits

**Solution**:
```bash
# Re-sync CRM
npm run sync:crm --force

# Check field mappings
npm run check:mappings
```

#### Leads Not Progressing
**Check**:
1. Cadence settings
2. Exit conditions not triggered
3. Manual holds in place
4. Weekend/holiday pauses

**Solution**:
```
/nurture-status --debug
```

### Performance Optimization

#### For Large Lead Volumes (100+ leads)
1. **Enable batch processing**:
   ```json
   {
     "batch_size": 20,
     "batch_delay": 5000
   }
   ```

2. **Use queuing**:
   ```json
   {
     "queue_mode": true,
     "review_before_send": false
   }
   ```

3. **Implement rate limiting**:
   ```json
   {
     "emails_per_hour": 50,
     "api_calls_per_minute": 30
   }
   ```

#### For Better Engagement
1. **A/B test subject lines**
2. **Personalize preview text**
3. **Include social proof**
4. **Test different CTAs**
5. **Monitor and adjust cadence**

## Metrics and Reporting

### Key Metrics to Track
- **Open rate** by stage (target: 40%+)
- **Reply rate** by stage (target: 10%+)
- **Meeting booking rate** (target: 5%+)
- **Time in nurture** before conversion
- **Exit reason** distribution

### Reporting Commands
```bash
# Weekly nurture report
npm run report:nurture --period weekly

# Stage performance
npm run report:stages

# Lead engagement scores
npm run report:engagement
```

## Advanced Features

### Dynamic Content Insertion
Use placeholders for personalization:
- `{{first_name}}` - Lead's first name
- `{{company}}` - Company name
- `{{pain_point}}` - Primary challenge
- `{{discovery_date}}` - Date of discovery call
- `{{value_prop}}` - Relevant value proposition

### Conditional Logic
```json
{
  "conditions": [
    {
      "if": "industry == 'SaaS'",
      "then": "use_template: 'saas_nurture'"
    },
    {
      "if": "company_size > 100",
      "then": "use_cadence: 'enterprise'"
    }
  ]
}
```

### Multi-Channel Nurture
Combine email with:
- **LinkedIn**: Connection requests, message sequences
- **SMS**: Quick check-ins (with consent)
- **Direct mail**: High-value targets
- **Webinars**: Educational touches

## Support and Resources

### Documentation
- Main skill documentation: `lead-management/skills/nurture-sequences/SKILL.md`
- Command reference: `lead-management/commands/nurture-status.md`
- Integration guide: `lead-management/CONNECTORS.md`

### Getting Help
- **GitHub Issues**: Report bugs or request features
- **Slack Community**: `#lead-management-support`
- **Email Support**: support@your-company.com

### Updates and Roadmap
- **Current Version**: 1.0.0
- **Next Release**: Enhanced AI personalization
- **Future Features**:
  - Multi-channel orchestration
  - Predictive send time optimization
  - Advanced segmentation rules
  - Custom stage definitions

---

*Last updated: February 2026*
*Version: 1.0.0*
*Plugin: @claude-plugins/lead-management*