# Master Rulebook

Use this file as the default inspection checklist for UI delivery reviews.

## Review Order

1. Responsive
2. Auto Layout / CSS layout structure
3. Spacing
4. Typography
5. Shadow / border / surface
6. Components and states
7. Business UX

## 1. Responsive

Check:

- The page remains usable at desktop, laptop, tablet, and narrow widths.
- Main content does not overlap with sidebar, header, drawers, modals, or AI panels.
- Tables have horizontal scroll, column prioritization, or mobile card transformation.
- Primary actions remain visible and reachable.
- Filters, tabs, status chips, and button groups wrap without clipping text.
- Touch targets are at least `44px` on mobile/H5.

Common issues:

- Fixed-width desktop layout squeezed into 768px.
- Right panel hiding table actions.
- Text clipped inside cards, buttons, tabs, or badges.
- Charts or tables losing labels and units.
- Sticky footer/header covering content.

Escalate:

- P0: user cannot complete the primary task at a supported width.
- P1: important content or action is hidden, clipped, or requires awkward workaround.
- P2: local wrapping, spacing, or polish issue that does not block completion.

## 2. Auto Layout / CSS Layout

Check:

- Related elements are grouped with flex/grid/Auto Layout, not loose absolute placement.
- Parent containers define stable sizing, gaps, and alignment.
- Cards, rows, tables, forms, and navs have predictable min/max widths.
- Dynamic content can grow by about 30% without breaking the layout.
- Overlays, drawers, popovers, and modals have clear stacking and scroll behavior.

Common issues:

- Manual x/y positioning causes drift after content changes.
- Table columns do not align between header and rows.
- Card heights jump when hover, status, or loading states appear.
- Empty/error/loading states have different dimensions from normal content.

Escalate:

- P0: layout overlap makes the page unusable.
- P1: fragile layout breaks under realistic content, resizing, or state changes.
- P2: inconsistent alignment or local grouping issue.

## 3. Spacing

Check:

- Page-level gaps follow a consistent rhythm.
- Card padding, row height, form gaps, and button groups use repeated tokens.
- Dense admin pages stay scannable without becoming cramped.
- Related controls are visually grouped; unrelated areas have enough separation.

Default tokens:

- Micro gap: `4px`
- Compact gap: `8px`
- Control gap: `12px`
- Card internal gap: `16px`
- Section gap: `24px`
- Major page gap: `32px`

Common issues:

- Mixed `18/20/22/26px` arbitrary spacing.
- Toolbar controls appear disconnected from the table they affect.
- Nested cards add double padding and visual noise.
- Status or action columns are too close to data columns.

Escalate:

- P1: spacing weakens hierarchy or causes misoperation.
- P2: inconsistent but non-blocking spacing.

## 4. Typography

Check:

- Page title, section title, card title, body, caption, and table text form a clear scale.
- Critical values, statuses, and actions are readable at first scan.
- Long Chinese and English strings wrap or truncate intentionally.
- Button, tag, tab, and table header text does not clip.
- Numeric data aligns consistently.

Default scale:

- Page title: `24px / 32px / 600`
- Section title: `18px / 26px / 600`
- Card title: `16px / 24px / 600`
- Body: `14px / 22px / 400`
- Secondary: `13px / 20px / 400`
- Caption: `12px / 18px / 400`
- Table header: `13px / 20px / 600`
- Table cell: `13-14px / 20px / 400`

Escalate:

- P1: hierarchy hides the primary task, key risk, or decision.
- P2: inconsistent local sizing, weight, line height, or truncation.

## 5. Shadow / Border / Surface

Check:

- Background, surfaces, borders, and shadows create a calm enterprise hierarchy.
- Shadows do not imply fake clickability.
- Active, selected, disabled, warning, and danger states are visually distinct.
- Contrast is sufficient for text, badges, and disabled states.

Default style:

- App background: light gray or neutral.
- Work surfaces: white.
- Borders: low-contrast neutral.
- Shadows: subtle, used for floating elements or important panels.
- Avoid heavy glow, excessive glassmorphism, and decorative gradients in admin systems.

Escalate:

- P1: visual hierarchy misleads task priority or hides risk state.
- P2: shadow, border, contrast, or surface polish issue.

## 6. Components and States

Check:

- Buttons: primary action is clear; destructive actions require confirmation.
- Tables: first column anchors the business object; row actions are stable.
- Forms: labels remain visible; validation is near the field; required fields are clear.
- Filters: active filters are visible and resettable.
- Navigation: selected state is obvious; collapsed nav has labels or tooltips.
- Tags/status: status uses text plus color or icon, not color alone.
- Dialogs/drawers: purpose, close behavior, focus, and scroll are clear.
- Empty/loading/error/permission states exist for major modules.

Escalate:

- P0: missing component prevents the workflow from completing.
- P1: important state is missing or a risky action lacks confirmation.
- P2: local state, hover, focus, or label issue.

## 7. Business UX

Check:

- The page supports the user's primary job without unnecessary detours.
- Information architecture follows business priority, not visual decoration.
- Page title, data state, filters, key metrics, and actions match the intended scene.
- AI suggestions, risk prompts, and automation outputs include reason, evidence, source, or confidence when they influence decisions.
- Audit trail, history, or approval records exist when trust/compliance matters.

Escalate:

- P0: wrong business scene, wrong data state, missing core workflow, or impossible task completion.
- P1: primary action unclear, important state missing, or AI output is not trustworthy enough to act on.
- P2: copy, grouping, or local efficiency issue.

## Evidence Rules

- Mention checked viewport widths when responsive quality is judged.
- Mark unverified areas explicitly.
- Do not claim pixel-perfect delivery without target design evidence.
- Do not score implementation fidelity when the target design or expected state is unavailable; score delivery quality instead.
