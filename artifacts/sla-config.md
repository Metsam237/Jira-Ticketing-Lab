# SLA Configuration

SLAs are tied to **Priority** and measured in **business hours** (Mon-Fri 9am-5pm local time).

## Time to First Response
The time from ticket creation until an agent first responds.

| Priority | Target |
|---|---|
| Critical | 15 minutes |
| High | 1 hour |
| Medium | 4 business hours |
| Low | 1 business day |

## Time to Resolution
The total time from ticket creation until ticket reaches Resolved status.

| Priority | Target |
|---|---|
| Critical | 4 business hours |
| High | 1 business day |
| Medium | 3 business days |
| Low | 5 business days |

## SLA Pause Conditions
The SLA clock pauses when status is:
- `Pending` (waiting on user response)

The clock resumes when the user responds and status returns to `In Progress`.

## Breach Actions
- **75% of SLA elapsed** → Notify assignee
- **90% of SLA elapsed** → Escalate to team lead
- **100% (breached)** → Notify manager + flag in dashboard
