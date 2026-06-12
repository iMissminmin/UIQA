# CRM Rule

Use for customer management, sales pipeline, opportunity management, customer success, follow-up workbenches, renewal, and performance analysis.

## Core Business Chain

Customer -> Lead / Opportunity -> Follow-up -> Deal / Renewal -> Performance -> Analysis

## Primary Users

- Sales operator
- Customer success manager
- Team manager
- Consultant or service owner

## Common Page Types

- Customer list
- Customer detail
- Opportunity pipeline
- Follow-up workbench
- Renewal/risk queue
- Performance dashboard
- AI recommended next action panel

## Must-Have UX Checks

- The first visible object is the customer, lead, opportunity, or account being acted on.
- Priority customers or high-risk opportunities are scannable without opening every row.
- Filters support common work patterns: owner, stage, priority, last contact, next follow-up, risk, region, source.
- Row actions match CRM work: call, message, assign, follow up, create task, update stage, view detail.
- Customer detail includes key facts, timeline, owner, last interaction, next action, and risk/intent signals.
- Batch actions are only shown when selection exists and are reversible or confirmed.
- AI recommendation explains why a customer or opportunity is prioritized.

## Required States

- No customers / no opportunities
- Loading customer data
- Sync failed or CRM integration failed
- Permission-limited customer view
- Duplicate customer
- Overdue follow-up
- High-value or high-risk opportunity
- AI uncertain recommendation

## P0 Examples

- Page claims to be customer risk review but shows unrelated generic list.
- Primary customer/opportunity action is missing.
- Owner or permission state exposes data incorrectly.
- Opportunity stage action can be changed without confirmation or audit when business-critical.

## P1 Examples

- Priority score exists but no reason or source is shown.
- Filters do not support daily follow-up work.
- Row actions shift or disappear on narrow screens.
- Customer timeline is missing, making follow-up decisions weak.
- Empty state has no import, create, or sync recovery action.
