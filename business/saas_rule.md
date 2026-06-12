# SaaS / Admin Rule

Use as the default business rule for B-side SaaS, ERP, admin dashboards, task centers, settings, analytics, and AI operations pages.

## Core Business Chain

Todo -> Alert -> Quick Action -> Detail / Resolve -> Analytics -> Configuration

## Primary Users

- Operations specialist
- Team manager
- Administrator
- Reviewer
- Customer-facing internal user

## Common Page Types

- Dashboard
- Table management page
- Detail page
- Task queue
- Settings/configuration page
- Approval/review page
- AI assistant or insight workspace

## Must-Have UX Checks

- The page exposes current scope: tenant, workspace, project, user role, time range, or selected object.
- Primary action is visible and appropriate for the current state.
- Alerts and exceptions include severity, reason, owner, and next action.
- Tables support scan, filter, sort, row action, batch action, and pagination or virtual scroll.
- Settings pages distinguish safe changes from high-risk changes.
- Analytics panels answer a business question and link to drill-down or next action.
- AI panels stay tied to selected object or current page state.

## Required States

- Empty
- Loading
- Error
- Permission/locked
- Disabled
- Selected
- Batch operation
- Saving/saved/failed
- AI thinking/generated/uncertain/unavailable

## P0 Examples

- Primary workflow cannot be completed.
- Permission state is wrong or exposes restricted action.
- Critical alert has no action path.
- Data state contradicts the page title or target scene.
- Layout overlap blocks table, form, modal, or primary action.

## P1 Examples

- Active filters are not visible or resettable.
- Batch action appears without selection context.
- Important settings lack validation or conflict warning.
- AI output is not attributable or actionable.
- Responsive layout hides secondary actions needed for completion.
