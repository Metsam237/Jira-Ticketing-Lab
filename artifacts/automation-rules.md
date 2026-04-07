# Automation Rules

Automation rules I configured to reduce manual work and enforce process consistency.

## Rule 1: Auto-Assign by Category

**Trigger:** Issue created
**Condition:** `Request Category` is set
**Action:** Assign to user based on category

| Category | Assignee Group |
|---|---|
| Hardware | hardware-team |
| Software | software-team |
| Access | identity-team |
| Network | network-team |

## Rule 2: Critical Incident Escalation

**Trigger:** Issue created
**Condition:** Priority = Critical AND Issue Type = Incident
**Actions:**
1. Add label `critical-incident`
2. Notify `#it-incidents` Slack channel
3. Page on-call via PagerDuty webhook
4. Create linked sub-task: "Post-incident review"

## Rule 3: Auto-Close Resolved Tickets

**Trigger:** Scheduled (daily at 2am)
**Condition:** Status = Resolved AND last updated > 5 days ago
**Actions:**
1. Transition to Closed
2. Add comment: "Auto-closed after 5 days with no response. Reopen if needed."

## Rule 4: Reopen on User Comment

**Trigger:** Comment added
**Condition:** Status = Resolved AND commenter = reporter
**Actions:**
1. Transition to In Progress
2. Notify previous assignee
3. Add comment: "Ticket reopened by reporter."

## Rule 5: SLA Breach Warning

**Trigger:** SLA changed
**Condition:** Time to Resolution remaining < 1 hour AND status != Done
**Actions:**
1. Add label `sla-warning`
2. Email assignee + team lead
3. Add internal comment with SLA details

## Rule 6: Stale Ticket Reminder

**Trigger:** Scheduled (Mondays at 9am)
**Condition:** Status = Pending AND last updated > 7 days
**Actions:**
1. Email reporter: "We are still waiting on your response..."
2. CC assignee
