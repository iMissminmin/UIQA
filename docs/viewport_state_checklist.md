# Viewport and State Checklist

Use this checklist for local pages, running apps, responsive screenshots, or design-to-code handoffs. If only one screenshot or a static export is available, mark unverified viewports and states explicitly.

## Default Viewports

Use these widths unless the product defines its own breakpoints:

- `1440px`: desktop, full workspace.
- `1280px`: laptop or common enterprise display.
- `1024px`: narrow desktop or tablet landscape.
- `768px`: tablet or constrained browser window.
- `390px`: mobile/H5 narrow view.

Record the checked widths in the final report.

## Responsive Acceptance

At each checked width, verify:

- Main content does not overlap sidebar, header, footer, drawer, modal, AI panel, or sticky action bar.
- Primary action remains visible or reachable through a clear responsive pattern.
- Table strategy is explicit: horizontal scroll, fixed object/action columns, column prioritization, mobile card transformation, or detail view.
- Filters, tabs, segmented controls, tags, status chips, and button groups wrap without clipping text.
- Forms preserve visible labels, validation messages, helper text, and submit actions.
- Dialogs and drawers have clear scroll behavior and stable footer actions.
- Charts preserve labels, units, legends, and value meaning.
- Touch targets are at least `44px` on mobile/H5 when touch use is in scope.
- Long Chinese, English, numbers, IDs, names, and mixed strings do not break layout.

## Required UI States

Check the states relevant to the page:

- Default
- Hover
- Focus
- Active
- Disabled
- Selected
- Loading
- Skeleton
- Empty
- Error
- Permission denied or locked
- Saving
- Saved
- Failed
- Syncing
- Long content
- No results after filtering
- Batch selection
- Confirmation
- Undo or recovery
- AI thinking
- AI generated
- AI uncertain
- AI unavailable

## Component-Specific Checks

Tables:

- Header and rows share a stable column model.
- Business object appears in the first meaningful column.
- Sort, filter, search, pagination, row action, and batch action behave consistently.
- Row actions are reachable on narrow widths.
- Selection state and batch action state are synchronized.

Forms:

- Labels remain visible.
- Required fields are clear.
- Validation appears near the field.
- Error summary or focus routing exists for complex forms.
- Destructive or irreversible submit actions are confirmed.

Dialogs and drawers:

- Title states purpose.
- Close/cancel behavior is clear.
- Focus does not disappear behind the overlay.
- Content scroll and footer actions do not overlap.

Navigation:

- Current location is visible.
- Collapsed nav has labels or tooltips.
- Breadcrumb, tabs, and side navigation do not contradict each other.

AI or risk panels:

- AI output is tied to the selected object or page state.
- Reason, evidence, source, confidence, and uncertainty are visible when the output influences decisions.
- The user has a review, dismiss, retry, or escalation path.

## Evidence Output

For each review, report:

- Widths checked.
- States checked.
- States unavailable.
- States not checked and why.
- Any viewport or state where the primary task fails.
