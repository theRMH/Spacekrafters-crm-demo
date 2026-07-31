# SpaceKrafters OS Database Design

## 1. Design Principles

- Use PostgreSQL as the primary relational database.
- Use UUIDs or globally unique identifiers for business entities.
- Every business table should include created_at, updated_at, created_by and updated_by where relevant.
- Sensitive records should be archived or cancelled rather than physically deleted.
- Store file binaries in object storage and store only metadata and object keys in the database.
- Keep an immutable audit trail for sensitive changes.
- Include company_id from the beginning to support future multi-company use, even if the first deployment has one company.

## 2. Organization and User Entities

### companies

- id
- name
- legal_name
- timezone
- currency
- active
- created_at

### users

- id
- company_id
- name
- email
- phone
- password_hash or authentication_provider_id
- status
- last_login_at

### roles

- id
- company_id
- name
- description

### user_roles

- user_id
- role_id
- effective_from
- effective_to

### permissions

- id
- resource
- action
- field_scope

### role_permissions

- role_id
- permission_id

### departments

- id
- company_id
- name

### employees

- id
- company_id
- user_id
- employee_code
- department_id
- manager_employee_id
- joining_date
- active

## 3. CRM Entities

### leads

- id
- company_id
- lead_number
- client_name
- phone
- email
- location
- site_address
- property_type
- lead_source
- estimated_budget
- expected_timeline
- requirement_notes
- assigned_pc_id
- priority
- status
- first_contact_due_at
- first_contact_at
- appointment_due_at
- converted_project_id
- lost_reason
- created_at

### lead_activities

- id
- lead_id
- activity_type
- activity_at
- user_id
- outcome
- notes
- next_action
- next_followup_at

### appointments

- id
- company_id
- lead_id
- project_id
- appointment_type
- scheduled_start
- scheduled_end
- location
- meeting_link
- organizer_id
- status
- confirmation_notes

### followups

- id
- lead_id
- project_id
- owner_id
- due_at
- completed_at
- outcome
- notes
- status

## 4. Project Entities

### projects

- id
- company_id
- project_number
- lead_id
- client_name
- project_name
- site_address
- location
- property_type
- contract_value
- start_date
- target_completion_date
- actual_completion_date
- current_stage
- progress_percentage
- status
- owner_employee_id

### project_assignments

- id
- project_id
- role_type
- employee_id
- assigned_at
- handover_status
- accepted_at
- released_at

### project_stage_history

- id
- project_id
- stage
- entered_at
- exited_at
- accountable_employee_id
- sla_due_at
- delayed_minutes
- delay_reason

### project_requirements

- id
- project_id
- requirement_summary
- room_scope_json
- preferences_json
- constraints
- exclusions
- approved_at

### project_handover_items

- id
- project_id
- checklist_code
- label
- required
- status
- verified_by
- verified_at
- comments

## 5. Site and Measurement Entities

### site_visits

- id
- company_id
- lead_id
- project_id
- appointment_id
- pc_employee_id
- se_employee_id
- scheduled_at
- started_at
- completed_at
- status
- notes

### rooms

- id
- project_id
- name
- floor
- room_type

### measurements

- id
- site_visit_id
- project_id
- room_id
- length
- width
- height
- door_window_details
- electrical_points_json
- plumbing_points_json
- existing_conditions
- notes
- submitted_by
- submitted_at

### site_checklist_items

- id
- site_visit_id
- checklist_code
- label
- required
- completed
- completed_by
- completed_at

## 6. Document and Design Entities

### documents

- id
- company_id
- lead_id
- project_id
- document_type
- title
- current_version_id
- access_level
- status
- archived_at

### document_versions

- id
- document_id
- version_number
- object_storage_key
- original_filename
- mime_type
- file_size
- checksum
- uploaded_by
- uploaded_at
- notes
- approval_status

### proposal_packs

- id
- lead_id
- project_id
- proposal_number
- version
- generated_file_key
- status
- created_by
- created_at

### proposal_pack_items

- proposal_pack_id
- document_version_id
- display_order

### proposal_sends

- id
- proposal_pack_id
- channel
- recipient
- sent_by
- sent_at
- external_message_id

### design_packages

- id
- project_id
- room_id
- package_name
- design_type
- assigned_designer_id
- status
- revision_count
- due_at

### design_submissions

- id
- design_package_id
- document_version_id
- submission_number
- submitted_by
- submitted_at
- submission_notes

### approvals

- id
- company_id
- entity_type
- entity_id
- approval_type
- requested_by
- approver_id
- status
- decision_at
- comments
- sequence_number

### client_review_events

- id
- design_package_id
- submission_id
- sent_at
- channel
- response_status
- response_at
- comments
- revision_requested

## 7. Task and Work Entities

### tasks

- id
- company_id
- project_id
- lead_id
- title
- description
- accountable_owner_id
- status
- priority
- start_at
- due_at
- completed_at
- parent_task_id
- task_type

### task_contributors

- task_id
- employee_id
- contribution_status
- submitted_at
- accepted_at

### task_dependencies

- task_id
- depends_on_task_id
- dependency_type

### daily_diaries

- id
- company_id
- employee_id
- project_id
- diary_date
- activity_type
- work_completed
- time_minutes
- status
- blocker
- next_action
- submitted_at

### comments

- id
- company_id
- entity_type
- entity_id
- author_id
- body
- created_at

## 8. Payment Entities

### payment_milestones

- id
- project_id
- milestone_name
- percentage
- due_amount
- due_date
- received_amount
- status

### payment_records

- id
- payment_milestone_id
- amount
- payment_date
- payment_mode
- reference_number
- proof_document_version_id
- recorded_by
- notes

