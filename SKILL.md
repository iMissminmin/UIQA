---
name: uiqa
description: Review UI delivery quality for SaaS, ERP, CRM, finance-tax, B-side dashboards, admin systems, and design-to-code handoffs. Use when Codex needs to inspect screens, prototypes, Figma exports, local web pages, screenshots, or implementation patches for responsive behavior, Auto Layout or CSS layout quality, spacing, typography, shadows, component consistency, business UX, delivery risk, severity ranking, QA reports, local HTML handoff reports, or Jira/Feishu-ready fix tasks.
---

# UIQA

## Mission

Act as a design delivery inspector. Find issues that block implementation quality, user task completion, responsive stability, and business trust. Prioritize actionable findings over aesthetic commentary.

Use this skill for review, QA, audit, polish, release readiness, regression checks, and fix-ticket generation. Do not use it for general frontend implementation unless the user asks for review or asks to fix issues found during a UIQA review.

## Required Resource Routing

Read only the files needed for the task:

- Core inspection rules: [rules/master_rulebook.md](rules/master_rulebook.md)
- Review method: [docs/review_method.md](docs/review_method.md)
- Business scene check: [docs/business_scene_check.md](docs/business_scene_check.md)
- Viewport and state checklist: [docs/viewport_state_checklist.md](docs/viewport_state_checklist.md)
- Severity decision tree: [docs/severity_decision_tree.md](docs/severity_decision_tree.md)
- Handoff report method: [docs/handoff_report_method.md](docs/handoff_report_method.md)
- Scoring and severity: [docs/scoring_system.md](docs/scoring_system.md)
- Multi-persona review lens: [docs/persona_review.md](docs/persona_review.md)
- QA report format: [templates/qa_report.md](templates/qa_report.md)
- Jira / Feishu task format: [templates/jira_task.md](templates/jira_task.md)
- CRM-specific UX checks: [business/crm_rule.md](business/crm_rule.md)
- Finance-tax-specific UX checks: [business/finance_tax_rule.md](business/finance_tax_rule.md)
- SaaS/admin-specific UX checks: [business/saas_rule.md](business/saas_rule.md)
- Example report style: [examples/review_example.md](examples/review_example.md)

Load a business rule file when the page domain is explicit or can be inferred. If the domain is unclear, use `saas_rule.md` as the default and state the assumption.

Load `review_method.md`, `business_scene_check.md`, `viewport_state_checklist.md`, and `severity_decision_tree.md` for Standard, Audit, and Regression reviews. For Quick Mode, load only the method files needed for the user's question. Load `handoff_report_method.md` when creating a local HTML report, fix tickets, or a handoff-ready QA report.

## Review Modes

- Quick Mode: inspect one screen, screenshot, small change, or narrow question; report P0/P1/P2 findings and top fixes. Example: "look at this screenshot" or "check this patch for layout risk".
- Standard Mode: inspect a complete page, local web page, or prototype with enough visual evidence; include score, risk, persona views, and QA report. Example: "review this dashboard page".
- Audit Mode: inspect a workflow, design-to-code delivery, or release candidate with interaction and state evidence; include evidence, scoring breakdown, Jira/Feishu tasks, and recheck criteria. Example: "audit this release candidate before handoff".
- Regression Mode: compare old and new states; focus on introduced layout, interaction, responsive, and business-state regressions. Example: "compare the new implementation with the previous screenshot".

If the user does not specify a mode, choose Standard Mode for complete screens and Quick Mode for narrow questions.

## Evidence Protocol

Match claims to the evidence actually available:

- Local web page or running app: inspect at least desktop, tablet, and narrow/mobile widths when responsive quality is in scope. Record the checked widths. Check primary action visibility, overflow, clipping, table behavior, modal/drawer behavior, and important states when available.
- Screenshot or static export: treat the review as screenshot-only. Do not claim interaction, responsiveness, hover/focus, loading, error, permission, or keyboard behavior unless separately provided.
- Design-to-code or implementation patch: review structural risk from code and available visuals. Mark fidelity, interaction, and viewport behavior as unverified when no target design or browser evidence exists.
- Figma or prototype export: distinguish between design intent and implemented behavior. Do not assume CSS layout quality from static frames alone.
- Missing evidence: state it in the report and lower confidence rather than filling gaps with assumptions.

Use measured or visible evidence whenever possible: viewport width, screenshot name, inspected state, DOM/CSS observation, design frame, diff location, or user-provided business scenario.

## Execution Flow

1. Inventory the artifact.
   - Identify page name, domain, page type, target users, source artifact, viewport evidence, and implementation context.
   - Note missing evidence instead of guessing: screenshot unavailable, no mobile view, no target design, no user role, or no data state.
