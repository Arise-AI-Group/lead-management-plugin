# Discovery Follow-Up Questions: {{CLIENT_NAME}}

*Generated: {{DATE}}*
*From Discovery: {{DISCOVERY_DATE}}*

---

## Critical Unknowns
*Must have answers before proposal*

### Financial Metrics
{{#each financial_unknowns}}
- [ ] {{this}}
{{/each}}

### Volume & Frequency
{{#each volume_unknowns}}
- [ ] {{this}}
{{/each}}

### Time & Resources
{{#each time_unknowns}}
- [ ] {{this}}
{{/each}}

### Process Details
{{#each process_unknowns}}
- [ ] {{this}}
{{/each}}

---

## Nice to Have
*Would improve proposal accuracy*

### System Information
{{#each system_questions}}
- [ ] {{this}}
{{/each}}

### Team Structure
{{#each team_questions}}
- [ ] {{this}}
{{/each}}

### Current Costs
{{#each cost_questions}}
- [ ] {{this}}
{{/each}}

---

## Follow-Up Email Template

Subject: Quick Follow-up Questions from Our Discovery Call

Hi {{CLIENT_FIRST_NAME}},

Thanks again for taking the time to walk through your processes yesterday. I'm putting together the opportunity assessment and have a few quick questions that will help me be more specific with the recommendations:

**Quick Numbers** (estimates are fine):
{{#each top_5_questions}}
{{number}}. {{question}}
{{/each}}

No need to be exact - ballpark figures work great. This helps me:
- Calculate accurate ROI projections
- Size the solution appropriately
- Prioritize quick wins

Could you either:
a) Reply with quick answers, or
b) Let me know a good time for a 15-min call?

I'll have the opportunity matrix ready by {{DELIVERY_DATE}}.

Best,
{{SENDER_NAME}}

---

## Internal Notes

### Why We Need This Information

{{#each why_needed}}
**{{metric}}**: {{reason}}
{{/each}}

### Alternative Data Sources
*If client can't provide*

{{#each alternatives}}
- **{{metric}}**: {{alternative_source}}
{{/each}}

### Assumptions We Could Make
*Only if absolutely necessary*

{{#each potential_assumptions}}
- **{{metric}}**: {{assumption}} ({{confidence}} confidence)
  - Flag as assumption in audit.json
  - Note source: "{{source}}"
  - Validation needed: {{validation}}
{{/each}}

---

## Discovery Call Gaps

### Topics Not Covered
{{#each missed_topics}}
- {{this}}
{{/each}}

### Processes Mentioned But Not Explored
{{#each unexplored_processes}}
- **{{process}}**: {{what_we_know}}
{{/each}}

### Stakeholders to Interview
{{#each stakeholders}}
- **{{name}}** ({{role}}): {{why_important}}
{{/each}}

---

## Next Discovery Session Agenda
*If follow-up call needed*

**Duration**: 30 minutes

**Agenda**:
1. **Financial Metrics** (10 min)
   {{#each financial_agenda}}
   - {{this}}
   {{/each}}

2. **Process Details** (10 min)
   {{#each process_agenda}}
   - {{this}}
   {{/each}}

3. **Success Criteria** (5 min)
   {{#each success_agenda}}
   - {{this}}
   {{/each}}

4. **Next Steps** (5 min)
   - Confirm proposal timeline
   - Schedule presentation

---

## Quality Gate Checklist

Before sending proposal, we must have:
{{#each must_haves}}
- [ ] {{this}}
{{/each}}

If missing any of above:
1. Schedule follow-up call
2. Or state clearly in proposal: "Pending [metric]"
3. Provide range estimates with assumptions noted

---

*Remember: Never fabricate missing data. Always mark as UNKNOWN and follow up.*