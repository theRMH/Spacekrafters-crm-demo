# SpaceKrafters OS API Specification

## 1. API Style

Recommended approach:

- REST API for transactional operations
- JSON request and response bodies
- Versioned base path such as `/api/v1`
- Server-side authorization for every request
- Signed upload URLs for large files
- Background jobs for notifications, PDF generation and scheduled SLA checks

GraphQL may be considered later for complex dashboards, but it is not required for the initial implementation.

## 2. Common Standards

### Authentication

- Session cookie or short-lived access token
- Refresh or reauthentication flow
- MFA-ready architecture

### Common Response Shape

```json
{
  "data": {},
  "meta": {},
  "error": null
}
```

### Error Shape

```json
{
  "data": null,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Required fields are missing",
    "fields": {
      "phone": "Phone number is required"
    }
  }
}
```

### Query Standards

- `page`
- `page_size`
- `sort`
- `order`
- `search`
- module-specific filters

## 3. Authentication and Users

- `POST /auth/login`
- `POST /auth/logout`
- `POST /auth/forgot-password`
- `POST /auth/reset-password`
- `GET /me`
- `GET /users`
- `POST /users`
- `GET /users/{id}`
- `PATCH /users/{id}`
- `POST /users/{id}/roles`
- `DELETE /users/{id}/roles/{roleId}`

## 4. CRM APIs

### Leads

- `GET /leads`
- `POST /leads`
- `GET /leads/{id}`
- `PATCH /leads/{id}`
- `POST /leads/{id}/assign`
- `POST /leads/{id}/contact-attempts`
- `POST /leads/{id}/followups`
- `POST /leads/{id}/mark-lost`
- `POST /leads/{id}/convert`

### Appointments

- `GET /appointments`
- `POST /appointments`
- `GET /appointments/{id}`
- `PATCH /appointments/{id}`
- `POST /appointments/{id}/confirm`
- `POST /appointments/{id}/cancel`

### Follow-Ups

- `GET /followups`
- `POST /followups`
- `PATCH /followups/{id}`
- `POST /followups/{id}/complete`

## 5. Site Visit APIs

- `GET /site-visits`
- `POST /site-visits`
- `GET /site-visits/{id}`
- `POST /site-visits/{id}/start`
- `POST /site-visits/{id}/complete`
- `POST /site-visits/{id}/measurements`
- `PATCH /measurements/{id}`
- `POST /site-visits/{id}/checklist-items/{itemId}/complete`
- `POST /site-visits/{id}/photos`

Completion endpoint must validate all mandatory checklist items and required measurements.

## 6. Proposal APIs

- `GET /proposal-packs`
- `POST /proposal-packs`
- `GET /proposal-packs/{id}`
- `POST /proposal-packs/{id}/items`
- `POST /proposal-packs/{id}/generate`
- `POST /proposal-packs/{id}/send`
- `GET /proposal-packs/{id}/send-history`

PDF generation should run as a background job and expose status:

- `GET /jobs/{jobId}`

## 7. Project APIs

- `GET /projects`
- `POST /projects`
- `GET /projects/{id}`
- `PATCH /projects/{id}`
- `POST /projects/{id}/assignments`
- `PATCH /projects/{id}/assignments/{assignmentId}`
- `GET /projects/{id}/timeline`
- `POST /projects/{id}/transition`
- `POST /projects/{id}/hold`
- `POST /projects/{id}/resume`
- `POST /projects/{id}/close`
- `POST /projects/{id}/reopen`

`transition` must validate workflow rules, mandatory documents, approvals and payment gates.

## 8. Handover APIs

- `GET /projects/{id}/handover`
- `POST /projects/{id}/handover/accept`
- `POST /projects/{id}/handover/query`
- `PATCH /projects/{id}/handover/items/{itemId}`

## 9. Document APIs

