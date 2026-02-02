# Process Map: {{CLIENT_NAME}}

*Generated: {{DATE}}*
*Source: {{SOURCE}}*

---

## Process Overview

{{#each processes}}

## {{number}}. {{name}}

**Function Area**: {{function_area}}
**Owner**: {{owner}}
**Trigger**: {{trigger}}
**Frequency**: {{frequency}}
**Status**: {{status}}

### Current State Workflow

```mermaid
graph TD
    Start([{{trigger}}]) --> Step1
    {{#each steps}}
    Step{{number}}[{{name}}<br/>Who: {{who}}<br/>Tool: {{tool}}]
    {{#if pain_point}}
    Step{{number}} -.-> Pain{{number}}[⚠️ {{pain_point}}]
    {{/if}}
    {{#if next}}
    Step{{number}} --> Step{{next}}
    {{else}}
    Step{{number}} --> End([{{outcome}}])
    {{/if}}
    {{/each}}
```

### Detailed Steps

{{#each steps}}
#### Step {{number}}: {{name}}
- **Responsible**: {{who}}
- **Tool/System**: {{tool}}
- **Input**: {{input}}
- **Output**: {{output}}
- **Duration**: {{duration}}
{{#if pain_points}}
- **Pain Points**:
  {{#each pain_points}}
  - "{{this}}"
  {{/each}}
{{/if}}
{{#if manual}}
- **⚠️ Manual Process** - Automation opportunity
{{/if}}

{{/each}}

### Identified Bottlenecks

{{#each bottlenecks}}
#### {{type}} Bottleneck: {{name}}
- **Location**: {{location}}
- **Impact**: {{impact}}
- **Client Quote**: "{{quote}}"
- **Automation Potential**: {{automation_potential}}
{{#if metrics}}
- **Metrics**:
  - Volume: {{metrics.volume}}
  - Time Cost: {{metrics.time_cost}}
  - Error Rate: {{metrics.error_rate}}
{{/if}}

{{/each}}

### Process Metrics

| Metric | Current | Source |
|--------|---------|--------|
| Volume | {{metrics.volume}} | {{metrics.volume_source}} |
| Cycle Time | {{metrics.cycle_time}} | {{metrics.cycle_time_source}} |
| Error Rate | {{metrics.error_rate}} | {{metrics.error_rate_source}} |
| Cost | {{metrics.cost}} | {{metrics.cost_source}} |
| FTEs Involved | {{metrics.ftes}} | {{metrics.ftes_source}} |

### Pain Point Summary

{{#each pain_summary}}
- **{{category}}**: "{{quote}}" - {{impact}}
{{/each}}

### Missing Information

{{#each unknowns}}
- [ ] {{this}}
{{/each}}

---

{{/each}}

## Cross-Process Analysis

### Common Patterns
{{#each patterns}}
- **{{pattern}}**: Appears in {{processes}}
{{/each}}

### Integration Points
{{#each integrations}}
- {{from_process}} → {{to_process}}: {{connection}}
{{/each}}

### System Dependencies
{{#each systems}}
- **{{system}}**: Used in {{processes}}
{{/each}}

## Automation Opportunities

### Quick Wins (Can implement immediately)
{{#each quick_automation}}
- **{{process}}**: {{opportunity}} - {{estimated_impact}}
{{/each}}

### Medium-term (Requires some setup)
{{#each medium_automation}}
- **{{process}}**: {{opportunity}} - {{estimated_impact}}
{{/each}}

### Strategic (Requires significant investment)
{{#each strategic_automation}}
- **{{process}}**: {{opportunity}} - {{estimated_impact}}
{{/each}}

## Data Flow Diagram

```mermaid
graph LR
    {{#each data_flows}}
    {{source}}[{{source_name}}] -->|{{data_type}}| {{target}}[{{target_name}}]
    {{/each}}
```

## Follow-Up Questions

### Process Clarification
{{#each process_questions}}
1. {{this}}
{{/each}}

### Metrics & Measurement
{{#each metrics_questions}}
1. {{this}}
{{/each}}

### Technical Details
{{#each technical_questions}}
1. {{this}}
{{/each}}

## Notes

{{#each notes}}
- {{this}}
{{/each}}

---

*This process map was generated from: {{data_source}}*
*All information shown is directly from client statements. Items marked "UNKNOWN" require follow-up.*
*No metrics have been estimated or fabricated - all numbers are client-provided.*