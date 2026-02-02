# Lead Management Plugins

Plugins that turn Claude into a lead management specialist for small businesses. Built for [Claude Cowork](https://claude.com/product/cowork), also compatible with [Claude Code](https://claude.com/product/claude-code).

## What This Is

A productized lead management system delivered as a Claude Cowork plugin. Covers the full pipeline from first contact to paid invoice — lead capture, discovery prep, follow-up, proposals, contracts, nurture, invoicing, and content creation.

Built by [Arise AI Group](https://arisegroup.ai) for small businesses that need effective lead management without the overhead of complex CRM setups or dedicated sales ops.

## Who It's For

- **Small service businesses** (agencies, consultancies, freelancers) with 1-10 person sales teams
- **Founders** who handle sales themselves and need a system, not a full-time hire
- **Teams** that capture leads from multiple sources (website, events, referrals) and lose track of follow-ups
- **Anyone** tired of leads going cold because nobody followed up in time

## Plugin

| Plugin | How it helps | Connectors |
|--------|-------------|------------|
| **[lead-management](./lead-management)** | Capture leads, prep for calls, draft follow-ups, assemble proposals, track contracts, nurture prospects, manage invoices, and repurpose meetings into content. | Slack, HubSpot, Notion, Fireflies, Microsoft 365 |

## Getting Started

```bash
# Install the plugin
claude plugins add lead-management-plugin/lead-management

# Or install from the marketplace
claude plugins add lead-management
```

Once installed, skills activate automatically when relevant, and slash commands are available in your session.

### Available Commands

| Command | What It Does |
|---------|-------------|
| `/lead-management:capture-lead` | Quick-capture a lead from any source with AI scoring |
| `/lead-management:pipeline-review` | Review pipeline health, stalled deals, conversion metrics |
| `/lead-management:prep-call` | Prepare for a discovery or sales call |
| `/lead-management:draft-followup` | Draft personalized follow-up after a call |
| `/lead-management:opportunity-assessment` | Transform discovery transcript into opportunity matrix |
| `/lead-management:send-proposal` | Assemble and route a proposal for review |
| `/lead-management:nurture-status` | Check nurture sequence status across all leads |

### Automatic Skills

These activate based on what you're doing — no command needed:

| Skill | Activates When You... |
|-------|----------------------|
| Lead Capture | Mention a new lead, contact, or form submission |
| Discovery Prep | Talk about meeting prep, upcoming calls, or pre-meeting tasks |
| Post-Call Follow-Up | Discuss call notes, transcripts, or follow-up emails |
| Opportunity Assessment | Process discovery transcripts into structured assessments |
| Proposal Assembly | Need a proposal, quote, or SOW |
| Nurture Sequences | Ask about drip campaigns, cold leads, or re-engagement |
| Contract Management | Work with contracts, e-signatures, or signing status |
| Invoice Tracking | Handle invoicing, payments, or revenue tracking |
| Content Engine | Want to repurpose meetings into marketing content |

## Architecture

This plugin follows the [knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) architecture from Anthropic:

- Same file structure, conventions, and `~~placeholder` system
- Can be installed alongside other knowledge-work-plugins (sales, productivity, etc.)
- Compatible with the `cowork-plugin-management` plugin for customization
- Every component is file-based — markdown and JSON, no code, no infrastructure, no build steps

## Customizing for Your Business

These plugins ship as a generic starting point. They become much more useful when you customize them:

1. **Swap connectors** — Edit `.mcp.json` to point at your specific tools (Salesforce instead of HubSpot, Gmail instead of Microsoft 365, etc.)
2. **Add your context** — Drop your company info, service offerings, and pricing into the skill files
3. **Adjust workflows** — Modify skill instructions to match how your team actually operates
4. **Customize email templates** — Update the email drafts in each skill to match your brand voice

Use the `cowork-plugin-management` plugin or the [CONNECTORS.md](./lead-management/CONNECTORS.md) reference to identify what to swap.

## Pipeline Coverage

The plugin covers every stage of the lead-to-revenue pipeline:

```
LEAD ENTRY           → lead-capture skill + /capture-lead command
DISCOVERY PREP       → discovery-prep skill + /prep-call command
POST-CALL            → post-call-followup skill + /draft-followup command
OPPORTUNITY ASSESS   → opportunity-assessment skill + /opportunity-assessment command
PROPOSAL             → proposal-assembly skill + /send-proposal command
CONTRACT             → contract-management skill
INVOICE & PAYMENT    → invoice-tracking skill
NURTURE (parallel)   → nurture-sequences skill + /nurture-status command
CONTENT (parallel)   → content-engine skill
PIPELINE OVERVIEW    → /pipeline-review command
```

## Contributing

Plugins are markdown files. Fork the repo, make your changes, and submit a PR.

## License

Apache-2.0 — see [LICENSE](./LICENSE)
