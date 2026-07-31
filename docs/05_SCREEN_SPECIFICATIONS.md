# SpaceKrafters OS Screen Specifications

## 1. Common Screen Standards

Every list screen should support:

- Search
- Filters
- Sorting
- Pagination or progressive loading
- Saved views where useful
- Export based on permission
- Bulk assignment or status action where safe
- Empty, loading and error states

Every detail screen should support:

- Record identifier
- Current status
- Assigned users
- Activity timeline
- Comments and mentions
- Attachments
- Relevant quick actions
- Audit information

## 2. Authentication

### Login

Purpose: Authenticate internal users.

Fields:

- Email or username
- Password
- Remember device

Actions:

- Login
- Forgot password

States:

- Invalid credentials
- Disabled account
- Password reset required

### Forgot Password

Fields:

- Email

Actions:

- Send reset link

## 3. Dashboard Screens

### Owner Dashboard

Cards:

- Active leads
- Active projects
- Projects delayed
- Pending approvals
- Outstanding payments
- Budget alerts
- Purchase delays
- Feedback pending

Widgets:

- Projects requiring attention
- SLA violations
- Stage aging
- Team productivity
- Budget vs actual
- Procurement pipeline
- Client ratings

Quick actions:

- Approve request
- Open delayed project
- Review employee score

### PC Dashboard

Cards:

- Leads assigned
- Calls due
- Appointments today
- Follow-ups due
- Client approvals pending
- Projects blocked

Lists:

- Lead SLA queue
- Today’s schedule
- Follow-up queue
- Projects requiring update

### SE Dashboard

- Visits today
- Measurements pending
- Daily reports pending
- Open technical issues
- Material receipts pending
- Snag items

### Designer Dashboard

- Designs assigned
- Due today
- Architect review returned
- Client revisions
- Approvals pending
- Revision count warnings

### Architect Dashboard

- Pending reviews
- Overdue reviews
- Recently approved
- Returned designs

### QS Dashboard

- Preliminary BOQs pending
- Actual BOQs pending
- Material specification requests
- Clarifications

### Purchase Dashboard

- Open purchase requirements
- RFQs pending
- Quotations to compare
- Approvals pending
- POs pending
- Deliveries delayed

### Accounts Dashboard

- 10% advances pending
- 40% advances pending
- Final payments pending
- POs to issue
- Expenses to verify
- Vendor bills pending

## 4. CRM Screens

### Lead List

Columns:

- Lead number
- Client
- Phone
- Location
- Property type
- Assigned PC
- Lead status
- SLA timer
- Next follow-up
- Last activity

Filters:

- PC
- Status
- Lead source
- Location
- SLA state
- Follow-up date
- Created date

Actions:

- Add lead
- Assign
- Schedule follow-up
- Mark lost
- Convert

### Create Lead

Fields:

- Client name
- Phone
- Email
- Location
- Full site address
- Property type
- Lead source
- Estimated budget
- Expected timeline
- Requirement notes
- Assigned PC
- Priority

Validation:

- Name and phone mandatory
- Assigned PC mandatory
- Duplicate phone warning

On save:

- Generate lead number
- Start two-hour SLA
- Notify assigned PC

### Lead Detail

Sections:

- Contact information
- Requirement summary
- SLA status
- Appointment
- Site visit
- Documents
- Follow-up timeline
- Notes

Actions:

- Log call
- Schedule appointment
- Add follow-up
- Create site visit
- Send proposal
- Convert to project
- Mark lost

### Call Log Modal

Fields:

- Date/time
- Outcome
- Notes
- Next action
- Next follow-up date

### Appointment Screen

Fields:

- Lead/client
- Date and time
- Meeting type
- Location/link
- PC
- Participants
- Confirmation state
- Notes

## 5. Site Visit Screens

### Site Visit List

Columns:

- Visit number
- Lead/project
- Date
- PC
- SE
- Address
- Status
- Checklist completion

### Site Visit Detail

Tabs:

- Summary
- PC requirements
- Measurements
- Photos
- Checklist
- Notes

Actions:

- Start visit
- Add measurement
- Upload photos
- Complete checklist
- Submit visit

### Room Measurement Form

Fields:

- Room name
- Length
- Width
- Height
- Door/window details
- Electrical points
- Plumbing points
- Existing furniture/conditions
- Sketch/file
- Notes

Validation:

- Room name mandatory
- Required dimensions mandatory

## 6. Proposal Screens

### Proposal Readiness

Shows readiness of:

- Preliminary BOQ
- Material specification
- Moodboard
- Requirement summary

Actions:

- Select versions
- Request missing input
- Generate proposal pack

### Proposal Pack Detail

Fields:

- Proposal number
- Lead/project
- Included documents
- Version
- Created by
- Sent status
- Sent date
- Channel
- Recipient

Actions:

- Generate PDF
- Preview
- Send by email
- Record WhatsApp send
- Create follow-up

## 7. Project Screens

### Project List

Columns:

- Project number
- Project name
- Client
- Location
- Current stage
- Progress
- PC
- SE
- Designer
- Next milestone
- Alert status

### Project Overview

Sections:

- Client and site summary
- Current stage
- Overall progress
- Team
- Payment status
- Budget status
- Next actions
- Alerts

### Project Timeline

Columns/timeline fields:

- Stage
- Entered date
- Exited date
- Duration
- Responsible owner
- SLA
- Delay
- Delay reason

### Project Team

- Role
- Assigned employee
- Assigned date
- Handover accepted
- Workload
- Replace/reassign action

