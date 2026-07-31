# SpaceKrafters OS Roles and Permissions

## 1. Permission Model

Permissions must be enforced at both interface and server levels.

Permission types:

- View
- Create
- Edit
- Submit
- Approve
- Reject
- Assign
- Export
- Delete
- View Financial Values
- View Audit History

Delete access should be rare. Business records should normally be cancelled or archived instead of deleted.

## 2. Owner

### Access

- Full company-wide visibility
- All projects and leads
- All dashboards and reports
- All budget and procurement values
- All employee performance data
- All audit logs

### Approval Rights

- Budget allocation
- Budget extension
- High-value purchase approval
- Workflow exceptions
- Revision exceptions
- Incentive approval
- Project closure exceptions

### Restrictions

- Owner actions must still be audit logged.

## 3. Project Coordinator

### Lead Access

- Create leads
- View assigned leads
- Edit lead details
- Record contact and follow-up
- Schedule appointments
- Convert qualified leads
- Mark lead lost with reason

### Project Access

- View assigned projects
- Update coordination status
- Schedule site visits
- Add client notes
- View approved documents
- Track approvals and payments
- Create and manage project tasks
- Submit daily diary
- Create snag list
- Initiate closure

### Procurement Access

- View project purchase requirements
- Review vendor comparison
- Approve project suitability of proposed vendor

### Restrictions

- Cannot approve own budget extension.
- Cannot edit approved financial records.
- Cannot issue purchase orders unless explicitly authorized.

## 4. Site Engineer

### Access

- View assigned projects and visits
- Enter measurements
- Upload site photographs
- Complete technical checklist
- Submit daily site report
- Record progress and issues
- Confirm material receipt
- Create technical clarification
- Update snag closure evidence
- Enter eligible site expenses

### Restrictions

- Cannot edit client commercial terms.
- Cannot approve project budget.
- Cannot approve own expense.
- Cannot approve designs as architect.

## 5. Designer

### Access

- View assigned project requirements
- View measurements and approved inputs
- Upload moodboards, 2D and 3D designs
- Create new document versions
- Submit design for architect review
- Record client comments
- Create revision tasks
- Follow up design approvals
- Submit daily diary

### Restrictions

- Cannot mark architect approval.
- Cannot change revision count manually.
- Cannot edit BOQ unless separately granted QS permission.
- Cannot record payments unless explicitly authorized.

## 6. Architect

### Access

- View design review queue
- View measurements, BOQ and material specifications as reference
- Approve design
- Approve with comments
- Return for correction
- Add technical comments
- View design version history

### Restrictions

- Cannot modify designer files.
- Cannot record client approval.
- Cannot alter budget or procurement records.

## 7. Quantity Surveyor

### Access

- Create preliminary BOQ
- Create actual BOQ
- Maintain material specifications
- Add quantity and rate details
- Version BOQ documents
- Submit for internal approval
- Respond to technical clarifications
- View approved drawings and measurements

### Restrictions

- Cannot select vendors unless additional procurement role is assigned.
- Cannot approve final budget.
- Cannot record client payments.

## 8. Purchase Head

### Access

- View approved project requirements and BOQ
- Create purchase requirements
- Manage vendor master data
- Record vendor quotations
- Prepare vendor comparison
- Propose vendor
- Track purchase approval
- Track vendor production and delivery
- Upload delivery and bill documents
- View procurement reports

### Restrictions

- Cannot approve own purchase recommendation where segregation is required.
- Cannot issue final PO unless permitted.
- Cannot edit project budget allocation.

## 9. Accounts Team

### Access

- View approved commercial and procurement records
- Record payment milestones
- Record receipts and payment proof
- Monitor outstanding collections
- Issue or upload purchase orders
- Verify vendor bills
- Review expenses
- Approve or reject expenses according to policy
- Export financial-operational reports

### Restrictions

- Cannot alter designs or technical approvals.
- Cannot change project scope.
- Cannot approve owner-level budget extension.

## 10. System Administrator

### Access

- Manage users
- Assign roles
- Configure master data
- Configure workflow settings
- Manage notification templates
- View technical logs
- Manage backups and integrations

### Restrictions

- Administrator access does not automatically grant authority to approve business transactions.
- Impersonation, if supported, must be audit logged.

## 11. Permission Matrix

| Module | Owner | PC | SE | Designer | Architect | QS | Purchase | Accounts |
|---|---|---|---|---|---|---|---|---|
| Leads | Full | Assigned Create/Edit | View assigned visit | Limited view after conversion | No | No | No | Limited commercial view |
| Appointments | Full | Create/Edit | View assigned | No | No | No | No | No |
| Measurements | Full | View/coordinate | Create/Edit assigned | View | View | View | View approved | No |
| BOQ | Full | View | View | View | View | Create/Edit | View approved | View approved |
| Material Specs | Full | View | View | View | View | Create/Edit | View approved | View approved |
| Moodboards/Designs | Full | View | View | Create/Edit | Review/Approve | View | View approved | No |
| Client Approval | Full | View/update follow-up | View | Record response | View | View | No | View |
| Payments | Full | View/follow-up | No | View/follow-up | No | No | No | Create/Edit |
| Daily Diary | Full | Own/Create | Own/Create | Own/Create | Optional own | Own/Create | Own/Create | Own/Create |
| Performance | Full | Own/team limited | Own | Own | Own | Own | Own/team limited | Limited |
| Budget | Full/Approve | View relevant/request extension | View category/request | Limited view | No | View cost inputs | View procurement category | Create/verify actuals |
| Expenses | Full | Create/View own project | Create | Create if permitted | No | Create if permitted | Create | Verify/Approve |
| Vendors | Full | View | View selected | No | No | View | Create/Edit | View/Edit commercial |
| Quotations | Full | Review | View | No | No | View | Create/Edit | View |
| Purchase Approval | Full | Project approval | Technical confirmation | No | No | Quantity confirmation | Submit | Financial/PO action |
| PO | Full | View | View | No | No | View | View/track | Create/Edit |
| Documents | Full | Project access | Project access | Project access | Design access | BOQ access | Procurement access | Financial access |
| Reports | Full | Assigned operational | Assigned project | Own/project | Review reports | BOQ reports | Procurement reports | Financial-operational |

## 12. Data Visibility Rules

- Users see only assigned projects unless their role grants broader department access.
- Financial values can be hidden by field-level permission.
- Employee performance details are visible to the employee, authorized manager and owner.
- Client contact information is restricted to roles that need communication access.
- Vendor commercial values are limited to procurement, accounts, owner and authorized PC.

## 13. Approval Segregation

Where feasible:

- Requestor should not be final approver.
- Expense submitter should not approve the same expense.
- Vendor recommender should not be sole final approver for high-value purchases.
- Budget extension should always require owner approval.
- Design creator cannot provide architect approval.

## 14. Audit Requirements

Log the following:

- Login and security events
- Role and permission changes
- Lead assignments
- SLA overrides
- Status transitions
- Document version changes
- Approval decisions
- Budget changes
- Expense approval
- Vendor selection
- PO issue or modification
- Payment record edits
- Incentive score overrides
- Project closure and reopening