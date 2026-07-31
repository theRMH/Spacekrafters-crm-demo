# SpaceKrafters OS End-to-End Workflow

## 1. Lead Intake

1. A user creates a lead manually.
2. The system assigns a unique lead number.
3. The lead is assigned to a Project Coordinator.
4. A two-hour response timer starts.
5. The PC contacts the lead and records the outcome.

### Decision: Was the lead contacted within two hours?

- Yes: Continue to qualification.
- No: Notify the PC and owner. Require a delay reason before further status changes.

## 2. Lead Qualification and Appointment

1. PC records the client requirement, location, property type, approximate budget and expected timeline.
2. PC proposes an appointment.
3. Appointment details are stored in the calendar.
4. PC and client confirmation status is recorded.

### Decision: Was an appointment fixed within 24 hours?

- Yes: Schedule site visit.
- No: Require reason, next action and follow-up date.

### Decision: Is the lead qualified?

- Qualified: Continue.
- Not ready: Move to nurture and create weekly follow-up.
- Lost: Capture loss reason and close lead.

## 3. Site Visit Planning

1. PC schedules the visit.
2. Site Engineer is assigned.
3. Both users receive the appointment details.
4. The system provides a site-visit checklist.

Required inputs:

- Client/site contact
- Address and map reference
- Visit date and time
- PC
- Site Engineer
- Property details
- Existing plans, if available

## 4. Site Visit and Measurement

The PC and SE perform the visit in parallel.

### Project Coordinator Activities

- Confirm client requirements
- Record room usage and preferences
- Capture budget and timeline discussions
- Record special constraints

### Site Engineer Activities

- Enter room-wise dimensions
- Record ceiling height
- Record electrical and plumbing points
- Capture existing-site photographs
- Upload floor plan or sketches
- Complete measurement checklist

### Completion Gateway

The site visit may be marked complete only when all mandatory PC and SE inputs are submitted.

## 5. Initial Proposal Preparation

Parallel activities begin after measurement completion:

- QS prepares preliminary BOQ.
- QS or authorized user prepares material specification.
- Designer prepares moodboard.
- PC reviews client requirement summary.

### Proposal Readiness Gateway

All required documents must be available and marked ready.

1. PC selects approved document versions.
2. System combines or registers them as one proposal pack.
3. Proposal is sent by email or WhatsApp.
4. Sent date, channel and recipient are recorded.
5. A follow-up task is created.

## 6. Proposal Follow-Up

1. PC follows up at least once every seven days.
2. Each interaction is recorded.
3. Next follow-up date is mandatory until the lead is closed or converted.

### Client Decision

- Rejected: Capture reason and close or nurture.
- Needs clarification: Create clarification task and update documents if required.
- Agreed to proceed: Convert lead to project.

## 7. Project Creation and Handover

1. System creates the project from the approved lead.
2. Owner or authorized person assigns:
   - PC
   - Site Engineer
   - Designer
   - Architect
   - QS
3. Project handover checklist is generated.
4. Designer and SE independently acknowledge receipt.
5. Missing information creates a handover query.

### Handover Completion Gateway

The project moves to design only after mandatory assignees accept the handover.

## 8. Concept Design and Technical Inputs

Parallel work:

- Designer prepares concept, moodboard and required drawings.
- QS prepares actual BOQ.
- QS prepares or updates material specification.
- SE provides technical site clarifications.

Each submission records:

- Version
- Submitted by
- Submission date
- Comments
- Related project stage

## 9. Architect Review

1. Designer submits design package for architect review.
2. Architect chooses:
   - Approve
   - Approve with comments
   - Return for correction
3. Comments and decision date are recorded.

### Decision: Architect Approved?

- No: Return to designer and increment internal correction count.
- Yes: Release package for client review.

## 10. Client Design Review

1. Approved design is sent to client.
2. Designer owns client follow-up during design stage.
3. Client response is recorded.

### Client Decision

- Approved: Continue to advance/payment gateway.
- Revision requested: Create revision task.
- No response: Follow up and escalate after configured delay.

### Revision Rule

- Revision 1 and 2 are standard.
- Revision 3 or above requires a mandatory reason.
- Owner is notified when revision count exceeds two.

### Delay Rule

If a design task remains overdue by more than two days, notify the assignee, PC and owner based on escalation settings.

## 11. Payment Milestone: 10% Advance

