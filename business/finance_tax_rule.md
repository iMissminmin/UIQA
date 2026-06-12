# Finance-Tax Rule

Use for accounting, tax declaration, invoice, voucher, reconciliation, contract risk, compliance review, and finance-tax AI workbenches.

## Core Business Chain

Data Source -> Risk / Exception -> Todo -> Review -> Submit / Resolve -> Audit Trail -> Analysis

## Primary Users

- Accountant
- Tax consultant
- Finance manager
- Compliance reviewer
- Agency service operator

## Common Page Types

- Tax risk dashboard
- Invoice/voucher review queue
- Reconciliation workspace
- Declaration workflow
- Contract risk review
- Exception detail page
- AI finance-tax assistant panel

## Must-Have UX Checks

- Page title, period, tenant/company, and data source are visible when decisions depend on them.
- Risk or exception states include reason, impact, severity, and next action.
- AI findings show evidence/source such as invoice, voucher, contract clause, tax rule, or transaction record.
- Workflow status is explicit: unstarted, checking, failed, needs review, submitted, resolved.
- High-risk operations require confirmation and leave audit records.
- Tables expose the business object first: invoice, voucher, declaration item, contract, company, or exception.
- Users can recover from sync, calculation, upload, and permission errors.

## Required States

- Data loading / syncing
- No risk found
- Risk found
- AI uncertain / needs human review
- Calculation failed
- Source document missing
- Permission denied
- Submission failed
- Submitted / locked / archived

## P0 Examples

- Wrong company, tenant, period, or tax category is shown for the target review.
- A high-risk exception cannot be opened or resolved.
- AI risk result has no source or evidence but drives a decision.
- Submit/declaration action is available in an invalid or failed state.
- Audit-critical action has no confirmation or trace.

## P1 Examples

- Risk severity is color-only with no text or icon.
- Failure state gives no retry or manual recovery path.
- Evidence is hidden behind unclear navigation.
- Period/company context is below the fold or easy to miss.
- Mobile or narrow view hides risk action buttons.
