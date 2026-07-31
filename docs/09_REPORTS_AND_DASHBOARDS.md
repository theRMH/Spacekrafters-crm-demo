# SpaceKrafters OS Reports and Dashboards

## 1. Reporting Principles

- Reports must respect role and record-level permissions.
- Every report should support a date range and relevant operational filters.
- Financial values must be hidden from roles without financial permission.
- Reports should provide drill-down links to the underlying record.
- Export to spreadsheet or PDF should be permission-controlled.
- Dashboard values should be calculated from source transactions, not manually entered summaries.

## 2. Owner Dashboard

### Summary Cards

- Leads created this month
- Leads awaiting first call
- Active projects
- Projects delayed
- Pending approvals
- Outstanding payments
- Total working budget
- Budget consumed
- Open purchase requirements
- Deliveries delayed
- Average client rating
- Team SLA compliance

### Attention Queue

Displays:

- Lead SLA breaches
- Projects stuck in a stage
- Design approval delays
- Revision count above two
- Payment overdue
- Budget threshold breached
- Purchase approval overdue
- Vendor delivery overdue
- Negative client feedback

### Charts

- Lead funnel
- Lead source conversion
- Projects by stage
- Project stage aging
- Budget vs actual by project
- Team performance trend
- Client rating trend
- Procurement on-time delivery

## 3. Project Coordinator Dashboard

- New leads assigned
- First calls due
- Appointments today
- Follow-ups due
- Active projects
- Client responses pending
- Payment follow-ups pending
- Projects without daily update
- Snag items pending

## 4. Site Engineer Dashboard

- Visits today
- Measurements due
- Site diaries missing
- Assigned projects
- Open site issues
- Material receipts to confirm
- Snag tasks pending
- Site progress trend

## 5. Designer Dashboard

- Designs assigned
- Designs due today/week
- Architect corrections
- Client review pending
- Revision counts
- Client follow-ups due
- Approval turnaround
- On-time submission score

## 6. Architect Dashboard

- Reviews pending
- Reviews overdue
- Average review time
- Approved with comments
- Returned designs
- Recently approved packages

## 7. QS Dashboard

- Preliminary BOQs pending
- Actual BOQs pending
- Material specifications pending
- Clarifications waiting
- BOQ revision count
- Average turnaround time

## 8. Purchase Dashboard

- Purchase requirements open
- RFQs pending
- Quotations received
- Comparisons pending
- Vendor approvals pending
- POs pending issue
- Deliveries due
- Deliveries delayed
- Bills missing
- Vendor performance trend

## 9. Accounts Dashboard

- 10% advances pending
- 40% advances pending
- Final payments pending
- Outstanding by aging bucket
- Expenses pending verification
- POs to issue
- Vendor bills pending verification
- Budget extension impact

## 10. CRM Reports

### Lead Register

Columns:

- Lead number
- Created date
- Client
- Phone
- Location
- Source
- Assigned PC
- Status
- First response time
- Appointment status
- Last follow-up
- Next follow-up
- Conversion date
- Lost reason

Filters:

- Date range
- PC
- Source
- Status
- Location
- Property type
- SLA state

### Lead Response SLA

Metrics:

- Total assigned leads
- Contacted within two hours
- Breached leads
- Average response time
- Breaches by PC
- Delay reasons

### Appointment Report

- Leads with appointments
- Time to appointment
- Appointment completion
- Rescheduled appointments
- No-show/cancellation reason

### Lead Conversion Report

- Conversion by source
- Conversion by PC
- Conversion by location
- Average conversion days
- Lost reasons

### Follow-Up Compliance

- Follow-ups due
- Completed on time
- Overdue
- Missed
- Compliance percentage by PC

## 11. Project Reports

### Project Register

- Project number
- Client
- Location
- Contract value
- Current stage
- Progress
- Start date
- Target completion
- Team
- Payment status
- Budget status
- Alert state

### Project Stage Aging

- Project
- Stage
- Entered date
- Days in stage
- SLA target
- Responsible user
- Delay reason

### Project Timeline Performance

- Planned duration
- Actual duration
- Delay days
- Delay category
- Department responsible

### Project Workload

- Employee
- Active projects
- Open tasks
- Due this week
- Overdue
- Estimated workload

### Project Closure Report