1. Designer or PC requests 10% advance.
2. Accounts records amount, date, mode and proof.
3. Status becomes received, partial or pending.
4. The project may proceed according to configured payment gate rules.

## 12. Detailed Design

Designer and Site Engineer work in parallel:

- 2D drawings
- 3D designs
- Technical dimensions
- Electrical/plumbing coordination
- Hardware and material counts

Architect approval is required before final client submission.

## 13. Final Design Approval

1. Architect approves detailed package.
2. Package is sent to client.
3. Client approval is recorded per room/package.
4. Approved design versions are locked as current approved versions.

## 14. Payment Milestone: 40% Advance

1. Accounts raises or records the milestone.
2. PC/designer follows up.
3. Payment proof and status are recorded.
4. Procurement/execution gate follows configured rules.

## 15. Project Budget Allocation

1. Owner enters the project working budget after excluding target profit.
2. Budget is split into categories such as:
   - Factory/modular work
   - Hardware
   - Civil work
   - Electrical
   - Plumbing
   - Painting
   - Labour
   - Transport
   - Site expenses
3. Team access is restricted by role.

### Budget Extension Gateway

If planned or actual cost exceeds available category/project budget:

1. User submits extension request.
2. Reason and amount are mandatory.
3. Owner approves, rejects or requests clarification.

## 16. Procurement Planning

PC and Purchase Head coordinate:

1. Create purchase requirements from BOQ and approved designs.
2. Split packages where different vendors are required.
3. Enter hardware counts and required dates.
4. Send or record RFQs.

## 17. Vendor Quotations and Comparison

1. Purchase Head records quotations from multiple factories/vendors.
2. Quotations are compared by:
   - Price
   - Specification compliance
   - Delivery period
   - Payment terms
   - Warranty
   - Past performance
3. Purchase Head proposes a vendor.
4. PC reviews project suitability.
5. Owner approval is invoked when required by value or policy.

## 18. Purchase Order

1. Approved purchase request reaches Accounts.
2. Accounts generates or uploads PO.
3. PO is sent to vendor.
4. Vendor acknowledgement and promised delivery date are recorded.

## 19. Material Follow-Up and Receipt

Purchase Head and responsible follow-up role monitor:

- Production progress
- Dispatch date
- Expected delivery
- Delays
- Site receipt

At receipt:

1. SE or authorized user confirms quantity and condition.
2. Delivery proof/photos are uploaded.
3. Shortage or damage creates an issue.
4. Vendor bill is uploaded and linked to PO/project.

## 20. Project Execution

### Daily Site Engineer Entry

- Work completed
- Progress percentage
- Labour details if required
- Site photos
- Issues
- Material requirements
- Planned work for next day

### Daily Project Coordinator Entry

- Client follow-ups
- Vendor/team coordination
- Site visits
- Decisions and blockers
- Project-wise time/activity

### Designer Entry

- Design support
- Clarifications
- Site revisions
- Client discussions

All entries are associated with a project and employee.

## 21. Expenses

Users submit:

- Site expenses
- Petty cash
- Conveyance
- Miscellaneous authorized expenses

Required information:

- Project
- Category
- Amount
- Date
- Proof
- Description
- Approver

Approved expenses update budget actuals.

## 22. Snag List

1. PC creates snag inspection.
2. Snag items are assigned to responsible users/vendors.
3. Each item records severity, due date, evidence and closure proof.
4. PC verifies closure.

### Closure Gateway

All critical snag items must be closed or formally waived before project completion.

## 23. Final Payment

1. Accounts records final amount and outstanding.
2. PC follows up with client.
3. Receipt/proof is recorded.
4. Owner can view closure exceptions if payment remains pending.

## 24. Project Completion

Project completion requires:

- Approved final design records
- Execution status complete
- Snag closure
- Required documents uploaded
- Final cost summary
- Payment status recorded
- Handover/completion date

## 25. Client Feedback

1. Seven days after completion, system creates feedback task.
2. Feedback link is sent by configured channel.
3. Client rates:
   - PC
   - Site Engineer
   - Designer
   - Communication
   - Timeliness
   - Quality
   - Overall experience
4. Feedback updates employee and project scorecards.

## 26. Performance and Incentive Processing

At the end of each period, system calculates or presents:

- SLA compliance
- On-time task completion
- Rework/revision impact
- Daily diary compliance
- Manager rating
- Client rating
- Quality score
- Project contribution

The initial system provides a recommended score and incentive report. Final incentive approval remains with management.