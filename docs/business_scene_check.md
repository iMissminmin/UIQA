# Business Scene Check

Use this method before visual or layout review. In B-side systems, a visually polished page still fails if it represents the wrong business scene or prevents the user from completing the real task.

## Scene Inventory

Capture these fields:

- Domain: SaaS/admin, CRM, ERP, finance-tax, data operations, customer service, approval, settings, or another explicit domain.
- Page type: dashboard, table management, detail, task queue, review/approval, settings, analytics, AI workspace, or workflow step.
- Target user: operator, manager, reviewer, administrator, accountant, sales, customer success, or service owner.
- Primary task: the one task that must be completable on this page.
- Business object: customer, opportunity, invoice, voucher, contract, risk, ticket, order, task, company, project, user, or record.
- Scope: tenant, workspace, company, project, period, owner, region, permission, or selected object.
- Expected state: what the page should show for the task.
- Actual state: what the evidence shows.
- Risk context: financial, legal, compliance, customer-impacting, operational, or low-risk.

## Core Questions

Ask these questions in order:

1. Does the page show the correct business object first?
2. Is the current scope visible before the user acts?
3. Is the primary action visible, enabled only when valid, and appropriate for the current state?
4. Can the user distinguish normal, urgent, failed, risky, blocked, and completed items?
5. Are filters, time range, ownership, and permission context visible and recoverable?
6. Does the page provide a clear next action for alerts, exceptions, failed sync, empty data, and permission limits?
7. Are high-risk operations confirmed, reversible when possible, and traceable?
8. If AI or automation influences a decision, does it expose reason, source, confidence, and human review path?

## P0 Scene Failures

Mark P0 when any of these are true:

- The page represents the wrong tenant, company, period, role, or selected object.
- The stated page purpose and actual content contradict each other.
- The primary workflow is absent or cannot be completed.
- A critical action is broken, hidden, or blocked by layout.
- Permission state exposes restricted data or restricted actions.
- High-risk submission, deletion, approval, tax, finance, contract, or customer-impacting action can proceed without required confirmation or trace.
- AI output directly drives a decision but has no evidence/source and no review path.

## P1 Scene Failures

Mark P1 when any of these are true:

- The primary action exists but is hard to identify at the decision moment.
- Important status, reason, owner, deadline, or recovery path is missing.
- Filters do not match the daily work pattern.
- The user must open many records to discover priority or risk.
- Empty, error, permission, or sync failure state does not tell the user what to do next.
- Batch action appears without selection context or safety guard.

## Acceptance Criteria

A business scene passes when:

- The correct object, scope, state, and role are visible.
- The primary task can be completed without hidden assumptions.
- Risk and exception states include reason and next action.
- High-risk actions include prevention, confirmation, and trace.
- Missing evidence is explicitly documented instead of inferred.
