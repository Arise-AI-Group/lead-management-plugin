# Opportunity Assessment Pipeline

## Workflow Overview

This pipeline transforms discovery meeting content into actionable business intelligence while maintaining strict data integrity.

---

## Pre-Flight Checklist

Before starting assessment:
- [ ] Transcript available (30+ minutes)
- [ ] Client name confirmed
- [ ] Output destination selected
- [ ] Validation mode enabled

---

## Phase-by-Phase Execution

### 📋 Phase 1: Initialize (2 minutes)

#### Actions
1. **Locate transcript source**
   ```
   Priority: Fireflies → Notion → Local → Manual
   ```

2. **Create working structure**
   ```json
   {
     "client_id": "[client-name]-[date]",
     "created_date": "[today]",
     "audit_status": "in_progress",
     "data_completeness": "unknown"
   }
   ```

3. **Set tracking arrays**
   - unknowns[]
   - assumptions_made[]
   - validated_facts[]

#### Validation Gate
- ✅ Transcript loaded
- ✅ Client identified
- ✅ Structure initialized

---

### 🔍 Phase 2: Extract Facts (10 minutes)

#### Actions
1. **Parse for company details**
   ```
   LOOK FOR: Company name, size, industry, revenue
   IF MISSING: Set to null, add to unknowns
   ```

2. **Extract pain points**
   ```
   RULE: Must be direct quote
   FORMAT: "Line [X]: '[exact quote]'"
   ```

3. **Identify current tools**
   ```
   CAPTURE: System names mentioned
   IGNORE: Systems you think they "must" use
   ```

4. **Document business goals**
   ```
   IF STATED: Record exactly
   IF IMPLIED: Mark as "Inferred - needs validation"
   IF ABSENT: Leave null
   ```

#### Quality Check
```
For each fact extracted, ask:
"What line number in transcript?"
If can't answer → Move to unknowns
```

#### Validation Gate
- ✅ No fabricated metrics
- ✅ All facts sourced
- ✅ Unknowns documented

---

### 🗺️ Phase 3: Map Processes (15 minutes)

#### Actions
1. **Identify processes discussed**
   ```
   MIN REQUIREMENT: Name + 2 steps + 1 pain point
   ```

2. **For each process, document:**
   ```markdown
   Process: [Client's name for it]
   Trigger: [What starts it]
   Steps:
     1. [Step as described]
        - Who: [Person/role mentioned]
        - Tool: [System if stated]
        - Pain: "[Quote if mentioned]"
     2. [Next step mentioned]
        ...
   ```

3. **Mark gaps**
   ```
   Missing steps: "UNKNOWN - [what's missing]"
   Missing metrics: null (don't guess)
   ```

4. **Identify bottlenecks**
   ```
   Type: Manual|Dependency|Visibility|Standardization
   Location: [Process step]
   Evidence: "[Client quote]"
   ```

#### Process Quality Criteria
- Name matches client terminology
- At least 2 concrete steps
- One or more pain points quoted
- No invented "obvious" steps

#### Validation Gate
- ✅ Each step traceable to transcript
- ✅ Pain points are quotes
- ✅ No assumed steps

---

### 💡 Phase 4: Identify Opportunities (10 minutes)

#### Actions
1. **Link each pain to opportunity**
   ```
   Pain: "Manual data entry taking forever"
   Opportunity: Automate data capture
   Type: Automation
   Category: Data Entry
   ```

2. **Score qualitatively**
   ```
   Impact: high|medium|low (based on frequency × severity)
   Effort: high|medium|low (based on complexity)
   Speed: days|weeks|months (general estimate)
   ```

3. **Calculate priority**
   ```
   Formula: (Impact × 2) + (3 - Effort)
   Range: 1-9 (9 = highest priority)
   ```

4. **Categorize by implementation**
   ```
   Quick Win: High impact + Low effort
   Strategic: High impact + Medium/High effort
   Later: Low impact OR Very high effort
   ```

