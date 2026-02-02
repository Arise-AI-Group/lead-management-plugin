# Opportunity Matrix for {{CLIENT_NAME}}

*Generated: {{DATE}}*
*Data Completeness: {{DATA_COMPLETENESS}}*

---

## Quick Wins 🎯
*High Impact + Low Effort = Implement First*

{{#each quick_wins}}
### {{id}}: {{name}}
- **Process**: {{process_name}}
- **Type**: {{type}}
- **Description**: {{description}}
- **Impact**: {{impact}} - {{impact_details}}
- **Effort**: {{effort}}
- **Speed to Value**: {{speed_to_value}}
- **Priority Score**: {{priority_score}}/10

**Why Now**: {{rationale}}

**Next Steps**:
1. {{next_step_1}}
2. {{next_step_2}}
3. {{next_step_3}}

---
{{/each}}

## Strategic Initiatives 🚀
*High Impact + Medium-High Effort = Plan for Q2*

{{#each strategic}}
### {{id}}: {{name}}
- **Process**: {{process_name}}
- **Type**: {{type}}
- **Description**: {{description}}
- **Impact**: {{impact}} - {{impact_details}}
- **Effort**: {{effort}}
- **Speed to Value**: {{speed_to_value}}
- **Priority Score**: {{priority_score}}/10

**Dependencies**: {{dependencies}}

**Data Requirements**:
{{#each data_requirements}}
- {{this}}
{{/each}}

**Risks**:
{{#each risks}}
- {{this}}
{{/each}}

---
{{/each}}

## Consider Later 📋
*Lower Priority or Very High Effort*

{{#each later}}
### {{id}}: {{name}}
- **Process**: {{process_name}}
- **Type**: {{type}}
- **Reason Delayed**: {{delay_reason}}
- **Revisit When**: {{revisit_condition}}

---
{{/each}}

## ROI Summary

{{#if roi_calculable}}
### Quantified Impact
- **Total Time Savings**: {{total_time_saved}}/week
- **Cost Reduction**: {{total_cost_reduction}}/month
- **Revenue Impact**: {{revenue_impact}}
- **Payback Period**: {{payback_period}}
- **Annual ROI**: {{annual_roi}}%
{{else}}
### Impact Assessment
**Note**: Specific ROI calculations require baseline metrics not provided during discovery.

**Qualitative Benefits**:
- {{benefit_1}}
- {{benefit_2}}
- {{benefit_3}}

**To Calculate ROI, We Need**:
{{#each missing_metrics}}
- [ ] {{this}}
{{/each}}
{{/if}}

## Implementation Approach

### Phase 1: Foundation (Weeks 1-4)
{{#each phase_1}}
- [ ] {{this}}
{{/each}}

### Phase 2: Expansion (Weeks 5-8)
{{#each phase_2}}
- [ ] {{this}}
{{/each}}

### Phase 3: Optimization (Weeks 9-12)
{{#each phase_3}}
- [ ] {{this}}
{{/each}}

## Success Metrics

### To Track from Day 1:
{{#each success_metrics}}
- **{{metric}}**: {{baseline}} → {{target}}
{{/each}}

## Required Follow-Up

### Missing Information:
{{#each unknowns}}
- [ ] {{this}}
{{/each}}

### Questions for Next Call:
{{#each follow_up_questions}}
1. {{this}}
{{/each}}

## Next Actions

### For Client:
{{#each client_actions}}
- [ ] {{this}}
{{/each}}

### For Agency:
{{#each agency_actions}}
- [ ] {{this}}
{{/each}}

---

*This opportunity matrix was generated from discovery transcript dated {{discovery_date}}. All metrics shown are from client-provided data. Items marked as "UNKNOWN" require follow-up discovery.*

## Notes
{{#each notes}}
- {{this}}
{{/each}}