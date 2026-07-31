# SpaceKrafters OS Product Requirements Document

## 1. Product Summary

SpaceKrafters OS is a centralized operations platform for managing the complete lifecycle of an interior design and execution project.

The platform connects lead management, site measurement, proposal preparation, design approvals, payment milestones, daily work reporting, team performance, project budgets, vendor quotations, purchase approvals and project closure.

The first implementation is designed specifically for SpaceKrafters. Multi-company SaaS capabilities may be introduced later.

## 2. Product Objectives

The system must help SpaceKrafters achieve the following:

- Ensure every lead is contacted and followed up on time.
- Standardize the movement of work between departments.
- Store all project documents in one project workspace.
- Record when work reaches and leaves each employee or department.
- Identify delays, missed SLAs and blocked activities.
- Track design revisions and approval history.
- Monitor payment milestones and outstanding collections.
- Measure employee productivity and client satisfaction.
- Control project budgets and expense approvals.
- Standardize vendor comparison, purchase approvals and material receipt.
- Provide the owner with a single management dashboard.

## 3. User Roles

- Owner
- Project Coordinator (PC)
- Site Engineer (SE)
- Designer
- Architect
- Quantity Surveyor (QS)
- Purchase Head
- Accounts Team
- System Administrator

## 4. Product Phases

### Phase 1: Interior Operations Management

Includes:

- Manual lead entry
- Lead assignment
- Initial contact SLA
- Appointment scheduling
- Follow-up management
- Site visit scheduling
- Site measurement records
- Site photographs and notes
- BOQ, material specification and moodboard uploads
- Proposal pack generation
- Design assignment and handover
- Architect approval
- Client approval tracking
- Revision tracking
- 10% advance tracking
- 40% advance tracking
- Project milestone tracking
- Central document repository

### Phase 2: Performance and Accountability

Includes:

- Project-wise daily diary
- Employee task ownership
- Stage aging
- Time spent by employee and department
- SLA compliance
- Delay reason capture
- Escalation rules
- Client feedback forms
- Employee scorecards
- Performance points
- Incentive recommendation reports

### Phase 3: Financial Control and Budget Management

Includes:

- Owner-defined project working budget
- Budget categories
- Budget versus actual
- Site expenses
- Petty cash
- Conveyance claims
- Expense proof uploads
- Approval workflows
- Budget extension requests
- Project cost summary
- Operational profitability view

This phase is not intended to replace statutory accounting software.

### Phase 4: Procurement and Vendor Management

Includes:

- Vendor master
- Vendor quotation entry and upload
- Item-level quotation comparison
- Purchase requests
- Purchase planning
- Vendor approval
- Purchase order generation or upload
- Material delivery tracking
- Purchase receipt confirmation
- Vendor bill upload
- Vendor performance reporting

## 5. Core Business Rules

### Lead Rules

- A manually entered lead must be assigned to a PC.
- The assigned PC must make the first call within two hours.
- If the two-hour SLA is missed, the owner must be notified.
- The PC must provide a reason for any missed SLA.
- An appointment should be fixed within 24 hours.
- If not fixed, the PC must update the reason and next action.
- Until converted or closed, every active lead requires a weekly follow-up.

### Site Visit Rules

- A site visit must include a PC and Site Engineer.
- Measurements, photographs, notes and checklist completion are mandatory before the visit is closed.
- Measurement completion must be acknowledged by the assigned team.

### Proposal Rules

- BOQ, material specification and moodboard must be stored against the lead or project.
- Only approved document versions may be included in the client proposal.
- The system must generate or register a combined proposal pack.
- Sent date, channel and follow-up date must be recorded.

### Design Rules

- Designer and Site Engineer must acknowledge project handover using a checklist.
- QS must submit the actual BOQ and material specification.
- Designer must submit the relevant moodboard, 2D drawings and 3D designs.
- Architect approval is required before client submission.
- Client approval must be tracked for each design package.
- A maximum of two standard client revisions are allowed.
- Revisions above two require a mandatory reason and owner notification.
- A design task delayed by more than two days must be escalated.

### Payment Rules

- Payment milestones must be configurable by project.
- Initial default milestones are 10% advance, 40% advance and final payment.
- The system records payment status and proof, but does not perform bank reconciliation in the initial version.

### Budget Rules

- The owner allocates a working budget after excluding the intended profit.
- Teams may view only the budget information required for their roles.
- Budget extension requests require owner approval.
- Expenses without project, category and proof cannot be submitted unless an authorized exception is recorded.

### Procurement Rules

- Multiple vendor quotations may be linked to one purchase requirement.
- Vendor selection must record price, delivery period, specification compliance and approval.
- Accounts issues or records the PO after required approvals.
- Material receipt and vendor bills must be linked to the project and PO.

### Closure Rules

- Snag items must be closed before final project closure.
- Final payment status must be visible during closure.
- Client feedback must be sent within seven days after site completion.

## 6. Project Workspace

Each project must have one consolidated workspace containing:

- Overview
- Team
- Timeline and stage history
- Measurements
- Site photographs
- BOQ
- Material specifications
- Moodboards
- 2D drawings
- 3D designs
- Approvals
- Payment milestones
- Tasks
- Daily diaries
- Budget
- Expenses
- Procurement
- Documents
- Snag list
- Feedback
- Audit history

## 7. Functional Requirements

### Common Requirements

- Role-based access control
- Mobile responsive interface
- Global search
- Project and date filters
- File upload and preview
- Activity history
- Comments and mentions
- Status transitions
- Approval actions
- Notifications
- Export to PDF or spreadsheet where applicable
- Audit logs for sensitive changes

### Document Requirements

- Project-wise folders or categories
- Document type
- Version number
- Uploaded by
- Upload date
- Approval status
- Current version indicator
- Access restrictions
- Download history for sensitive files where feasible

### Task Requirements

- One task may have several participants working simultaneously.
- A task must have one accountable owner even when contributors are multiple.
- Dependencies may be finish-to-start or parallel.
- Each contributor may submit their part separately.
- The parent task is completed only when all mandatory inputs are submitted and accepted.

## 8. Success Metrics

- Percentage of leads contacted within two hours
- Percentage of appointments updated within 24 hours
- Weekly follow-up compliance
- Average days spent in each project stage
- Number of delayed tasks by role
- Design revision rate
- Client approval turnaround time
- Daily diary compliance
- Project budget variance
- Procurement delivery compliance
- Client satisfaction score
- Employee performance score

## 9. Non-Functional Requirements

- Secure authentication
- Role-based permissions enforced at server level
- Audit trail for approvals, budgets, expenses and procurement
- Responsive mobile and desktop experience
- Reliable file storage separate from application server where possible
- Daily database backup
- File backup and retention policy
- Encryption in transit
- Reasonable page response under normal business usage
- Support for at least 50 active internal users without redesign
- Architecture capable of later supporting multiple companies

## 10. Initial Exclusions

- Full accounting ledger
- GST and TDS filing
- Payroll
- Attendance hardware integration
- Bank feeds
- Stock valuation
- Client portal
- Vendor portal
- Native Android and iOS apps
- Automatic CAD file interpretation

## 11. Acceptance Standard

A feature is accepted when:

- The defined role can access the correct screen.
- Required fields and validations work.
- Status changes follow the approved workflow.
- Notifications and escalations are triggered correctly.
- Audit history is recorded.
- Mobile and desktop layouts are usable.
- The relevant report reflects the transaction correctly.