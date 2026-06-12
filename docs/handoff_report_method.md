# Handoff Report Method

Use this method when the review needs to be handed off to product, design, frontend, QA, or implementation owners.

## When To Create A Local HTML Report

Create a self-contained local HTML handoff report by default for:

- Standard reviews with enough evidence for a complete page judgment.
- Audit reviews of workflows, release candidates, or design-to-code deliveries.
- Regression reviews with before/after evidence.
- Reviews where product, design, and engineering need a shared artifact.

Use chat-only output for:

- Quick Mode.
- Narrow questions.
- Single screenshot triage unless a handoff artifact is requested.
- Code-only review without visual/browser evidence.
- Cases with no concrete artifact to review.

## Report Content

The report must include:

- Conclusion: pass, conditional pass, or fail.
- UX risk: low, medium, high, or critical.
- Score: final, provisional, or not scored.
- Evidence level.
- Checked viewports, states, artifacts, routes, screenshots, and assumptions.
- P0/P1/P2 findings with evidence, impact, root cause, fix suggestion, and recheck criteria.
- Business UX assessment.
- Responsive and layout assessment.
- Component and state coverage.
- Accessibility and trust notes.
- Fix order.
- Recheck checklist.

## Score Handling

Include a delivery score only when the review scope and evidence support it.

Do not score by default for:

- Narrow questions.
- Single screenshot triage.
- Code-only review without visual/browser evidence.
- Reviews with too many unverified states.

When a score is required but evidence is incomplete, label it provisional and apply caps from `scoring_system.md`.

## Fix Ticket Handoff

Create one Jira/Feishu task per independent root cause unless one fix clearly resolves multiple findings.

Each task should include:

- Title
- Priority
- Type
- Owner role
- Current behavior
- Expected behavior
- Evidence
- Impact
- Root cause
- Recommended fix
- Acceptance criteria

## Local HTML Requirements

- Store reports at `reports/uiqa-{artifact-or-page-name}-{YYYYMMDD-HHMM}.html`.
- Keep reports self-contained with embedded CSS and no external CDN dependencies.
- Use clear severity styling: P0 blocking, P1 high risk, P2 improvement.
- Include screenshots or visual evidence only when available.
- Use relative paths for local assets when the report and assets are in the same workspace.
- Provide the local file path after creation.

Only start or reference a local dev server when:

- A server is already running and the report is reachable through it.
- The user explicitly asks for browser preview.
- The report depends on local assets that are easier to verify through a server.

Otherwise, provide the HTML file path and state that it opens directly in a browser.

## Recheck Checklist

After fixes, verify:

- Original P0/P1 evidence no longer reproduces.
- Primary task remains completable.
- Checked viewports still pass.
- Relevant states still pass.
- No new overlap, clipping, focus, permission, or data-state regression appears.
- Score and conclusion are updated only after evidence supports the change.
