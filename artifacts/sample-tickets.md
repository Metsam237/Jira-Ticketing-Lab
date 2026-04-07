# Sample Tickets

Three example tickets showing how the system handles different scenarios end-to-end.

---

## Ticket 1: Critical Incident — Email Outage

**Key:** ITHD-1042
**Type:** Incident
**Priority:** Critical
**Reporter:** jane.doe@example.com
**Assignee:** john.smith (Network Team)

**Summary:** Company-wide email outage — Outlook not connecting

**Description:**
> Multiple users reporting they cannot send or receive email since 9:15am.
> Outlook shows "Disconnected from server". Webmail also unreachable.
> Estimated 200+ users affected.

**Lifecycle:**
| Time | Status | Action |
|---|---|---|
| 09:18 | New | Auto-created from monitoring alert |
| 09:19 | Assigned | Auto-assigned to network-team |
| 09:22 | In Progress | John acknowledged, started investigation |
| 09:35 | In Progress | Identified failed Exchange node, failover initiated |
| 09:48 | Resolved | Service restored, all users reconnected |
| 09:50 | -- | Linked to PROB-87 (Exchange cluster instability) |
| 14:00 | Closed | Reporter confirmed resolution |

**SLA:** Time to First Response = 1 min ✅ | Time to Resolution = 30 min ✅

---

## Ticket 2: Service Request — New Software License

**Key:** ITHD-1156
**Type:** Service Request
**Priority:** Low
**Reporter:** alex.chen@example.com
**Assignee:** maria.lopez (Software Team)

**Summary:** Need Adobe Photoshop license for design work

**Description:**
> Joining the design team next Monday and need Photoshop installed
> on my MacBook before then. Manager has approved (see attached email).

**Lifecycle:**
| Day | Status | Action |
|---|---|---|
| Day 1 | New → Assigned | Auto-routed to software-team |
| Day 1 | In Progress | Maria verified manager approval, ordered license |
| Day 2 | Pending | Waiting on Adobe portal provisioning |
| Day 3 | In Progress | License received, scheduled install with Alex |
| Day 4 | Resolved | Photoshop installed and tested |
| Day 5 | Closed | Alex confirmed working |

**SLA:** Time to Resolution = 3 business days ✅

---

## Ticket 3: Recurring Problem — Wi-Fi Drops in Conference Room B

**Key:** PROB-87
**Type:** Problem
**Priority:** Medium
**Linked Incidents:** ITHD-998, ITHD-1015, ITHD-1033

**Summary:** Conference Room B Wi-Fi drops every 30-45 minutes

**Root Cause Analysis:**
> Investigation traced the issue to an aging Cisco AP (model 2702i)
> with degraded radio performance. Channel interference from a nearby
> microwave compounds the issue during lunch hours.

**Workaround:**
> Use the wired connection at the conference table podium until AP is replaced.

**Resolution:**
> Replaced AP with Cisco 9120 model. Issue has not recurred in 30 days.

**Outcome:**
- 3 incidents prevented per month
- Added preventive: AP refresh program for all units > 5 years old
