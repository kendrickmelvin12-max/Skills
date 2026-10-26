# Scops Design Skill — Prompt Library

Copy/paste these prompts into Antigravity. They activate the `scops-design-system` skill and help keep implementation scoped and consistent.

## 1. Default prompt for any build
```text
Use the `scops-design-system` skill for this task.

First inspect the existing repository, its design tokens, fonts, shared components, responsive breakpoints, navigation, animation library, and neighboring screens. Make a short implementation plan before editing.

If this is Scops, preserve its Inter body/UI typography, Manrope headings, and Geist Mono technical text roles. Preserve the desktop sidebar animation, mobile-specific navigation/layout, settings-card patterns, and existing motion timing/easing unless I explicitly ask for a change.

Make only the changes needed for my request. Reuse components and tokens; do not introduce a competing design system, redesign unrelated screens, or invent fake functionality. Keep responsive behavior and accessibility in scope.

After implementation, run relevant checks, inspect the changed UI at mobile/tablet/desktop widths if browser tools are available, test important interaction states, and report changed files, checks actually run, and remaining issues.
```

## 2. Start a completely new project
```text
Use the `scops-design-system` skill as the quality standard for this new project.

Before implementation, establish the project's visual direction and define a small, coherent design system: typography roles, semantic color tokens, spacing scale, radii, surfaces, component patterns, responsive breakpoints, and motion rules. Use Scops as inspiration for calm, premium SaaS craft—not as a reason to copy its branding blindly.

If this is an extension of Scops, use Inter for body/UI, Manrope for headings, and Geist Mono for technical text. For a different product, choose fonts that fit its purpose and document the choice.

Build reusable buttons, form controls, cards, navigation, feedback states, and layout primitives only where useful. Make desktop and mobile layouts intentional from the start. Respect accessibility, reduced motion, loading/empty/error/success states, and real backend behavior. Do not fake capabilities. Finish with responsive and functional verification and a concise report.
```

## 3. Targeted change without redesigning everything
```text
Use the `scops-design-system` skill. This is a targeted change, not a full redesign.

Inspect the relevant component and nearby screens first. Reuse existing tokens and components. Preserve current typography, layout, desktop/mobile behavior, navigation, and all existing animation durations, easing, delays, stagger, and transition behavior unless the requested change explicitly requires modifying them.

Change only what is necessary for: [DESCRIBE YOUR REQUEST].

Do not refactor unrelated files, change APIs/data models, replace the design system, or introduce new dependencies unless required. Verify the changed flow and run relevant checks. Report exactly what changed and what was tested.
```

## 4. Desktop sidebar, mobile layout, and settings cards
```text
Use the `scops-design-system` skill and inspect the existing source before touching the UI.

For desktop navigation, preserve the current collapsed/expanded sidebar behavior, icon alignment, label reveal/fade, logo change, active-route indicator animation, footer actions, and exact existing Framer Motion transition settings.

For mobile, preserve the dedicated mobile navigation, active-tab animation, sticky top bar, safe-area padding, touch-friendly controls, and route-specific shell exceptions. Ensure dialogs, dropdowns, floating buttons, and page content do not conflict with the bottom navigation.

For settings, reuse the current card tokens, responsive padding, section headings/dividers, labeled controls, selection tiles, and save/reset footer pattern. Keep persistence and success/error states truthful.

For Scops typography, preserve Inter for body/UI text, Manrope for headings, and Geist Mono for technical text. Keep existing font imports and CSS variables.

Do not invent new animation values or redesign unrelated screens. Check narrow mobile, tablet, and desktop widths, keyboard focus, and reduced-motion behavior. Report any existing bugs you discover separately instead of silently expanding scope.
```

## 5. Typography-only request
```text
Use the `scops-design-system` skill. Audit typography before making changes.

For Scops, preserve the current font system: Inter for body/UI text, Manrope for headings, and Geist Mono for monospace/technical details. Inspect `src/app/layout.tsx`, `src/app/globals.css`, and existing font utility usage before editing. Reuse existing CSS variables and semantic classes; do not load duplicate fonts or replace the font stack.

Improve hierarchy, sizing, weight, line height, wrapping, and responsive readability only as requested. Do not change layout, color tokens, animation, or unrelated components. Verify headings, body text, controls, tables, and mobile wrapping.
```

## 6. UI polish / quality audit
```text
Use the `scops-design-system` skill to audit the requested screens for polish without doing an automatic redesign.

Inspect visual hierarchy, typography consistency, spacing, cards/surfaces, form states, responsive behavior, sidebar/mobile navigation, motion consistency, accessibility, empty/loading/error/success states, and dead or misleading controls.

First return a prioritized list of findings grouped as critical, important, and polish. Do not change files until I approve the implementation scope. For each finding, cite the file/component and explain the user impact.
```

## 7. Add project-level agent guidance
If the repository has an `AGENTS.md` or equivalent agent instruction file, add a concise note like this:
```text
For UI work, use the `scops-design-system` skill when available. Inspect existing tokens, typography, components, responsive patterns, and motion before editing. Preserve existing functionality and exact animation timing/easing unless the user requests a change. Prefer small targeted changes, truthful interaction states, accessibility, and responsive verification. Do not claim tests or visual checks were performed unless they actually were.
```

## Recommended workflow
1. Use Prompt 6 to request an audit when you are unsure what needs improvement.
2. Review and approve the findings.
3. Use Prompt 3 or Prompt 4 for a scoped implementation.
4. Use Prompt 1 for ordinary future tasks and Prompt 2 for greenfield projects.
5. Ask the agent to report tests and visual checks honestly.