#### ROI Handling
```
IF client provided metrics:
  Calculate: Time saved × Rate = Value
ELSE:
  State: "ROI: TBD - requires baseline metrics"
  List: What metrics needed for calculation
```

#### Validation Gate
- ✅ Each opportunity linked to stated pain
- ✅ No fabricated ROI numbers
- ✅ Priority scores justified

---

### 📊 Phase 5: Generate Outputs (5 minutes)

#### Actions
1. **Complete audit.json**
   ```bash
   Review all fields for:
   - Completeness (null is OK)
   - Accuracy (matches transcript)
   - No fabrication
   ```

2. **Generate opportunity-matrix.md**
   ```
   Structure:
   - Quick Wins (top 3-5)
   - Strategic (next 3-5)
   - Later (remaining)
   ```

3. **Create process-map.md**
   ```
   Include:
   - Visual workflow
   - Bottleneck markers
   - Pain point annotations
   ```

4. **Compile discovery-unknowns.md**
   ```
   Organize by:
   - Critical (blocks proposal)
   - Important (improves accuracy)
   - Nice-to-have (additional context)
   ```

#### Final Validation
```python
for output in [audit.json, opportunity-matrix.md, process-map.md]:
    if contains_fabricated_metric:
        REJECT and fix
    if missing_source_attribution:
        ADD reference
    if includes_assumptions:
        MARK clearly
```

#### Validation Gate
- ✅ All outputs generated
- ✅ Zero fabricated metrics
- ✅ Unknowns documented
- ✅ Ready for client review

---

## Post-Pipeline Actions

### Immediate
1. **Save outputs**
   ```
   Location: [client]/discovery/
   Format: JSON + Markdown
   ```

2. **Update tracking**
   ```
   Status: discovery_complete
   Next: proposal_assembly
   ```

3. **Notify team**
   ```
   Channel: #sales-wins
   Message: "Assessment complete for [client]"
   Attach: opportunity-matrix.md
   ```

### Within 24 Hours
1. **Client validation**
   - Send process summary
   - Confirm accuracy
   - Gather missing metrics

2. **Internal review**
   - Check quality standards
   - Validate opportunities
   - Assign ownership

3. **Trigger next skill**
   - `/proposal-assembly [client]`

---

## Quality Metrics

Track for continuous improvement:
- **Data completeness**: % fields with values vs unknowns
- **Validation accuracy**: Client confirmation rate
- **Opportunity conversion**: % that make it to proposal
- **Time to value**: Days from assessment to implementation

---

## Troubleshooting Guide

### Issue: "Not enough content to assess"
**Solution**:
- Check transcript length (need 500+ words)
- Verify recording quality
- Schedule deeper discovery call

### Issue: "All metrics are unknown"
**Solution**:
- Normal for first call
- Generate follow-up questions
- Schedule metrics-focused call

### Issue: "Can't identify clear processes"
**Solution**:
- Ask for specific examples
- Focus on daily activities
- Map "a day in the life"

### Issue: "Client disputes findings"
**Solution**:
- Review source quotes
- Check for interpretation errors
- Update with corrections

---

## Pipeline Configuration

### Environment Settings
```yaml
validation_level: strict
hallucination_check: enabled
output_format: markdown
connector_fallback: true
auto_save: true
```

### Time Allocation
```yaml
initialize: 2_minutes
extract_facts: 10_minutes
map_processes: 15_minutes
identify_opportunities: 10_minutes
generate_outputs: 5_minutes
buffer: 3_minutes
total: 45_minutes
```

---

## Success Criteria

Pipeline successful when:
1. ✅ Transcript fully processed
2. ✅ No fabricated data
3. ✅ Opportunities identified
4. ✅ Outputs validated
5. ✅ Team notified
6. ✅ Next steps clear

---

## Notes

- This pipeline prioritizes accuracy over completeness
- Unknowns are features, not bugs
- Client validation is part of the process
- Each phase builds on the previous
- Validation gates are mandatory

**Golden Rule**: When in doubt, mark UNKNOWN and ask.