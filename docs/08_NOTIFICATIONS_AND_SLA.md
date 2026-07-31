# SpaceKrafters OS Notifications and SLA Rules

## 1. Notification Channels

Supported in-app channels:

- In-app notification center
- Email
- WhatsApp through an approved provider

Optional later channels:

- SMS
- Push notifications through a PWA or native app

Every notification should store recipient, channel, related record, scheduled time, send time, status and failure reason.

## 2. Notification Severity

### Informational

General assignment, successful submission or completed activity.

### Action Required

The recipient must complete an action before a due date.

### Warning

The due time is approaching or a project is at risk.

### Critical

An SLA has been breached, a budget is exceeded or a delivery/project is materially delayed.

## 3. Lead SLA Rules

### Initial Call

Trigger: Lead assigned to PC.

- Due: Within 2 hours
- Warning: Configurable, recommended at 90 minutes
- Breach recipients: Assigned PC and Owner
- Required breach action: PC enters reason and next action

Completion event:

- Valid call/contact activity recorded

### Appointment Update

Trigger: Lead created or qualified.

- Target: Appointment fixed or valid next-action reason recorded within 24 hours
- Warning: Recommended at 20 hours
- Breach recipients: PC and Owner

### Weekly Follow-Up

Trigger: Active lead remains unconverted and not lost.

- Frequency: Every 7 days
- Warning: On due morning
- Breach recipients: PC
- Escalation: Owner after configured overdue period

## 4. Site Visit SLA Rules

### Site Visit Confirmation

- Notify PC and SE on assignment
- Remind 24 hours before visit
- Remind 2 hours before visit

### Measurement Submission

- Trigger: Site visit marked started or completed
- Due: Configurable by business, recommended same day or next working day
- Warning: Assigned SE
- Breach: SE, PC and Owner based on severity

Site visit cannot close if mandatory checklist items are missing.

## 5. Proposal SLA Rules

### Missing Proposal Input

Trigger: Site measurement completed.

Parallel due tasks:

- QS preliminary BOQ
- Material specification
- Designer moodboard
- PC requirement summary review

Each input has an assignee and due date.

### Proposal Follow-Up

Trigger: Proposal sent.

- Create follow-up date
- Remind PC on due date
- Escalate if no interaction is recorded after configured period

## 6. Project Handover Notifications

Trigger: Project team assigned.

Recipients:

- Designer
- Site Engineer
- Other mandatory assignees

Actions:

- Accept handover
- Raise missing-input query

Escalation:

- Reminder before acceptance deadline
- Notify PC/Owner if not accepted

## 7. Design SLA Rules

### Designer Submission

- Trigger: Design task assigned
- Warning before due date
- Breach after due date
- Critical escalation when overdue by more than 2 days

Recipients:

- Designer
- PC
- Owner for critical delay

### Architect Review

- Trigger: Design submitted to architect
- Warning before review due date
- Breach to Architect and PC
- Escalation to Owner after configured delay

### Client Review Follow-Up

- Trigger: Design sent to client
- Assigned follow-up owner: Designer
- Repeated reminders based on configured interval
- Escalation if client response is not updated

### Revision Count

- Revision 1: Informational
- Revision 2: Warning that standard revision limit is reached
- Revision 3+: Mandatory reason and Owner notification

## 8. Payment Notifications

### Payment Due

Recipients:

- Accounts
- PC or Designer responsible for follow-up

Events:

- Milestone approaching due date
- Due today
- Overdue
- Partial payment received
- Payment received

Owner receives overdue summaries according to policy.

## 9. Task Notifications

Events:

- Task assigned
- Contributor assigned
- Dependency completed
- Input requested
- Due-date warning
- Overdue
- Blocked
- Submitted for review
- Changes requested
- Approved/completed

For parallel tasks, contributors receive their own due alerts while the accountable owner sees combined progress.

## 10. Daily Diary Rules

- Reminder near end of working day if no entry exists
- Missing-entry notice next working day
- Weekly compliance summary to employee and authorized manager
- Repeated non-compliance may reduce performance score based on policy

## 11. Budget Notifications

### Budget Thresholds

Recommended configurable thresholds:

- 70% used: Informational
- 85% used: Warning
- 95% used: Critical
- Over 100%: Block or require owner override

Recipients depend on role and project:

- Owner
- PC
- Accounts
- Purchase Head for procurement categories

### Budget Extension

Events:

- Request submitted
- Clarification requested
- Approved
- Rejected

## 12. Expense Notifications

Events:

- Expense submitted
- Proof missing
- Approval pending
- Approved
- Rejected
- Returned for correction

No expense should update actual budget until it reaches the configured approved status.

## 13. Procurement Notifications

### Purchase Requirement

- New request submitted
- Missing specification
- RFQ due

### Vendor Quotations

- Quote received
- Minimum quotation count not met
- Comparison ready
- Recommendation submitted

### Purchase Approval

- Approval requested
- Approval overdue
- Approved/rejected

### Purchase Order

- PO issued
- Vendor acknowledgement pending
- Delivery approaching
- Delivery overdue

### Material Receipt

- Delivery received
- Short quantity
- Damaged material
- Bill missing

## 14. Snag and Closure Notifications

Events:

- Snag assigned
- Snag due soon
- Snag overdue
- Closure evidence submitted
- Closure accepted/rejected
- Project ready for closure
- Project closure blocked

## 15. Feedback Notifications

Trigger: Seven days after project completion.

Flow:

1. Create feedback request.
2. Send client link.
3. Remind after configured interval if no response.
4. Notify PC when feedback is received.
5. Notify Owner for ratings below configured threshold.

## 16. Escalation Policy Structure

Each SLA may define several escalation steps.

Example:

| Step | Timing | Recipient | Channel |
|---|---|---|---|
| Warning | 30 minutes before due | Assignee | In-app |
| Breach | At due time | Assignee + Manager | In-app + Email |
| Escalation 1 | 2 hours overdue | Owner | In-app |
| Escalation 2 | 1 working day overdue | Owner | Email/WhatsApp |

## 17. Working Hours and Holidays

SLA calculation must support:

- Company timezone
- Working hours
- Weekly holidays
- Public/company holidays
- Optional pause when record is formally placed on hold

The two-hour lead-call SLA should clearly define whether it is business-hour based or elapsed time based. This must be configurable.

## 18. Delay Reason Requirements

Mandatory reason fields should appear for:

- Missed lead call SLA
- Appointment not fixed
- Design overdue
- Revision above two
- Task overdue with manual closure
- Budget extension
- Purchase/delivery delay
- Project stage delay

Delay reason records should include:

- Category
- Description
- Responsible party
- Corrective action
- New expected date

## 19. Notification Templates

Templates require variables such as:

- Recipient name
- Lead/project number
- Client/project name
- Assigned user
- Due date/time
- Days/hours overdue
- Required action
- Direct record link

Example in-app message:

`Lead SKL-1023 has not been contacted within the 2-hour SLA. Add the delay reason and next action.`

## 20. Notification Preferences

Users may control optional notifications, but mandatory compliance notifications cannot be disabled.

Configurable preferences:

- In-app
- Email
- WhatsApp
- Daily digest
- Immediate alerts

## 21. Delivery and Retry

- Failed email/WhatsApp sends should be retried.
- Permanent failure must be visible to an administrator.
- Duplicate notifications should be prevented using event and recipient identifiers.
- All critical alerts must remain visible in-app even if external delivery fails.