# SpaceKrafters OS Information Architecture

## 1. Navigation Principles

- Navigation must be role-aware.
- Users should see only modules relevant to their work.
- The project workspace is the primary source of truth.
- Mobile navigation should prioritize Home, CRM, Projects, My Work and More.
- Desktop navigation should use a left sidebar.
- All sensitive actions must be controlled by permission, not only hidden in the UI.

## 2. Desktop Left Sidebar

### Home

- Dashboard
- My Alerts
- My Tasks
- Calendar

### CRM

- Leads
- Appointments
- Follow-Ups
- Nurture Leads
- Lost Leads
- Converted Leads

### Projects

- All Projects
- Active Projects
- Projects Requiring Attention
- Completed Projects
- Archived Projects

### Site Operations

- Site Visits
- Measurement Records
- Site Photos
- Site Reports
- Snag Lists

### Proposal Center

- Preliminary BOQs
- Material Specifications
- Moodboards
- Proposal Packs
- Sent Proposals

### Design Center

- My Design Queue
- Design Submissions
- Architect Review
- Client Review
- Revision Requests
- Approved Designs

### Payments

- Payment Milestones
- Pending Collections
- Payment Records
- Outstanding Summary

### Work Management

- My Tasks
- Team Tasks
- Daily Diary
- Workload
- Delays and Blockers

### Performance

- Employee Scorecards
- SLA Compliance
- Productivity
- Client Feedback
- Incentive Reports

### Budget and Expenses

- Project Budgets
- Budget Categories
- Budget vs Actual
- Site Expenses
- Petty Cash
- Conveyance
- Budget Extensions
- Expense Approvals

### Procurement

- Purchase Requirements
- RFQs
- Vendor Quotations
- Vendor Comparison
- Purchase Approvals
- Purchase Orders
- Material Deliveries
- Vendor Bills
- Vendors

### Documents

- All Documents
- Project Documents
- BOQ Files
- Design Files
- Site Photos
- Procurement Files
- Bills and Invoices

### Reports

- CRM Reports
- Project Reports
- Stage Aging
- Performance Reports
- Budget Reports
- Procurement Reports
- Feedback Reports
- Audit Reports

### Administration

- Users
- Roles
- Permissions
- SLA Rules
- Approval Rules
- Notification Templates
- Project Templates
- Document Types
- Expense Categories
- Budget Categories
- Vendor Categories
- Company Settings
- Audit Logs

## 3. Mobile Bottom Navigation

### Home

Role-specific dashboard, alerts and quick actions.

### CRM

Visible to Owner, PC and authorized management users.

### Projects

Project list and project workspace.

### My Work

Tasks, daily diary, approvals and assigned site visits.

### More

Performance, budget, procurement, documents, reports and settings based on role.

## 4. Role-Specific Home Pages

### Owner Home

- Projects requiring attention
- SLA violations
- Pending approvals
- Budget alerts
- Outstanding collections
- Team performance
- Procurement delays

### Project Coordinator Home

- New leads
- SLA timers
- Today’s follow-ups
- Appointments
- Site visits
- Client approvals pending
- Project blockers
- Daily diary status

### Site Engineer Home

- Today’s sites
- Measurements pending
- Site update required
- Material receipt confirmations
- Open technical issues
- Snag items

### Designer Home

- Assigned designs
- Design due dates
- Architect comments
- Client revision requests
- Client follow-ups
- Approved packages

### Architect Home

- Review queue
- Overdue reviews
- Recently approved packages
- Returned designs

### Quantity Surveyor Home

- Preliminary BOQs
- Actual BOQs
- Material specifications
- Clarification requests
- Pending approvals

### Purchase Head Home

- Open purchase requirements
- Quotations pending
- Comparison pending
- Vendor approvals
- Delivery delays
- Bills pending upload

### Accounts Home

- Payment milestones
- Collections pending
- POs to issue
- Bills to verify
- Expense approvals
- Payment proofs

## 5. Project Workspace Architecture

Every project contains the following tabs:

### Overview

- Project summary
- Current stage
- Progress
- client and site details
- assigned team
- next milestone
- alerts

### Timeline

- Stage history
- handoffs
- duration per stage
- responsible user
- delay reasons

### Team

- Assigned users
- role
- assignment date
- handover acceptance
- workload

### Requirements

- Client requirement summary
- room scope
- preferences
- constraints
- agreed exclusions

### Site and Measurements

- Visits
- room-wise measurements
- sketches
- photographs
- checklists

### Proposal

- Preliminary BOQ
- material specification
- moodboard
- proposal pack
- sent history

### Designs

- Concept designs
- 2D drawings
- 3D designs
- room/package classification
- versions

### Approvals

- Architect approvals
- client approvals
- approval comments
- decision dates

### Payments

- 10% advance
- 40% advance
- final payment
- proof and status

### Tasks

- Project tasks
- dependencies
- contributors
- owner
- due dates
- blockers

### Daily Diary

- PC entries
- SE entries
- Designer entries
- filters by date and user

### Budget

- allocated budget
- category budget
- actual expenses
- commitments
- variance

### Procurement

- purchase requirements
- quotations
- vendor selection
- PO
- delivery
- bills

### Documents

- all project files
- categories
- versions
- approval state

### Snag List

- snag items
- ownership
- severity
- target date
- closure evidence

### Feedback

- feedback status
- team ratings
- comments

### Activity History

- status changes
- edits
- uploads
- approvals
- notifications

## 6. Global Components

### Global Search

Searchable items:

- Lead number
- Client name
- Phone
- Project number
- Project name
- Vendor
- PO number
- Document name

### Global Filters

- Date range
- Project status
- Project stage
- Owner/assignee
- Department
- Client
- Location
- Alert state

### Notification Center

- New assignments
- SLA warnings
- Overdue tasks
- approval requests
- comments and mentions
- budget alerts
- delivery delays

### Quick Create

- Lead
- Task
- Site visit
- Daily diary
- Expense
- Purchase request
- Document upload

## 7. Status Taxonomy

### Lead Status

- New
- Assigned
- Contact Attempted
- Contacted
- Appointment Pending
- Appointment Scheduled
- Site Visit Completed
- Proposal Preparation
- Proposal Sent
- Follow-Up
- Qualified
- Nurture
- Converted
- Lost

### Project Stage

- Handover Pending
- Design Assigned
- Concept Design
- Architect Review
- Client Review
- 10% Advance Pending
- Detailed Design
- Final Architect Review
- Final Client Approval
- 40% Advance Pending
- Procurement
- Execution
- Snagging
- Final Payment Pending
- Completed
- On Hold
- Cancelled

### Task Status

- Not Started
- In Progress
- Waiting for Input
- Submitted
- Under Review
- Changes Required
- Approved
- Completed
- Blocked
- Cancelled

### Approval Status

- Draft
- Submitted
- Pending
- Approved
- Approved with Comments
- Rejected
- Withdrawn

### Procurement Status

- Requirement Draft
- RFQ Pending
- Quotations Received
- Comparison Pending
- Approval Pending
- Approved
- PO Issued
- Vendor Confirmed
- In Production
- Dispatched
- Partially Received
- Received
- Closed
- Cancelled