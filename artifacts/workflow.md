# Workflow Configuration

## Statuses

| Status | Category | Description |
|---|---|---|
| `New` | To Do | Ticket created, not yet triaged |
| `Assigned` | To Do | Triaged and assigned to an agent |
| `In Progress` | In Progress | Agent actively working on it |
| `Pending` | In Progress | Waiting on end user response |
| `Resolved` | Done | Fix applied, awaiting confirmation |
| `Closed` | Done | Confirmed resolved by reporter or auto-closed after 5 days |

## Transitions

| From | To | Trigger | Conditions |
|---|---|---|---|
| New | Assigned | Manual / Automation | Assignee field must be set |
| Assigned | In Progress | Manual | Assignee must be current user |
| In Progress | Pending | Manual | Comment with reason required |
| Pending | In Progress | User responds (automation) | New comment from reporter |
| In Progress | Resolved | Manual | Resolution field required |
| Resolved | Closed | User confirms / Auto after 5 days | -- |
| Resolved | In Progress | Reopen by reporter | Within 14 days only |
| Closed | -- | Terminal state | -- |

## Validators
- **Resolution required**: Cannot transition to Resolved without filling Resolution field
- **Comment required**: Pending transition requires explanatory comment
- **Assignee required**: Cannot move from New unless an assignee is set

## Post-Functions
- On Resolved → notify reporter via email
- On Closed → trigger satisfaction survey
- On Pending → start "waiting on user" SLA clock