## 9. Performance Entities

### sla_rules

- id
- company_id
- rule_code
- entity_type
- trigger_event
- duration_minutes
- warning_minutes
- escalation_policy_id
- active

### sla_instances

- id
- sla_rule_id
- entity_type
- entity_id
- owner_id
- started_at
- due_at
- completed_at
- status
- breached_at
- breach_reason

### employee_scores

- id
- company_id
- employee_id
- period_start
- period_end
- sla_score
- task_score
- diary_score
- quality_score
- manager_score
- client_score
- adjustment_points
- final_score
- status

### score_adjustments

- id
- employee_score_id
- points
- reason
- approved_by
- created_at

### client_feedback

- id
- project_id
- submitted_at
- overall_rating
- communication_rating
- timeliness_rating
- quality_rating
- pc_rating
- se_rating
- designer_rating
- comments

### incentive_recommendations

- id
- employee_score_id
- recommended_amount
- approved_amount
- approved_by
- status

## 10. Budget and Expense Entities

### project_budgets

- id
- project_id
- version
- total_working_budget
- status
- approved_by
- approved_at

### budget_categories

- id
- company_id
- code
- name
- active

### project_budget_lines

- id
- project_budget_id
- budget_category_id
- allocated_amount
- committed_amount
- actual_amount

### budget_extension_requests

- id
- project_id
- budget_category_id
- requested_amount
- reason
- impact_if_rejected
- requested_by
- status
- approved_by
- decided_at

### expenses

- id
- company_id
- project_id
- budget_category_id
- expense_type
- expense_date
- amount
- paid_by_employee_id
- payee
- description
- proof_document_version_id
- status
- submitted_by
- approved_by
- approved_at

## 11. Procurement Entities

### vendors

- id
- company_id
- vendor_code
- name
- category
- contact_name
- phone
- email
- address
- tax_identifier
- status
- rating

### purchase_requirements

- id
- company_id
- project_id
- requirement_number
- title
- boq_reference_document_id
- budget_category_id
- required_by_date
- requested_by
- status

### purchase_requirement_items

- id
- purchase_requirement_id
- item_name
- specification
- quantity
- unit
- estimated_amount

### vendor_quotations

- id
- purchase_requirement_id
- vendor_id
- quotation_number
- quotation_date
- total_amount
- tax_amount
- delivery_days
- payment_terms
- warranty_terms
- document_version_id
- status

### vendor_quotation_items

- id
- vendor_quotation_id
- purchase_requirement_item_id
- unit_rate
- quantity
- amount
- specification_compliant
- comments

### vendor_selections

- id
- purchase_requirement_id
- selected_vendor_id
- selected_quotation_id
- recommendation_reason
- recommended_by
- status
- approved_by
- approved_at

### purchase_orders

- id
- company_id
- project_id
- purchase_requirement_id
- vendor_id
- po_number
- po_date
- total_amount
- expected_delivery_date
- status
- issued_by
- document_version_id

### purchase_order_items

- id
- purchase_order_id
- purchase_requirement_item_id
- description
- quantity
- unit
- unit_rate
- amount

### material_receipts

- id
- purchase_order_id
- receipt_number
- received_at
- received_by
- status
- delivery_note_number
- notes

### material_receipt_items

- id
- material_receipt_id
- purchase_order_item_id
- quantity_received
- quantity_damaged
- quantity_short
- comments

### vendor_bills

- id
- vendor_id
- project_id
- purchase_order_id
- bill_number
- bill_date
- amount
- document_version_id
- status

## 12. Snag and Closure Entities

### snag_lists

- id
- project_id
- inspection_date
- created_by
- status

### snag_items

- id
- snag_list_id
- room_id
- description
- severity
- responsible_employee_id
- vendor_id
- due_at
- status
- before_document_id
- closure_document_id
- verified_by
- verified_at

### project_closures

- id
- project_id
- closure_date
- checklist_json
- payment_status
- approved_by
- closure_notes

## 13. Notification and Audit Entities

### notification_templates

- id
- company_id
- template_code
- channel
- subject
- body_template
- active

### notifications

- id
- company_id
- recipient_user_id
- template_id
- entity_type
- entity_id
- channel
- scheduled_at
- sent_at
- read_at
- status
- error_message

### escalation_policies

- id
- company_id
- name
- active

### escalation_steps

- id
- escalation_policy_id
- step_number
- delay_minutes
- recipient_role
- recipient_user_id
- channel

### audit_logs

- id
- company_id
- user_id
- action
- entity_type
- entity_id
- before_json
- after_json
- ip_address
- user_agent
- created_at

## 14. Recommended Indexes

- leads(company_id, status, assigned_pc_id)
- leads(phone)
- followups(owner_id, due_at, status)
- projects(company_id, current_stage, status)
- project_assignments(employee_id, released_at)
- project_stage_history(project_id, entered_at)
- tasks(accountable_owner_id, status, due_at)
- daily_diaries(employee_id, diary_date)
- documents(project_id, document_type)
- approvals(approver_id, status)
- expenses(project_id, status, expense_date)
- purchase_requirements(project_id, status)
- purchase_orders(vendor_id, status)
- notifications(recipient_user_id, status, scheduled_at)
- audit_logs(entity_type, entity_id, created_at)

## 15. Multi-Company Preparation

- All tenant-owned entities include company_id.
- Enforce tenant filtering in every query.
- Object storage keys should begin with company_id/project_id.
- Unique business numbers should be unique within company, not globally.
- Company configuration should control currency, timezone, workflow templates and numbering patterns.