- Completion date
- Snag closure status
- Payment status
- Feedback status
- Final budget variance

## 12. Design Reports

### Design Queue

- Project/package
- Designer
- Due date
- Status
- Current reviewer
- Days pending

### Revision Report

- Project
- Package
- Revision count
- Revision reasons
- Internal/client revision
- Additional revision exception

### Approval Turnaround

- Architect review duration
- Client review duration
- Approvals overdue
- Approval outcome

## 13. Payment Reports

### Outstanding Payments

- Project
- Milestone
- Due amount
- Received amount
- Outstanding
- Due date
- Days overdue
- Follow-up owner

### Collection Summary

- Amount due
- Amount collected
- Collection percentage
- Collections by month
- Collections by project

## 14. Daily Diary and Productivity Reports

### Diary Compliance

- Employee
- Required working days
- Entries submitted
- Missing days
- Compliance percentage

### Activity Summary

- Employee
- Project
- Activity type
- Total time
- Completed activities
- Blocked activities

### Task Completion

- Assigned
- Completed on time
- Completed late
- Overdue
- Waiting for input
- Rework count

## 15. Performance and Incentive Reports

### Employee Scorecard

- SLA score
- Task score
- Diary score
- Quality score
- Manager rating
- Client rating
- Adjustments
- Final score

### Incentive Recommendation

- Employee
- Period
- Score
- Suggested incentive
- Approved incentive
- Approval status

### Performance Trend

- Monthly score trend
- SLA trend
- Quality/rework trend
- Client rating trend

## 16. Budget Reports

### Budget vs Actual

- Project
- Working budget
- Allocated by category
- Committed
- Actual
- Remaining
- Variance percentage

### Budget Threshold Report

- Projects above 70%
- Projects above 85%
- Projects above 95%
- Projects over budget

### Budget Extension Report

- Project
- Category
- Requested amount
- Reason
- Status
- Approved amount
- Decision time

### Operational Profitability View

- Contract/project value
- Working budget
- Committed cost
- Actual cost
- Estimated remaining cost
- Projected operational margin

This is an operational view and not a statutory profit-and-loss report.

## 17. Expense Reports

### Expense Register

- Expense number
- Project
- Category
- Type
- Date
- Amount
- Submitter
- Approver
- Status
- Proof available

### Petty Cash Report

- Employee/project
- Opening/authorized amount where used
- Expenses
- Balance
- Pending proof

### Conveyance Report

- Employee
- Date
- Project
- From/to or purpose
- Amount
- Approval status

## 18. Procurement Reports

### Purchase Requirement Register

- Requirement number
- Project
- Package
- Required date
- Requestor
- Status
- Budget category

### Vendor Quotation Comparison Report

- Requirement
- Vendors
- Quote totals
- Delivery period
- Specification compliance
- Selected vendor
- Selection reason

### Purchase Order Register

- PO number
- Project
- Vendor
- Date
- Amount
- Expected delivery
- Status

### Delivery Performance

- Vendor
- Total deliveries
- On-time deliveries
- Delayed deliveries
- Short/damaged receipts
- On-time-in-full percentage

### Vendor Performance

- Price competitiveness
- Quality rating
- Delivery rating
- Issue count
- Overall score

### Procurement Cycle Time

- Requirement creation to RFQ
- RFQ to quotation completion
- Comparison to approval
- Approval to PO
- PO to receipt

## 19. Feedback Reports

### Client Feedback Summary

- Project
- Overall rating
- Communication
- Timeliness
- Quality
- PC rating
- SE rating
- Designer rating
- Comments

### Low Rating Alert Report

- Rating below configured threshold
- Project
- Employee/department
- Comment
- Corrective action status

## 20. Audit Reports

- User activity
- Approval decisions
- Budget edits
- Expense changes
- Vendor selection changes
- Payment record changes
- Permission changes
- Project status overrides

## 21. Export Standards

Every export should include:

- Report name
- Company
- Generated by
- Generated date/time
- Applied filters
- Data rows

Sensitive exports should be audit logged.

## 22. Dashboard Refresh

- Operational counts may refresh on page load and after transactions.
- Heavy charts may use cached aggregates.
- Owner dashboard should display the last refreshed time.
- Background aggregation may be used for performance and financial summaries.