### Handover Checklist

Checklist items:

- Client requirement available
- Measurements complete
- Site photos available
- Preliminary BOQ available
- Material specification available
- Moodboard available
- Commercial terms available
- Risks/constraints documented

Actions:

- Accept handover
- Raise missing-information query

## 8. Design Screens

### Design Queue

Columns:

- Project
- Design package
- Room/category
- Designer
- Due date
- Revision number
- Current reviewer
- Status

### Design Submission

Fields:

- Project
- Package/room
- Design type
- Version notes
- Files
- Related BOQ/spec version
- Submission comments

Actions:

- Save draft
- Submit to architect

### Architect Review

Displays:

- Design preview/download
- Related measurements
- BOQ/spec reference
- Version history
- Previous comments

Actions:

- Approve
- Approve with comments
- Return for correction

### Client Review Tracking

Fields:

- Sent date
- Sent channel
- Client response
- Comments
- Revision required
- Follow-up date

Actions:

- Record approval
- Create revision
- Send reminder

## 9. Payment Screens

### Payment Milestone List

Columns:

- Project
- Milestone
- Due amount
- Received amount
- Due date
- Status
- Last follow-up

### Record Payment

Fields:

- Project
- Milestone
- Amount
- Date
- Mode
- Reference
- Proof
- Notes

Validation:

- Amount and date mandatory
- Overpayment warning

## 10. Task and Daily Diary Screens

### My Tasks

Views:

- Today
- Upcoming
- Overdue
- Waiting for input
- Completed

Task fields:

- Project
- Task title
- Owner
- Contributors
- Due date
- Priority
- Dependencies
- Mandatory inputs

### Daily Diary Entry

Fields:

- Date
- Project
- Activity type
- Work completed
- Time spent
- Status
- Blocker
- Next action
- Attachments/photos

### Team Diary Review

Filters:

- Date
- Employee
- Role
- Project
- Missing entry

## 11. Performance Screens

### Employee Scorecard

Sections:

- Employee and role
- Period
- SLA compliance
- Task completion
- Daily diary compliance
- Quality/rework
- Manager rating
- Client rating
- Total points
- Adjustment history

Actions:

- Add manager rating
- Add justified adjustment
- Approve score

### Incentive Report

Columns:

- Employee
- Role
- Base score
- Adjustments
- Final score
- Suggested incentive
- Approved incentive
- Approval status

### Feedback Form

Fields:

- Overall experience
- Communication
- Timeliness
- Quality
- PC rating
- SE rating
- Designer rating
- Comments

## 12. Budget and Expense Screens

### Project Budget

Sections:

- Total working budget
- Category allocations
- Committed amount
- Actual amount
- Remaining amount
- Variance

Actions:

- Allocate
- Revise draft allocation
- Request extension
- Approve extension

### Expense Entry

Fields:

- Project
- Expense category
- Amount
- Date
- Paid by
- Vendor/payee
- Proof
- Description

Status:

- Draft
- Submitted
- Approved
- Rejected
- Posted to actuals

### Budget Extension

Fields:

- Project
- Current budget
- Requested additional amount
- Category
- Reason
- Impact if rejected
- Supporting documents

## 13. Procurement Screens

### Vendor List

Columns:

- Vendor code
- Name
- Category
- Contact
- Location
- Rating
- Active status

### Purchase Requirement

Fields:

- Project
- Requirement title
- BOQ reference
- Items/packages
- Quantity
- Specification
- Required-by date
- Budget category
- Requestor

### Vendor Quotation

Fields:

- Vendor
- Requirement
- Item rates
- Taxes
- Delivery period
- Payment terms
- Warranty
- Attachments

### Vendor Comparison

Rows:

- Item/package
- Vendor prices
- specification compliance
- delivery days
- payment terms
- recommendation

Actions:

- Recommend vendor
- Request clarification
- Send for approval

### Purchase Approval

Shows:

- Requirement
- Recommended vendor
- Comparison
- Budget availability
- Approval history

Actions:

- Approve
- Reject
- Return for clarification

### Purchase Order

Fields:

- PO number
- Vendor
- Project
- Approved requirement
- Items
- Amount
- Terms
- Delivery address
- Expected date
- PO file

### Material Receipt

Fields:

- PO
- Delivery date
- Quantity received
- Damaged/short quantity
- Received by
- Photos
- Delivery note
- Remarks

## 14. Snag and Closure Screens

### Snag List

Fields:

- Area/room
- Description
- Severity
- Responsible user/vendor
- Due date
- Before photo
- Status
- Closure photo
- Verified by

### Project Closure

Checklist:

- Execution complete
- Critical snags closed
- Final documents uploaded
- Payment status recorded
- Final cost updated
- Feedback task scheduled

## 15. Documents Screen

Columns:

- File name
- Project
- Category
- Version
- Current version
- Status
- Uploaded by
- Upload date

Actions:

- Upload
- Preview
- Download
- Create version
- Submit for approval
- Mark current
- Archive

## 16. Administration Screens

- User management
- Role management
- Permission configuration
- SLA configuration
- Approval rules
- Notification templates
- Master data
- Project templates
- Document categories
- Expense categories
- Budget categories
- Audit logs

## 17. Required UI States

For each transactional screen:

- Empty state with primary action
- Loading skeleton
- Validation errors near fields
- Save success confirmation
- Network failure with retry
- Permission-denied message
- Locked/approved-record state
- Unsaved-change warning