2. Select review mode and references.
   - Pick one mode.
   - Load `master_rulebook.md`, `review_method.md`, `business_scene_check.md`, `severity_decision_tree.md`, `scoring_system.md`, relevant business rule, and templates needed for the requested output.
   - Load `viewport_state_checklist.md` when responsive behavior or state coverage is in scope.
   - Load `persona_review.md` for Standard, Audit, or persona/risk-rationale requests.
   - Load `handoff_report_method.md` when producing a local HTML report or fix-ticket handoff.
3. Confirm business scene.
   - Check whether the page state matches the intended task, data state, user role, tenant/account, date range, and permissions.
   - If the business state is wrong or the core workflow is absent, mark P0 before visual polish.
4. Review delivery quality in this order.
   - Business scene and primary task
   - Responsive behavior
   - Auto Layout / CSS layout structure
   - Spacing and rhythm
   - Typography and information hierarchy
   - Shadow, border, surface, and depth
   - Component consistency and states
   - Trust, accessibility, and task completion
5. Classify severity.
   - Use P0/P1/P2 from `scoring_system.md`.
   - Every issue must include impact, root cause, and concrete fix.
6. Score and assess risk.
   - Use 100-point scoring only when the review scope is broad enough.
   - For narrow, screenshot-only, or code-only reviews, use severity and risk without a total score unless the user asks for a provisional score.
   - Label any score based on incomplete evidence as provisional.
   - Do not score above 70 with unresolved P0.
   - Do not score above 85 when responsive or important component states are unverified.
7. Produce outputs.
   - For reviews, use `qa_report.md`.
   - Create a local HTML report for Standard, Audit, and Regression reviews when there is enough evidence for a standalone handoff.
   - Use chat-only output for Quick Mode, narrow questions, screenshot-only triage, or when the user explicitly asks for chat-only output.
   - For fix tickets, use `jira_task.md`.
   - If implementation fixes are requested and files are available, fix P0/P1 issues before final handoff.
8. Handoff evidence.
   - State checked viewports, unverified areas, final score, risk level, top fix order, and any assumptions.

## Fix Workflow

When the user asks to fix issues after a UIQA review:

1. Fix P0 blockers first.
2. Fix release-impacting P1 issues.
3. Recheck responsive behavior and important component states.
4. Complete P2 polish only after the page is usable and stable.
5. Report what changed, what was verified, and what remains unverified.

Work with the current files. Do not revert user changes while fixing UIQA findings, and keep unrelated edits out of scope.

## Local HTML Report Output

For Standard, Audit, and Regression review tasks, generate a self-contained local HTML report by default when there is enough evidence for a standalone handoff.

Do not create an HTML report by default when:

- The user asks for a quick check, chat-only answer, or narrow issue review.
- The only evidence is a single screenshot and the requested output does not require a handoff artifact.
- There is no concrete artifact to review.
- The workspace is not writable and writing to `/tmp` would not help the user's workflow.

In these cases, return the same findings in chat and state that no HTML report was created.

Default location:

- Create reports under the current workspace at `reports/uiqa-{artifact-or-page-name}-{YYYYMMDD-HHMM}.html`.
- If the workspace is unavailable or not writable, create the report in `/tmp` and state that fallback.

Report requirements:

- Include conclusion, UX risk, checked evidence, assumptions, P0/P1/P2 findings, business UX assessment, responsive/layout assessment, component/state coverage, fix order, and recheck checklist.
- Include delivery score only when the scope and evidence support scoring; otherwise state "Not scored" and explain why.
- Include screenshots or visual evidence when available; use relative paths for local assets when the report and assets are in the same workspace.
- State the evidence level: full browser review, prototype/static review, screenshot-only review, code-only review, or mixed evidence.
- Keep the HTML self-contained with embedded CSS and no external CDN dependencies.
- Use a clear severity visual system: P0 as blocking, P1 as high risk, P2 as improvement.
- Make the report readable as a standalone handoff for product, design, and engineering.

After creating the report:

- Provide the local file path.
- If a local dev server is already running, the user explicitly asks for browser preview, or the report depends on local assets that need server verification, provide the browser URL as the preview link.
- If no server is started, provide the file path and state that it opens directly in a browser.

## Review Standards

- Findings first. Start with release-blocking or task-blocking problems.
- Prefer measured or visible evidence over taste statements.
- Treat overlap, clipping, unreadable compression, missing primary action, inaccessible critical state, and wrong business state as serious delivery risks.
- Do not over-index on decoration. Business task completion, responsive stability, and component state coverage carry more weight.
- Use persona review to explain why a problem matters, not to produce four separate verbose reviews.

## Output Contract

For review tasks, include:

- Conclusion: pass / conditional pass / fail
- Delivery score and UX risk, or "Not scored" with UX risk when the scope is narrow or evidence is incomplete
- P0/P1/P2 findings with impact, root cause, and fix suggestion
- Business UX assessment
- Responsive and layout assessment
- Component/state coverage
- Fix order
- Checked evidence and remaining assumptions
- Local HTML report path or browser URL when a report was created; otherwise state that chat-only output was used

For task-generation requests, create one ticket per fixable issue unless the issues share one root cause.
