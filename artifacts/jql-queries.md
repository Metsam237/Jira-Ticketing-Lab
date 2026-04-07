# Useful JQL Queries

A collection of JQL (Jira Query Language) queries I use for daily IT operations and reporting.

## Daily Triage

**My open tickets, sorted by priority then age:**
```jql
assignee = currentUser() AND statusCategory != Done
ORDER BY priority DESC, created ASC
```

**Unassigned tickets created in the last 24h:**
```jql
project = "IT Helpdesk" AND assignee is EMPTY AND created >= -1d
ORDER BY priority DESC
```

**Tickets waiting on user for more than 3 days:**
```jql
status = "Pending" AND updated <= -3d
```

## SLA Monitoring

**Tickets approaching SLA breach (within 1 hour):**
```jql
"Time to resolution" = breached() OR "Time to resolution" = breachTime("1h")
```

**Critical incidents currently open:**
```jql
issuetype = Incident AND priority = Critical AND statusCategory != Done
```

## Reporting

**All tickets resolved last week:**
```jql
project = "IT Helpdesk" AND status changed to Resolved DURING (startOfWeek(-1), endOfWeek(-1))
```

**Top reporters this month:**
```jql
project = "IT Helpdesk" AND created >= startOfMonth()
ORDER BY reporter
```

**Mean time to resolution by priority:**
Use the **Resolution Time Report** with this filter:
```jql
project = "IT Helpdesk" AND resolved >= -30d
```

## Problem Management

**Incidents linked to a problem:**
```jql
issue in linkedIssues("PROB-42")
```

**Problems with no workaround documented:**
```jql
issuetype = Problem AND "Workaround" is EMPTY AND statusCategory != Done
```

## Cleanup

**Stale tickets (no update in 14 days):**
```jql
project = "IT Helpdesk" AND statusCategory != Done AND updated <= -14d
ORDER BY updated ASC
```
