# Issue Type Configuration

## Issue Types

### 1. Incident
**Purpose:** Unplanned interruption or degradation of an IT service.
**Examples:** System outage, application crash, network down, email not working.

**Required Fields:**
- Summary
- Description
- Priority (Critical/High/Medium/Low)
- Affected Service
- Affected Users (count or group)
- Reporter

**Optional Fields:**
- Attachments (screenshots, logs)
- Linked Problem (if root cause identified)

---

### 2. Service Request
**Purpose:** A formal request from a user for something to be provided (access, software, hardware, information).
**Examples:** New laptop request, software license, VPN access, password reset.

**Required Fields:**
- Summary
- Description
- Request Category (Access / Hardware / Software / Information)
- Approver (for elevated requests)
- Reporter

---

### 3. Task
**Purpose:** Internal IT work that is not user-facing.
**Examples:** Server patching, certificate renewal, backup verification, license audit.

**Required Fields:**
- Summary
- Description
- Assignee
- Due Date

---

### 4. Problem
**Purpose:** The underlying root cause of one or more incidents.
**Examples:** Recurring memory leak in app X, faulty network switch causing intermittent outages.

**Required Fields:**
- Summary
- Description
- Linked Incidents (one or more)
- Root Cause (filled at resolution)
- Workaround (if available)

## Priority Matrix

| Priority | Impact | Urgency | Example |
|---|---|---|---|
| Critical | Org-wide | Immediate | Email server down |
| High | Department | Same day | Shared drive inaccessible |
| Medium | Team | 2 business days | Single user app issue |
| Low | Individual | 5 business days | Cosmetic UI bug |
