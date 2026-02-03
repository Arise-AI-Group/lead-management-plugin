# Nurture Sequence Quick Reference

## 🚀 Quick Commands

| Command | Purpose | Example |
|---------|---------|---------|
| `/nurture-sequences` | Start nurturing leads | Process next batch of emails |
| `/nurture-status` | View pipeline status | See all leads in nurture |
| `/nurture-status --due` | Show leads ready for action | Today's nurture tasks |
| `/nurture-status --stage 3` | Filter by stage | See all Stage 3 leads |

## 📅 Standard Cadence Timeline

```
Day 0  - Discovery call / Lead capture
Day 3  - Stage 1: Value drop (no CTA)
Day 7  - Stage 2: Educational content (soft CTA)
Day 14 - Stage 3: Brief check-in
Day 30 - Stage 4: Re-engagement attempt
Day 60+- Stage 5: Long-term quarterly touches
```

## ✉️ Email Templates Cheat Sheet

### Stage 1 (Day 3) - Pure Value
```
Subject: Thought you'd find this useful — [topic]
- Share case study/tool/insight
- NO call-to-action
- 2-3 paragraphs max
```

### Stage 2 (Day 7) - Education + Soft CTA
```
Subject: [Specific pain point topic]
- "3 things" format works well
- Include soft CTA at end
- 3-4 paragraphs
```

### Stage 3 (Day 14) - Check-In
```
Subject: Quick check-in
- Under 100 words
- Super casual tone
- Easy yes/no question
```

### Stage 4 (Day 30) - Direct Re-engagement
```
Subject: [Specific, not generic]
- Acknowledge time passed
- One clear CTA
- Offer to pause if not ready
```

### Stage 5 (Day 60+) - Quarterly Value
```
Subject: [Value-forward]
- Major updates only
- Case studies
- No pressure to respond
```

## 🎯 Personalization Variables

```javascript
{{first_name}}      // Lead's first name
{{company}}         // Company name
{{pain_point}}      // Primary challenge discussed
{{discovery_date}}  // Date of discovery call
{{industry}}        // Their industry
{{competitor}}      // Mentioned competitor
{{timeline}}        // Their stated timeline
{{budget_range}}    // If discussed
```

## 🚪 Exit Conditions (Automatic)

| Trigger | What Happens | Next Action |
|---------|-------------|-------------|
| Lead replies | Exit nurture | Sales team alerted |
| Books meeting | Exit nurture | Discovery prep |
| Unsubscribes | Exit + mark | No contact |
| Deal closes (won) | Exit | Client onboarding |
| Deal closes (lost) | Exit | Quarterly only |
| Email bounces | Pause | Verify email |

## 🔄 Batch Processing Workflow

1. **Morning Check** (9 AM)
   ```
   /nurture-status --due
   ```

2. **Review & Personalize**
   - Check context from discovery notes
   - Adjust templates as needed
   - Add specific examples

3. **Send Batch**
   ```
   /nurture-sequences
   > Option: Process all due
   ```

4. **Log & Track**
   - Update CRM stages
   - Note any manual touches
   - Flag hot leads

## 📊 Pipeline Status View

```
┌──────────┬─────────┬───────┬──────────┬────────────┐
│ Lead     │ Company │ Stage │ Last     │ Next       │
├──────────┼─────────┼───────┼──────────┼────────────┤
│ J. Smith │ Acme    │ 2     │ 5 days   │ Day 7 email│
│ J. Doe   │ TechCo  │ 3     │ 12 days  │ Check-in   │
└──────────┴─────────┴───────┴──────────┴────────────┘
```

## 🎨 Best Practices

### Subject Lines That Work
- ✅ "Thought you'd find this useful — automation tips"
- ✅ "Quick question about [their goal]"
- ✅ "Reduce [pain point] by 50% — case study"
- ❌ "Following up"
- ❌ "Just checking in"
- ❌ "Our services"

### Timing Tips
- **Best days**: Tuesday, Wednesday, Thursday
- **Best times**: 10-11 AM, 2-3 PM (their timezone)
- **Avoid**: Mondays, Fridays, holidays
- **Stage 3 check-in**: Mid-week afternoon

### Personalization Levels
1. **Minimum** (Required)
   - First name
   - Company name
   - One specific reference

2. **Standard** (Recommended)
   - Pain point mentioned
   - Industry context
   - Timeline reference

3. **Premium** (High-value leads)
   - Competitor comparisons
   - Custom ROI calculations
   - Team member names

## 🔧 Troubleshooting Quick Fixes

| Issue | Quick Check | Fix |
|-------|-------------|-----|
| Emails not sending | Check API tokens | `npm run verify:tokens` |
| Low open rates | Review subject lines | A/B test new ones |
| No replies | Check Stage 3 timing | Make it easier to reply |
| CRM out of sync | Check field mappings | `npm run sync:crm` |

## 📈 Target Metrics

| Metric | Target | Red Flag |
|--------|--------|----------|
| Open rate | 40%+ | Under 25% |
| Reply rate | 10%+ | Under 5% |
| Meeting rate | 5%+ | Under 2% |
| Unsubscribe | <2% | Over 5% |
| Bounce rate | <3% | Over 5% |

## 🆘 Emergency Commands

```bash
# Pause all nurture sequences
/nurture-sequences --pause-all

# Resume after pause
/nurture-sequences --resume-all

# Check system health
npm run health:check

# Export pipeline for backup
/nurture-status --export csv
```

## 🔗 Related Skills

- **Before Nurture**: `/lead-capture`, `/discovery-call`
- **During Nurture**: `/nurture-sequences`, `/nurture-status`
- **After Nurture**: `/discovery-prep`, `/proposal-assembly`
- **Analytics**: `/pipeline-report`, `/engagement-metrics`

---

**Pro Tip**: Keep discovery call notes detailed! The more context you have, the better your nurture emails will perform. Use `{{discovery_notes}}` to pull in relevant details.

**Remember**: The goal isn't to convince them to buy, it's to stay helpful and top-of-mind until they're ready.