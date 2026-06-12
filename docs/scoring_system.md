# Delivery Score and Severity

Use scoring when the review covers a complete screen, workflow, release candidate, or design-to-code delivery. For narrow questions, use severity only.

## Severity

- P0 Blocker: blocks release or task completion. Examples: wrong business scene, missing core workflow, severe layout overlap, unusable responsive state, broken primary action, dangerous action without confirmation, critical data mismatch.
- P1 Must Fix: materially harms delivery quality or user efficiency. Examples: missing important state, unclear primary action, fragile responsive behavior, clipped important content, inconsistent table/action behavior, AI output without evidence for a decision.
- P2 Recommended: local polish or optimization. Examples: spacing drift, minor alignment issue, weak hover/focus state, copy refinement, non-critical visual inconsistency.
- Suggestion: optional improvement that does not affect release quality.

## Score Weights

Total: 100 points.

| Dimension | Weight | What to inspect |
| --- | ---: | --- |
| Structure quality | 25 | layout model, grouping, Auto Layout/CSS structure, table/form stability |
| Responsive readiness | 15 | desktop/laptop/tablet/narrow behavior, wrapping, scroll, touch targets |
| Component and state coverage | 20 | buttons, tables, filters, forms, navigation, empty/loading/error/permission states |
| Visual quality | 15 | spacing, typography, shadow, border, surface, hierarchy |
| Business UX | 15 | task completion, scene match, IA, primary action, workflow efficiency |
| Trust and accessibility | 10 | risk evidence, AI explainability, contrast, keyboard/focus, status semantics |

## Deduction Guide

Use ranges, not exact math, when evidence is incomplete:

- Severe overlap or impossible task: `-20` to `-35`
- Wrong business state or missing core workflow: `-25` to `-40`
- Unsupported 768/1024 responsive behavior: `-10` to `-20`
- Important content clipped or hidden: `-8` to `-16`
- Missing empty/loading/error/permission state: `-4` to `-12`
- Primary action unclear or duplicated: `-6` to `-12`
- Table/filter usability issue: `-5` to `-12`
- AI recommendation lacks reason/evidence/confidence: `-5` to `-12`
- Inconsistent typography/spacing/component use: `-2` to `-8`
- Minor polish issue: `-1` to `-4`

## Score Caps

- Any unresolved P0: maximum `70`.
- Multiple unresolved P0 issues: maximum `60`.
- Core workflow missing: maximum `55`.
- Business scene or data state wrong: maximum `65`.
- No responsive evidence for an otherwise complete review: maximum `85`.
- Major component states unverified: maximum `85`.
- No target design available in a design-to-code review: maximum `80` for fidelity, but delivery quality may still be scored.
- Screenshot-only review without interaction evidence: maximum `88`.

## Risk Level

- Critical: P0 exists, release should stop.
- High: no P0, but one or more P1 issues can cause user failure, compliance risk, or repeated support cost.
- Medium: P1 issues are limited and workaround exists; P2 polish remains.
- Low: no P0/P1; only minor P2 or suggestions remain.

## Pass Criteria

- Pass: score `90+`, no P0/P1, responsive and states verified for requested scope.
- Conditional pass: score `75-89`, no P0, P1 issues have clear fix path and do not block release.
- Fail: score below `75`, any unresolved P0, or important evidence contradicts the target business scene.

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

Avoid vague findings such as "layout is not good" or "visual needs polish". Convert them into measurable issues.
