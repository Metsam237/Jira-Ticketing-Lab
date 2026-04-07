# Jira Service Management Setup Guide

A step-by-step walkthrough for setting up an IT helpdesk project in Jira Service Management.

## Prerequisites
- Atlassian account
- Admin access to a Jira Cloud or Server instance
- Outline of your IT support team structure

## Step 1: Create the Project

1. From the Jira home page, click **Create project**
2. Select the **IT Service Management** template
3. Choose **Service Management** as the project type
4. Name it: `IT Helpdesk` (or your preferred name)
5. Set the project key: `ITHD`
6. Click **Create**

## Step 2: Configure Issue Types

Go to **Project settings → Issue types** and ensure these are enabled:

- Incident
- Service Request
- Task
- Problem

For each, configure the required fields per [`artifacts/issue-types.md`](../artifacts/issue-types.md).

## Step 3: Set Up the Workflow

1. Go to **Project settings → Workflows**
2. Edit the default workflow to match the diagram in [`artifacts/workflow.md`](../artifacts/workflow.md)
3. Add the following statuses:
   - New, Assigned, In Progress, Pending, Resolved, Closed
4. Configure transitions, validators, and post-functions as documented

## Step 4: Define Roles and Permissions

Navigate to **Project settings → People**:

| Role | Members | Permissions |
|---|---|---|
| Service Desk Team | Agents | Create, edit, transition, comment |
| Administrators | IT Admins | Full project admin |
| End Users | All staff | Create issues via portal only |

## Step 5: Configure SLAs

1. Go to **Project settings → SLAs**
2. Create two SLA goals:
   - **Time to First Response**
   - **Time to Resolution**
3. Set targets per priority as defined in [`artifacts/sla-config.md`](../artifacts/sla-config.md)
4. Configure pause conditions (status = Pending)

## Step 6: Set Up Automation Rules

1. Go to **Project settings → Automation**
2. Create rules from the templates in [`artifacts/automation-rules.md`](../artifacts/automation-rules.md)
3. Test each rule with a sample ticket before enabling

## Step 7: Enable the Customer Portal

1. Go to **Project settings → Portal**
2. Customize the welcome message and request types
3. Group request types into categories:
   - Get IT Help
   - Request Something
   - Report a Problem
4. Share the portal URL with end users

## Step 8: Set Up Email Channel

1. Go to **Project settings → Email requests**
2. Connect a support email address (e.g., `helpdesk@example.com`)
3. Configure the default request type for incoming emails (usually Service Request)

## Step 9: Verify with Test Tickets

Create a test ticket of each type and walk it through the full lifecycle:
- Verify automation rules fire
- Verify SLAs start/pause correctly
- Verify notifications are sent
- Verify reports show the ticket

## Step 10: Document and Train

- Share this guide with the IT team
- Run a 1-hour training session on the new workflow
- Set up a feedback channel for the first 2 weeks
