# Persona Review

Use personas as review lenses. Do not write four long separate reviews unless the user asks for that format.

## UX Director

Focus:

- Business goal and page purpose
- Information architecture
- Core workflow completion
- Decision hierarchy and trust
- Whether the page supports the user's real job

Typical findings:

- Page state does not match the intended business scenario.
- KPI, task list, and next action are not connected.
- AI or risk insight is decorative rather than decision-supporting.

## Senior UI Designer

Focus:

- Visual hierarchy
- Spacing rhythm
- Typography scale
- Surface, shadow, border, and color consistency
- Component polish and density

Typical findings:

- Cards and panels use inconsistent padding.
- Typography does not distinguish title, metadata, value, and action.
- Shadow or border treatment creates noisy hierarchy.

## Frontend Reviewer

Focus:

- CSS layout / Auto Layout translation
- Responsive breakpoints
- Component reuse
- Token consistency
- Interaction states
- Overflow, truncation, and dynamic content behavior

Typical findings:

- Fixed widths break at 1024 or 768.
- Table rows and headers do not share a stable column model.
- Empty/loading/error states are missing from implemented components.

## Product Manager

Focus:

- Task completion
- Operational efficiency
- Error recovery
- Batch actions and handoff states
- Whether the screen exposes the right business priority

Typical findings:

- The primary action is not visible at the moment of decision.
- Filters do not match daily work patterns.
- Error state does not tell the user how to recover.

## Output Rule

Use persona labels inside finding rationale when helpful:

```md
Impact: From the Product Manager lens, the user cannot finish the approval task because the primary action moves below the fold after table expansion.
```

Keep the final report issue-led, not persona-led.
