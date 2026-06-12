# UIQA Review Method

Use this method to turn UI review from a visual checklist into a repeatable delivery acceptance workflow for B-side admin systems, SaaS workbenches, CRM, ERP, finance-tax, and design-to-code handoffs.

Core principle:

> B-side UI acceptance = business task completion + clear decision hierarchy + operable data components + responsive stability + complete states + accessibility + recheckable evidence.

## Review Inputs

Before judging quality, identify the review inputs:

- Artifact: local page, running app, screenshot, Figma export, prototype, implementation patch, or mixed evidence.
- Page: name, route, module, domain, and page type.
- User: role, permission level, business responsibility, and work frequency.
- Primary task: the job the page must support.
- Data context: tenant, company, project, object, time range, filters, status, and sample data state.
- Evidence level: full browser review, prototype/static review, screenshot-only review, code-only review, or mixed evidence.

If any input is missing, state the gap instead of inventing context.

## Method

1. Confirm the business scene.
   - Identify the target user, primary task, expected state, actual state, and release risk.
   - If the business scene is wrong or the primary workflow is missing, mark P0 before visual review.

2. Run the primary task path.
   - Start from page entry.
   - Locate the object or queue to act on.
   - Apply expected filters or selection.
   - Trigger the primary action.
   - Check completion, confirmation, feedback, and recovery.

3. Inspect decision hierarchy.
   - Check whether users can quickly answer: What is happening? What matters most? What should I do next?
   - Validate title, scope, KPI, alert, table, filter, and action relationships.

4. Inspect core components.
   - Tables, forms, filters, search, tabs, navigation, drawers, dialogs, popovers, charts, AI panels, and batch actions.
   - Validate normal, long-content, empty, loading, error, permission, disabled, selected, and saving states.

5. Inspect responsive behavior.
   - Use the default widths in `viewport_state_checklist.md` unless the product has explicit breakpoints.
   - Check overflow, clipping, sticky regions, table strategy, and touch targets.

6. Inspect accessibility and trust.
   - Check keyboard access, focus visibility, semantic status, color-independent status, contrast, error prevention, and recovery.
   - For AI or risk recommendations, check source, reason, confidence, and human review path.

7. Classify findings.
   - Use `severity_decision_tree.md` and `scoring_system.md`.
   - Every finding must include evidence, impact, root cause, fix suggestion, and recheck criteria.

8. Produce the handoff.
   - Use `qa_report.md` for review output.
   - Use `jira_task.md` for fix tickets.
   - Use `handoff_report_method.md` when a local HTML handoff report is useful.

9. Recheck after fixes.
   - Re-run the original evidence path and viewports.
   - Confirm no new overlap, clipping, state, permission, or workflow regression was introduced.

## Mode Guidance

- Quick Mode: use steps 1, 3, 7, and 8. Keep output chat-only unless a handoff artifact is requested.
- Standard Mode: use all steps for one complete screen or page.
- Audit Mode: use all steps across a workflow, release candidate, or design-to-code handoff; include fix tickets and recheck criteria.
- Regression Mode: compare old and new evidence using the same task path, viewports, and state coverage.

## Output Discipline

- Findings first.
- Evidence before opinion.
- Business blockers before visual polish.
- Do not score when evidence is too narrow.
- Mark unverified interaction, responsive, permission, and state behavior explicitly.
