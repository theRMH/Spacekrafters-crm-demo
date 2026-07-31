# SpaceKrafters OS Development Roadmap

## 1. Delivery Strategy

Build the system as a modular web application with a mobile-first responsive interface.

Recommended stack:

- Next.js with TypeScript
- PostgreSQL
- Supabase or a dedicated Node.js backend, depending on deployment preference
- Object storage such as AWS S3 or Cloudflare R2
- Background job worker for SLA checks, notifications and document generation
- Email provider and WhatsApp Business API adapter

The current HTML demo is a product concept. It should not be treated as production code.

## 2. Architecture Foundations

These foundations must be completed before module work:

- Company/tenant model
- Authentication
- Users, employees and roles
- Server-side permissions
- Audit logging
- File upload and object storage
- Notification framework
- Background job processing
- Master data
- Responsive application shell
- Error monitoring
- Backup strategy

## 3. Release 0: Discovery and Finalization

### Deliverables

- Approve end-to-end workflow
- Confirm role hierarchy
- Confirm approval thresholds
- Confirm SLA business-hour rules
- Confirm payment gates
- Finalize incentive scoring formula
- Finalize required reports
- Confirm WhatsApp/email provider
- Confirm hosting architecture

### Exit Criteria

- Client signs off workflow and scope.
- Open business decisions are documented.
- Development backlog is prioritized.

## 4. Release 1: Operations Core

### Modules

- Authentication and role-aware navigation
- Owner and PC dashboards
- Lead management
- Lead assignment
- Two-hour SLA
- Appointment scheduling
- Follow-up tracking
- Site visit scheduling
- Measurement entry
- Site photographs and checklist
- Project creation and handover
- Project workspace
- Document repository

### User Outcome

SpaceKrafters can track leads, appointments, site visits and the initial movement into projects.

### Acceptance Criteria

- Lead SLA warnings and breaches work.
- Site visit cannot close without mandatory inputs.
- Project handover is acknowledged.
- Project documents are stored centrally.

## 5. Release 2: Proposal and Design Workflow

### Modules

- Preliminary BOQ
- Material specification
- Moodboard
- Proposal readiness
- Proposal pack generation
- Proposal send history
- Weekly follow-up automation
- Design packages
- Designer submissions
- Architect review
- Client review tracking
- Revision management
- 10% and 40% payment milestones

### Acceptance Criteria

- Only approved versions enter the proposal pack.
- Architect decisions are audit logged.
- Revision count is automatic.
- Revision above two triggers an escalation.
- Payment milestone status is visible in project workspace.

## 6. Release 3: Work Management and Accountability

### Modules

- Tasks
- Multiple contributors
- Task dependencies
- Daily diary
- Stage aging
- Delay reasons
- Role-specific dashboards
- SLA compliance report
- Client feedback request
- Employee scorecard
- Incentive recommendation

### Acceptance Criteria

- Parallel contributors can submit separate inputs.
- One accountable owner remains responsible for the parent task.
- Diary compliance is measurable.
- Score calculations are explainable and adjustable with audit history.

## 7. Release 4: Budget and Expenses

### Modules

- Project working budget
- Budget categories
- Budget allocation
- Budget vs actual
- Expense entry
- Petty cash
- Conveyance
- Expense proof
- Expense approval
- Budget extension
- Budget threshold alerts

### Acceptance Criteria

- Approved expenses update actuals.
- Unapproved expenses do not affect actuals.
- Budget extensions require owner approval.
- Threshold alerts work by project and category.

## 8. Release 5: Procurement and Vendors

### Modules

- Vendor master
- Purchase requirements
- Purchase items and specifications
- Vendor quotations
- Comparison view
- Vendor recommendation
- Purchase approval
- Purchase order
- Vendor acknowledgement
- Material delivery
- Material receipt
- Shortage/damage reporting
- Vendor bill upload
- Vendor performance

### Acceptance Criteria

- Quotation comparison is item-level.
- Vendor selection records reason and approval.
- PO is connected to project, requirement and vendor.
- Material receipt records shortage and damage.
- Delivery performance is reportable.

## 9. Release 6: Closure, Reports and Hardening

### Modules

- Snag list
- Closure workflow
- Final payment status
- Feedback scheduling
- Complete dashboards
- Reports and exports
- Audit reports
- Notification preferences
- Performance optimization
- Security review
- Backup restoration test

### Acceptance Criteria

