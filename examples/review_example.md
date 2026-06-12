# Review Example

## User Prompt

```txt
Use UIQA to review this CRM customer management page at 1440 and 768 widths. Include score, P0/P1/P2 findings, and Jira tasks.
```

## Expected Behavior

1. Select Standard Mode.
2. Load:
   - `rules/master_rulebook.md`
   - `docs/scoring_system.md`
   - `docs/persona_review.md`
   - `business/crm_rule.md`
   - `templates/qa_report.md`
   - `templates/jira_task.md`
3. Confirm business scene:
   - User: sales or customer success operator
   - Primary task: find priority customers and trigger follow-up
   - Expected state: customer table with filters, status, owner, next action
4. Review responsive, layout, spacing, typography, components, and business UX.
5. Score and output fix order.

## Sample Finding

| Severity | Module | Issue | Evidence | Impact | Root cause | Fix suggestion | Recheck criteria |
| --- | --- | --- | --- | --- | --- | --- | --- |
| P1 | Customer table | Row actions disappear at 768px | Screenshot shows action column outside visible scroll area | User cannot create follow-up task on mobile/narrow web | Table has fixed columns but no horizontal scroll container | Add `overflow-x: auto`, preserve first customer column, keep actions in sticky/right column or detail drawer | At 768px, customer name and follow-up action are both reachable |

## Sample Score

- Structure quality: 20 / 25
- Responsive readiness: 8 / 15
- Component and state coverage: 14 / 20
- Visual quality: 12 / 15
- Business UX: 12 / 15
- Trust and accessibility: 7 / 10
- Total: 73 / 100
- UX risk: High
- Conclusion: Fail until P1 responsive and state issues are fixed.

## Sample Jira Task

- Title: Fix customer table actions hidden at 768px
- Priority: P1
- Type: Responsive
- Owner role: Frontend
- Page or module: Customer management table
- Current behavior: row actions are outside the reachable area at 768px.
- Expected behavior: user can still follow up, assign, or open detail from narrow web.
- Acceptance criteria: at 768px, table scroll works, customer identity remains readable, and row actions are reachable without overlap.
