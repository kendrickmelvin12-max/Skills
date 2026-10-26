# Scops-Inspired Design Reference

This file supplements `SKILL.md`. It describes reusable principles, not fixed brand tokens. The current repository is the source of truth for exact colors, fonts, spacing, radii, shadows, breakpoints, components, and motion values.

## Product feel
- Premium, calm, deliberate SaaS rather than a generic template.
- Clear typography, strong hierarchy, disciplined spacing, and restrained decoration.
- Useful feedback, visible status, and clear next actions.
- Accessible dark/light themes when supported.

## Existing project preservation
Inspect and preserve design tokens, shared components, typography, spacing rhythm, animation library and timing/easing, responsive breakpoints, navigation, loading/error conventions, route patterns, auth, and data-fetching conventions.

## Motion checklist
- Does motion clarify state or feedback?
- Does timing/easing match existing patterns?
- Does it avoid layout shifts?
- Does it work with keyboard and touch?
- Is reduced motion respected?
- Is the interface still usable when animation is reduced?

## Responsive checklist
- Mobile: no accidental overflow; readable labels; usable controls.
- Tablet: sensible density and no awkward breakpoint behavior.
- Desktop: clear content width and hierarchy.
- Long content: wrapping/truncation is intentional and full values remain accessible.
- Dialogs/menus fit the viewport and remain keyboard-accessible.
- Tables have a usable small-screen presentation when needed.

## State checklist
For important controls, consider default, hover, focus-visible, active, selected, disabled, pending/loading, success, empty, error, permission-denied, and offline/retry states where relevant. Implement only states that make sense for the actual component and backend.
