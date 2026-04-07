# Jira Ticketing Lab — IT Service Management

A hands-on lab demonstrating how to design and implement an IT support ticketing system using **Jira Service Management**. This repo documents the configuration decisions, workflows, SLAs, and automation rules I built while standing up an IT helpdesk project from scratch.

## What This Lab Covers
- IT helpdesk project setup with custom issue types
- A 5-stage ticket lifecycle workflow with status transitions
- SLA configuration tied to priority levels
- JQL queries for daily IT operations and reporting
- Automation rules for ticket assignment and escalation
- Sample tickets walking through the full lifecycle

## Ticket Lifecycle

```
   ┌──────────┐    ┌─────────────┐    ┌──────────────┐    ┌──────────┐    ┌────────┐
   │   New    │───▶│  Assigned   │───▶│ In Progress  │───▶│ Resolved │───▶│ Closed │
   └──────────┘    └─────────────┘    └──────────────┘    └──────────┘    └────────┘
        │                │                   │                  │
        │                │                   ▼                  │
        │                │            ┌──────────────┐          │
        │                │            │   Pending    │          │
        │                │            │  (waiting    │          │
        │                │            │  on user)    │          │
        │                │            └──────────────┘          │
        │                │                   │                  │
        └────────────────┴───────────────────┴──────────────────┘
                              Can be reopened
```

## Repository Structure
```
Jira-Ticketing-Lab/
├── README.md
├── artifacts/
│   ├── issue-types.md          # Issue type configuration & fields
│   ├── workflow.md             # Workflow statuses, transitions, conditions
│   ├── sla-config.md           # SLA definitions by priority
│   ├── jql-queries.md          # Useful JQL queries for IT ops
│   ├── automation-rules.md     # Automation rule examples
│   └── sample-tickets.md       # Example tickets across the lifecycle
└── docs/
    └── setup-guide.md          # Step-by-step Jira setup walkthrough
```

## Key Decisions

| Area | Decision | Rationale |
|---|---|---|
| **Issue Types** | Incident, Service Request, Task, Problem | Aligns with ITIL service management categories |
| **Priorities** | Critical, High, Medium, Low | Drives SLA targets and auto-assignment |
| **Roles** | Agent, Admin, End User | Separation of duties for security and clarity |
| **Workflow** | 6 statuses with `Pending` for user wait | Captures real-world handoffs to end users |
| **SLAs** | Tied to priority, business hours only | Realistic for a mid-size IT team |
| **Self-Service Portal** | Enabled | Reduces ticket volume by ~30% in real deployments |

## Skills Demonstrated
- **Service Management Design** — issue types, workflows, SLAs aligned to ITIL practices
- **Jira Configuration** — projects, custom fields, workflow schemes, permission schemes
- **Automation** — rule-based assignment, escalation, notifications
- **JQL** — querying tickets for reporting and triage
- **Documentation** — clear technical writing for ops handoff

## Getting Started

1. Read [`docs/setup-guide.md`](docs/setup-guide.md) for the step-by-step Jira setup
2. Review the artifacts in [`artifacts/`](artifacts/) for the configuration details
3. Apply the patterns to your own Jira Service Management instance

## Future Enhancements
- AI-powered ticket categorization and routing
- Integration with IT asset management (Jira Assets / Snipe-IT)
- Slack/Teams integration for notifications
- Custom dashboards for IT performance KPIs

---
Built by [Metsam237](https://github.com/Metsam237)
