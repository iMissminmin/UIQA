# Severity Decision Tree

Use this decision tree with `scoring_system.md`. Severity should reflect user task impact, business risk, and release readiness, not personal taste.

## Step 1: Does It Block The Primary Task?

If yes, mark P0.

Examples:

- Primary action cannot be found, reached, or completed.
- Workflow step is missing.
- Layout overlap blocks table, form, modal, drawer, or action.
- Required permission, tenant, object, or period is wrong.
- Submit, approve, delete, declaration, payment, or customer-impacting action is broken.

If no, continue.

## Step 2: Does It Create Business, Compliance, Or Trust Risk?

If the risk is severe and action can be taken on wrong or unsafe information, mark P0.

If the risk materially harms judgment but has a workaround, mark P1.

Examples:

- AI recommendation lacks evidence/source/confidence.
- Risk severity is unclear.
- Financial, tax, contract, approval, or audit action lacks confirmation or trace.
- Permission state is misleading.
- Error state hides recovery path.

## Step 3: Does It Make Important Work Inefficient Or Fragile?

If yes, mark P1.

Examples:

- Important content or row action is clipped.
- 1024px or 768px layout hides actions needed for completion.
- Filters are not visible, resettable, or aligned with the task.
- Table selection and batch action state are inconsistent.
- Empty/loading/error/permission states are missing for a major module.
- Component behavior changes unexpectedly across states.

## Step 4: Is It Local Polish Without Task Failure?

If yes, mark P2.

Examples:

- Spacing drift.
- Minor alignment issue.
- Weak hover/focus state that does not block use.
- Local typography inconsistency.
- Copy refinement.
- Non-critical color, border, or shadow issue.

## Step 5: Is It Optional Improvement?

If it does not affect release quality, mark Suggestion.

Examples:

- Alternative chart type that may improve insight but current chart is still accurate and usable.
- More convenient shortcut for expert users.
- Minor density preference where current density remains readable and stable.

## Escalation Rules

Escalate one level when:

- The issue affects a high-frequency workflow.
- The issue affects financial, legal, tax, compliance, customer, or security outcomes.
- The issue appears across multiple pages or shared components.
- The issue affects both desktop and narrow widths.
- The issue prevents independent verification or audit.

Do not escalate when:

- The issue is only a personal aesthetic preference.
- The behavior is unverified and no evidence supports the claim.
- The issue is outside the requested scope and has no release impact.

## Required Finding Format

Every finding must include:

- Severity
- Module or screen area
- Issue
- Evidence
- Impact
- Root cause
- Fix suggestion
- Recheck criteria

## Recheck Criteria Pattern

Use this pattern:

> Recheck at `[viewport/state/path]`: user can `[complete task]`; `[specific content/action]` remains visible; no new overlap, clipping, permission, or state regression appears.
