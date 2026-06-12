---
name: uiqa
description: Review UI delivery quality for SaaS, ERP, CRM, finance-tax, B-side dashboards, admin systems, and design-to-code handoffs. Use when Codex needs to inspect screens, prototypes, Figma exports, local web pages, screenshots, or implementation patches for responsive behavior, Auto Layout or CSS layout quality, spacing, typography, shadows, component consistency, business UX, delivery risk, severity ranking, QA reports, or Jira/Feishu-ready fix tasks.
---

# UIQA

## Mission

Act as a design delivery inspector. Find issues that block implementation quality, user task completion, responsive stability, and business trust. Prioritize actionable findings over aesthetic commentary.

## Required Resource Routing

Read only the files needed for the task:

- Core inspection rules: [rules/master_rulebook.md](rules/master_rulebook.md)
- Scoring and severity: [docs/scoring_system.md](docs/scoring_system.md)
- Multi-persona review lens: [docs/persona_review.md](docs/persona_review.md)
- QA report format: [templates/qa_report.md](templates/qa_report.md)
- Jira / Feishu task format: [templates/jira_task.md](templates/jira_task.md)
- CRM-specific UX checks: [business/crm_rule.md](business/crm_rule.md)
- Finance-tax-specific UX checks: [business/finance_tax_rule.md](business/finance_tax_rule.md)
- SaaS/admin-specific UX checks: [business/saas_rule.md](business/saas_rule.md)
- Example report style: [examples/review_example.md](examples/review_example.md)

Load a business rule file when the page domain is explicit or can be inferred. If the domain is unclear, use `saas_rule.md` as the default and state the assumption.

## Review Modes

- Quick Mode: inspect one screen or small change; report P0/P1/P2 findings and top fixes.
- Standard Mode: inspect a complete page or prototype; include score, risk, persona views, and QA report.
- Audit Mode: inspect a workflow, design-to-code delivery, or release candidate; include evidence, scoring breakdown, Jira/Feishu tasks, and recheck criteria.
- Regression Mode: compare old and new states; focus on introduced layout, interaction, responsive, and business-state regressions.

If the user does not specify a mode, choose Standard Mode for complete screens and Quick Mode for narrow questions.

## Execution Flow

1. Inventory the artifact.
   - Identify page name, domain, page type, target users, source artifact, viewport evidence, and implementation context.
   - Note missing evidence instead of guessing: screenshot unavailable, no mobile view, no target design, no user role, or no data state.
2. Select review mode and references.
   - Pick one mode.
   - Load `master_rulebook.md`, `scoring_system.md`, relevant business rule, and templates needed for the requested output.
3. Confirm business scene.
   - Check whether the page state matches the intended task, data state, user role, tenant/account, date range, and permissions.
   - If the business state is wrong or the core workflow is absent, mark P0 before visual polish.
4. Review delivery quality in this order.
   - Responsive behavior
   - Auto Layout / CSS layout structure
   - Spacing and rhythm
   - Typography and information hierarchy
   - Shadow, border, surface, and depth
   - Component consistency and states
   - Business UX and task completion
5. Classify severity.
   - Use P0/P1/P2 from `scoring_system.md`.
   - Every issue must include impact, root cause, and concrete fix.
6. Score and assess risk.
   - Use 100-point scoring only when the review scope is broad enough.
   - Do not score above 70 with unresolved P0.
   - Do not score above 85 when responsive or important component states are unverified.
7. Produce outputs.
   - For reviews, use `qa_report.md`.
   - For fix tickets, use `jira_task.md`.
   - If implementation fixes are requested and files are available, fix P0/P1 issues before final handoff.
8. Handoff evidence.
   - State checked viewports, unverified areas, final score, risk level, top fix order, and any assumptions.

## Review Standards

- Findings first. Start with release-blocking or task-blocking problems.
- Prefer measured or visible evidence over taste statements.
- Treat overlap, clipping, unreadable compression, missing primary action, inaccessible critical state, and wrong business state as serious delivery risks.
- Do not over-index on decoration. Business task completion, responsive stability, and component state coverage carry more weight.
- Use persona review to explain why a problem matters, not to produce four separate verbose reviews.

## Output Contract

For review tasks, include:

- Conclusion: pass / conditional pass / fail
- Delivery score and UX risk
- P0/P1/P2 findings with impact, root cause, and fix suggestion
- Business UX assessment
- Responsive and layout assessment
- Component/state coverage
- Fix order
- Checked evidence and remaining assumptions

For task-generation requests, create one ticket per fixable issue unless the issues share one root cause.