- `GET /documents`
- `POST /documents`
- `GET /documents/{id}`
- `POST /documents/{id}/versions`
- `GET /documents/{id}/versions`
- `POST /documents/{id}/submit`
- `POST /documents/{id}/mark-current`
- `POST /documents/{id}/archive`
- `POST /uploads/presign`
- `POST /uploads/complete`

The upload flow should be:

1. Request signed upload URL.
2. Upload directly to object storage.
3. Confirm upload and create document version.

## 10. Design and Approval APIs

### Design Packages

- `GET /design-packages`
- `POST /projects/{projectId}/design-packages`
- `GET /design-packages/{id}`
- `PATCH /design-packages/{id}`
- `POST /design-packages/{id}/submissions`
- `POST /design-packages/{id}/send-to-client`
- `POST /design-packages/{id}/record-client-response`
- `POST /design-packages/{id}/create-revision`

### Approvals

- `GET /approvals`
- `POST /approvals`
- `GET /approvals/{id}`
- `POST /approvals/{id}/approve`
- `POST /approvals/{id}/approve-with-comments`
- `POST /approvals/{id}/reject`
- `POST /approvals/{id}/withdraw`

Approval endpoints must record approver, decision time and comments.

## 11. Payment APIs

- `GET /projects/{id}/payment-milestones`
- `POST /projects/{id}/payment-milestones`
- `PATCH /payment-milestones/{id}`
- `POST /payment-milestones/{id}/payments`
- `GET /payments`
- `GET /payments/outstanding-summary`

## 12. Task and Diary APIs

### Tasks

- `GET /tasks`
- `POST /tasks`
- `GET /tasks/{id}`
- `PATCH /tasks/{id}`
- `POST /tasks/{id}/contributors`
- `POST /tasks/{id}/dependencies`
- `POST /tasks/{id}/submit`
- `POST /tasks/{id}/accept-contribution`
- `POST /tasks/{id}/complete`
- `POST /tasks/{id}/block`

### Daily Diary

- `GET /daily-diaries`
- `POST /daily-diaries`
- `GET /daily-diaries/{id}`
- `PATCH /daily-diaries/{id}`
- `GET /daily-diaries/compliance`

## 13. Performance APIs

- `GET /performance/scorecards`
- `GET /performance/scorecards/{employeeId}`
- `POST /performance/scorecards/{id}/manager-rating`
- `POST /performance/scorecards/{id}/adjustments`
- `POST /performance/scorecards/{id}/approve`
- `GET /performance/incentives`
- `POST /performance/incentives/{id}/approve`

### Feedback

- `POST /feedback-requests`
- `GET /feedback-requests/{token}`
- `POST /feedback-requests/{token}/submit`
- `GET /projects/{id}/feedback`

Public feedback endpoints must use expiring, project-specific tokens.

## 14. Budget and Expense APIs

### Budgets

- `GET /projects/{id}/budgets`
- `POST /projects/{id}/budgets`
- `PATCH /project-budgets/{id}`
- `POST /project-budgets/{id}/submit`
- `POST /project-budgets/{id}/approve`
- `GET /projects/{id}/budget-summary`

### Budget Extensions

- `POST /projects/{id}/budget-extensions`
- `GET /budget-extensions`
- `POST /budget-extensions/{id}/approve`
- `POST /budget-extensions/{id}/reject`

### Expenses

- `GET /expenses`
- `POST /expenses`
- `GET /expenses/{id}`
- `PATCH /expenses/{id}`
- `POST /expenses/{id}/submit`
- `POST /expenses/{id}/approve`
- `POST /expenses/{id}/reject`

## 15. Procurement APIs

### Vendors

- `GET /vendors`
- `POST /vendors`
- `GET /vendors/{id}`
- `PATCH /vendors/{id}`
- `GET /vendors/{id}/performance`

### Purchase Requirements

- `GET /purchase-requirements`
- `POST /purchase-requirements`
- `GET /purchase-requirements/{id}`
- `PATCH /purchase-requirements/{id}`
- `POST /purchase-requirements/{id}/submit`