- Project closure checklist is enforced.
- Critical snag items block closure unless formally overridden.
- Reports reconcile to source records.
- Restore procedure is tested.

## 10. Suggested Sprint Backlog

### Sprint Group A: Foundation

- App shell
- Auth
- User/role management
- Permission middleware
- Database migrations
- Audit service
- File upload service

### Sprint Group B: CRM

- Lead list/detail
- Create lead
- Assignment
- SLA timer
- Call log
- Appointment
- Follow-up

### Sprint Group C: Site and Project

- Site visits
- Measurements
- Photos
- Checklists
- Lead conversion
- Project workspace
- Team assignment
- Handover

### Sprint Group D: Documents and Design

- Documents/versioning
- Proposal pack
- Design package
- Architect approval
- Client review
- Revision logic

### Sprint Group E: Performance

- Task engine
- Contributors/dependencies
- Daily diary
- SLA reports
- Feedback
- Scores/incentives

### Sprint Group F: Budget

- Budget master
- Budget categories
- Expenses
- Approvals
- Extensions
- Variance reports

### Sprint Group G: Procurement

- Vendors
- Purchase requirements
- Quotations
- Comparison
- Approvals
- PO
- Receipts
- Bills

### Sprint Group H: Closure and Reporting

- Snag list
- Closure
- Dashboards
- Exports
- Audit screens
- QA and hardening

## 11. Testing Strategy

### Unit Tests

- SLA calculations
- Revision limits
- Budget calculations
- Score calculations
- Permission checks

### Integration Tests

- Lead to project conversion
- Proposal generation
- Approval sequence
- Expense to budget actual
- Vendor selection to PO
- PO to receipt
- Project closure

### End-to-End Tests

Role-based scenarios for:

- Owner
- PC
- SE
- Designer
- Architect
- QS
- Purchase Head
- Accounts

### User Acceptance Testing

Use real sample projects and anonymized sample documents.

## 12. Deployment Environments

- Development
- Staging/UAT
- Production

Production releases should require:

- Database migration review
- Backup confirmation
- Automated checks
- UAT approval for major workflow changes
- Rollback plan

## 13. Hosting Recommendation

### Application

- Managed platform or VPS/container hosting

### Database

- Managed PostgreSQL preferred for reliability

### File Storage

- AWS S3 or Cloudflare R2

### Backups

- Daily database backups
- Point-in-time recovery where available
- Object storage versioning or backup policy
- Periodic restoration testing

### Monitoring

- Application errors
- Job failures
- Database health
- Storage growth
- Notification failures
- Backup failures

## 14. Security Checklist

- Enforce HTTPS
- Secure password policy
- Optional MFA
- Tenant isolation
- Server-side authorization
- Signed private-file URLs
- Input validation
- Rate limiting
- Audit logs
- Dependency scanning
- Secret management
- Backup encryption

## 15. Data Migration

Potential source data:

- Existing lead spreadsheets
- Active project list
- Users and roles
- Vendor list
- Opening project budget
- Outstanding payments
- Important current documents

Migration steps:

1. Clean source data.
2. Map fields.
3. Import into staging.
4. Validate with business owners.
5. Perform production import.
6. Retain import log.

## 16. Training and Adoption

Role-specific training:

- Owner: dashboards and approvals
- PC: leads, follow-ups and project coordination
- SE: visits, measurements and daily site reporting
- Designer/Architect: design and approvals
- QS: BOQ and specifications
- Purchase: vendors and procurement
- Accounts: payments, expenses and POs

Adoption controls:

- Simple role-specific home screens
- Required fields only where necessary
- Mobile-first daily workflows
- Missing update reminders
- Weekly adoption report

## 17. Future Product Roadmap

After the SpaceKrafters implementation stabilizes:

- Client portal
- Vendor portal
- PWA/offline site forms
- Native mobile apps
- Inventory and warehouse tracking
- Tally/accounting integration
- AI project risk summaries
- AI document classification
- Automated BOQ assistance
- Multi-company SaaS onboarding
- Subscription and billing management

## 18. Definition of Done

A backlog item is complete only when:

- Functional requirements are implemented.
- Permissions are enforced.
- Audit events are recorded where required.
- Mobile and desktop views work.
- Validation and error states exist.
- Automated tests pass.
- UAT acceptance criteria pass.
- Documentation is updated.
- Feature is deployed to the approved environment.