### Quotations

- `POST /purchase-requirements/{id}/quotations`
- `GET /purchase-requirements/{id}/quotations`
- `GET /purchase-requirements/{id}/comparison`
- `POST /purchase-requirements/{id}/recommend-vendor`

### Purchase Approval

- `POST /purchase-requirements/{id}/approve`
- `POST /purchase-requirements/{id}/reject`
- `POST /purchase-requirements/{id}/request-clarification`

### Purchase Orders

- `GET /purchase-orders`
- `POST /purchase-orders`
- `GET /purchase-orders/{id}`
- `PATCH /purchase-orders/{id}`
- `POST /purchase-orders/{id}/issue`
- `POST /purchase-orders/{id}/acknowledge`

### Material Receipts

- `POST /purchase-orders/{id}/receipts`
- `GET /purchase-orders/{id}/receipts`
- `POST /material-receipts/{id}/confirm`
- `POST /material-receipts/{id}/report-issue`

### Vendor Bills

- `GET /vendor-bills`
- `POST /vendor-bills`
- `PATCH /vendor-bills/{id}`
- `POST /vendor-bills/{id}/verify`

## 16. Snag and Closure APIs

- `GET /projects/{id}/snag-lists`
- `POST /projects/{id}/snag-lists`
- `POST /snag-lists/{id}/items`
- `PATCH /snag-items/{id}`
- `POST /snag-items/{id}/submit-closure`
- `POST /snag-items/{id}/verify`
- `POST /projects/{id}/closure-check`
- `POST /projects/{id}/complete`

## 17. Reports and Dashboard APIs

- `GET /dashboards/owner`
- `GET /dashboards/pc`
- `GET /dashboards/site-engineer`
- `GET /dashboards/designer`
- `GET /dashboards/architect`
- `GET /dashboards/purchase`
- `GET /dashboards/accounts`

- `GET /reports/leads`
- `GET /reports/project-aging`
- `GET /reports/sla-compliance`
- `GET /reports/performance`
- `GET /reports/budget-variance`
- `GET /reports/procurement`
- `GET /reports/feedback`

Exports:

- `POST /exports`
- `GET /exports/{jobId}`

## 18. Notifications APIs

- `GET /notifications`
- `POST /notifications/{id}/read`
- `POST /notifications/read-all`
- `GET /notification-preferences`
- `PATCH /notification-preferences`

Internal background endpoints or jobs:

- SLA warning processor
- SLA breach processor
- Weekly follow-up generator
- Design delay escalator
- Feedback scheduler
- Payment reminder scheduler
- Delivery delay checker

## 19. Audit APIs

- `GET /audit-logs`
- `GET /entities/{entityType}/{entityId}/audit-history`

Audit access must be permission-controlled.

## 20. Webhooks and Integrations

### Outbound Events

- lead.created
- lead.sla_warning
- lead.sla_breached
- appointment.created
- proposal.sent
- approval.requested
- approval.completed
- payment.due
- payment.received
- budget.extension_requested
- purchase_order.issued
- material.delivery_due
- project.completed
- feedback.requested

### Integration Adapters

Keep email and WhatsApp behind provider interfaces so vendors can be changed without rewriting business logic.

Potential integrations:

- Email provider
- WhatsApp Business API provider
- Object storage
- PDF generation service
- Accounting export or Tally integration in a later version

## 21. Idempotency and Concurrency

Use idempotency keys for:

- Payment recording
- Purchase order issue
- Notification send
- Feedback submission
- File upload completion

Use optimistic locking or version checks for:

- Budget edits
- Vendor selection
- Approval decisions
- Project stage transition

## 22. Security Requirements

- Validate tenant/company ownership on every entity request.
- Validate role and record scope.
- Use signed URLs with limited lifetime for private files.
- Rate-limit public feedback and authentication endpoints.
- Sanitize filenames and uploaded metadata.
- Scan uploads where practical.
- Never trust client-side approval or financial totals.