---
name: scops-design-system
description: Applies Scops-inspired design principles to new UI builds and changes to landing pages, dashboards, forms, settings, responsive layouts, and interaction polish. Use during Antigravity builds to create premium, calm, consistent, accessible interfaces while preserving each repository's existing design tokens, components, responsiveness, and animation timing/easing.
---

# Scops Design System Skill

## Mission
Use Scops as the quality bar: premium, calm, intentional SaaS design with strong hierarchy, disciplined spacing, useful feedback, accessible controls, responsive layouts, and purposeful motion. This is a reusable design skill for future builds, not a command to copy Scops branding into every unrelated product. Adapt it to the current repository.

## Non-negotiable rules
1. Inspect before editing: identify framework, routes, global styles, tokens, fonts, spacing, radii, shadows, breakpoints, component library, icon package, animation system, and neighboring screens.
2. Extend, don't replace: reuse existing components and tokens. Do not create duplicate button/input/card systems or add a competing design system.
3. Make the smallest change that satisfies the request. Do not redesign unrelated pages, copy, routes, state, behavior, or layout.
4. Preserve established animation durations, delays, easing, stagger, scroll triggers, hover transitions, and reduced-motion behavior. Do not remove or replace Framer Motion or another existing motion system casually.
5. Never invent exact colors, font families, token values, breakpoints, shadows, or radii if the repository defines them. If absent, infer a small coherent set from existing UI and document the inference.
6. Build real states: loading, empty, error, success, disabled, focus, selected, pending, and permission-limited states where relevant. Do not fake functionality with static data in production paths.
7. Responsive by default: check narrow mobile, tablet, and desktop; prevent overflow, clipped dialogs, broken navigation, cramped controls, and unreadable tables.
8. Accessibility is part of polish: semantic HTML, logical headings, visible keyboard focus, labels, keyboard operation, contrast, accessible names, and reduced-motion support.
9. Respect architecture and security. UI changes must not bypass authorization, server validation, workspace isolation, or established API boundaries.
10. Finish the details: no dead buttons, unexplained badges, inconsistent icons, arbitrary spacing, placeholder copy, false success messages, or silent failures.

## Design character
- Premium, not flashy: restrained surfaces, confident typography, deliberate spacing, purposeful contrast, and limited accent use.
- Clear, not crowded: one dominant purpose per screen and a visible hierarchy.
- Calm and trustworthy: predictable controls, honest status labels, plain-language errors, and transparent consequences.
- Purposeful depth: cards, borders, dividers, elevation, and background variation should communicate grouping, not merely decorate.
- Consistent craft: buttons, inputs, menus, cards, badges, tables, dialogs, and toasts should feel like one system.
- Content-led: make information understandable before adding ornament.

## Required workflow

### 1. Reconnaissance
- Inspect the relevant screen and similar existing components.
- Find actual theme tokens, typography, spacing, breakpoints, icons, and animation conventions.
- Determine whether this is a new screen, an extension, a bug fix, or a targeted visual adjustment.
- Identify data-loading, validation, permission, empty/error, and test requirements.
- If a material decision cannot be inferred safely, ask a concise question. Otherwise proceed with reasonable assumptions.

### 2. Plan
Define the user's primary goal, main action, secondary actions, information hierarchy, reusable components/tokens, responsive behavior, meaningful states, motion, and accessibility needs. Align new work with neighboring screens; avoid isolated components that look polished but do not fit the product.

### 3. Implement
- Use shared components and design tokens first.
- Use the existing icon package; don't mix emoji, unrelated icon libraries, and handmade icons.
- Keep one clear primary action; make secondary actions quieter and destructive actions unmistakable.
- Use meaningful action labels, not vague “Click here” labels.
- Provide immediate pending/success/error feedback and prevent duplicate submissions.
- Design for long names, long emails, empty values, large numbers, and user-generated content.
- Avoid hard-coded mock data in production flows.
- Keep components understandable; don't over-abstract simple screens.
- Avoid adding dependencies unless the current stack cannot reasonably support the requirement.

### 4. Motion and interactions
Motion should communicate hierarchy, state change, continuity, or feedback—not delay the user.
- In existing projects preserve duration, easing, delay, stagger, trigger, and transition conventions.
- Do not introduce competing animation systems or remove existing motion without explicit approval.
- Avoid layout-shifting animations unless the current design intentionally uses them.
- Keep feedback immediate; avoid excessive bounce, elastic movement, parallax, and long entrance animations in productivity UI.
- Respect `prefers-reduced-motion` and existing accessibility patterns.
- In a new project without a motion system, use subtle, fast transitions and consistent motion tokens rather than arbitrary per-element values.

### 5. Verify
- Run available relevant lint, typecheck, tests, and build commands.
- Inspect the changed interface at mobile, tablet, and desktop widths.
- Check keyboard focus and keyboard operation for important controls.
- Exercise relevant loading, empty, error, success, disabled, and permission-denied states.
- Verify buttons, forms, dialogs, dropdowns, tabs, links, and navigation actually work.
- Check for new console/build warnings and regressions on neighboring screens.
- Do not claim a check passed unless it was run; do not claim visual verification without browser/screenshot inspection.

## Visual standards

### Layout and hierarchy
- Use a clear page title and concise supporting text when needed.
- Keep primary actions easy to find without making every action equally prominent.
- Use spacing and headings before adding extra cards.
- Maintain consistent content width, alignment, gutters, and vertical rhythm.
- Keep dense screens scannable with purposeful grouping and restrained labels.

### Typography
- Reuse the repository's fonts and type scale.
- Use size, weight, line height, and contrast to create hierarchy; don't bold everything.
- Keep body text readable and line lengths controlled.
- Avoid all-caps for long labels/body copy and avoid tiny low-contrast text for important information.
- Use tabular numerals for metrics/money only if consistent with the project's conventions.

### Surfaces, color, and themes
- Use cards when content forms a meaningful unit; avoid unnecessary nested cards.
- Use borders, shadows, radii, gradients, blur, glow, and glass effects only if the existing design language supports them.
- Read actual theme tokens before adding colors.
- Prefer semantic tokens (background, foreground, muted, border, primary, destructive, success, warning, info) where available.
- Never convey status by color alone; pair it with text, icon, shape, or accessible labeling.
- Check contrast and component boundaries in dark/light modes where supported.

### Forms
- Every input needs a label; a placeholder is not a label.
- Explain required fields and validation expectations.
- Place validation near the field and preserve input after recoverable errors.
- Show pending state and prevent accidental duplicate submissions.
- Make success and the next step clear.
- Use appropriate input types, autocomplete, and accessible descriptions.
- Do not disable submission without explaining why.

### Data-heavy screens
- Make status, owner/client, date, key metric, and next action scannable where relevant.
- Format dates, currency, counts, and empty values consistently.
- Use progressive disclosure instead of displaying every field at once.
- Reflow tables into a usable mobile alternative instead of shrinking them until unreadable.
- Distinguish live data from demo data; keep filters and sorting visible and reversible.

### Empty/loading/error states
- Empty states explain what is missing and provide a useful next action.
- Loading states preserve layout where practical to reduce layout shift.
- Errors explain what happened in plain language and how to recover.
- Success feedback is concise and must reflect confirmed success, not merely a click.
- Long-running operations need meaningful progress/status, not just an indefinite spinner.

### Responsive behavior
- Design small screens deliberately; don't simply shrink desktop.
- Use fluid widths and content-aware wrapping.
- Keep touch targets comfortable and separated.
- Ensure menus, dialogs, sidebars, navigation, and action bars work on touch devices.
- Avoid accidental horizontal overflow.
- Ensure sticky UI does not cover content or keyboard focus.
- Test long content, zoom, and intermediate widths when feasible.

## Scops-inspired product principles
These principles come from the Scops product context; apply them as general interaction lessons without forcing Scops-specific branding on unrelated products.
- Make the current state and source of truth visible.
- Separate facts from suggestions, drafts, pending actions, and approved decisions.
- Explain consequences before meaningful actions.
- Preserve history for important agreements and decisions; never silently overwrite significant state.
- Use respectful, human language rather than blame or intimidation.
- Keep users in control: suggestions can be reviewed, edited, accepted, or discarded.
- Make the next useful step visible in review queues, empty states, and pending states.
- Be honest about capabilities and outcomes; never imply something happened unless the system confirms it.

## AI UI rules
- Distinguish generated drafts from saved, approved, or sent content.
- Provide edit, regenerate, copy, discard, and confirmation actions as appropriate.
- Show relevant source context or reasons for classifications/recommendations.
- Do not style uncertain AI output as guaranteed truth.
- Require explicit confirmation before sending external communication or performing consequential mutations.
- Preserve user work after recoverable errors.
- Use status text that accurately describes what the system did.

## Technical and product boundaries
- Do not change authentication, authorization, billing, security rules, API contracts, or schemas as a side effect of visual work.
- Do not bypass server-side validation or permission checks to make an interaction appear functional.
- Never expose secrets in client-side code.
- Do not invent endpoints or fake unimplemented capabilities.
- If the design requires missing backend behavior, report the dependency rather than hiding it with mock UI.
- Avoid broad refactors during visual work unless required and authorized.
- The user's explicit design direction takes precedence over the default visual style, except for accessibility, security, and technical constraints.

## Definition of done
A task is complete only when the requested outcome is implemented, existing conventions are reused, responsive behavior and relevant states are covered, keyboard/accessibility basics are respected, motion and unrelated behavior are preserved, no dead controls or false success states remain in the changed path, relevant checks are run, and limitations are reported honestly.

## Required final report
Report:
1. Changed screens/components and visible behavior.
2. Existing tokens/components/patterns reused.
3. Responsive/accessibility checks performed.
4. Motion preserved or exact motion changes made and why.
5. Commands/tests actually run and their results.
6. Remaining issues or limitations.
Keep it concise and factual.


## Scops reference patterns: desktop sidebar, mobile shell, and settings cards

When working in the Scops repository, use the current implementation as the source of truth. These are patterns observed in the current codebase, not universal hard-coded rules for every future product. Before copying them, re-check the latest components and tokens.

### Desktop sidebar behavior
Reference component: `src/components/dashboard/Sidebar.tsx`.
- The sidebar is desktop-only (`hidden lg:flex`), sticky at the top, full viewport height, vertically structured, and clipped horizontally to prevent labels spilling during width changes.
- It uses a compact icon rail around 72px wide and expands to about 256px on hover. The current component derives its visible state from hover; inspect the latest implementation before changing interaction semantics.
- The brand mark changes from the compact “S” to “Scops” as the sidebar expands.
- Navigation icons stay in place while text labels fade in/out through Framer Motion `AnimatePresence`; labels must not wrap during the transition.
- The active route has a narrow primary-color marker using a shared `layoutId`, so movement between active items feels continuous rather than independently re-animating each marker.
- Navigation rows use compact, consistent spacing, rounded corners, and a muted default state with a soft accent hover/active surface.
- Footer actions (upgrade, feedback, settings, logout) share the same row geometry and icon alignment. The upgrade action is intentionally emphasized; logout gets a destructive hover treatment.
- Preserve the existing animation library and transition configuration. Do not add arbitrary duration/easing values, replace the active-marker layout animation, or alter the collapsed/expanded widths unless explicitly requested.
- Test pointer hover, pointer leave, keyboard focus, route changes, long labels, reduced motion, and whether the sidebar behaves sensibly on touch devices. Do not assume hover is available on mobile.

### Mobile dashboard shell and navigation
Reference components: `src/components/dashboard/MobileBottomNav.tsx`, `TopNav.tsx`, and `src/app/(dashboard)/layout.tsx`.
- Mobile uses a dedicated bottom tab bar instead of squeezing the desktop sidebar onto a narrow screen. The bar is fixed to the viewport bottom, uses a translucent background/backdrop blur, a subtle top border, and safe-area padding.
- The current bottom navigation presents four compact destinations (Home, Projects, Templates, Settings) with icon-over-label layout. Keep labels readable and consistent; avoid adding too many destinations or reducing touch targets to fit.
- The active tab uses a shared Framer Motion `layoutId` pill/highlight with the current spring settings (`stiffness: 400, damping: 30`). Preserve these exact settings unless the user explicitly asks to change the motion.
- The desktop sidebar is hidden below the large breakpoint, while the mobile bottom navigation is hidden at medium widths and above. Verify the current breakpoints in the actual code before modifying them.
- The top navigation is sticky and compact (currently 56px high), with a translucent background and backdrop blur. On mobile, search is icon-only and opens the existing command palette; desktop uses the wider search control and keyboard shortcut hint.
- Main content includes bottom safe-area/navigation padding on mobile so the bottom bar does not cover the final card, button, or form field. Preserve and verify the `pb-safe-nav` / safe-area utilities and any route-specific chrome exceptions.
- Ensure dialogs, sheets, dropdowns, toasts, FABs, and keyboard-open states do not collide with the fixed bottom bar. Test at narrow widths and with device safe areas.
- Some routes intentionally hide the standard shell. Preserve route-specific exceptions and do not force the bottom bar onto focused builder/new-project flows without checking intended behavior.

### Settings page and card design
Reference components: `src/app/(dashboard)/settings/workspace/page.tsx` and `settings/preferences/page.tsx`.
- Settings pages use a centered, full-width content column with a maximum width around `max-w-3xl`, consistent vertical page spacing, a clear title, and short supporting copy.
- The main settings surface uses the shared theme tokens: `bg-card`, `border-border/40`, `rounded-2xl`, and a restrained `shadow-sm`. Avoid inventing a separate visual treatment for each settings section.
- Card padding is responsive (currently `p-4 sm:p-8`); section groups use clear headings, generous but consistent spacing, and subtle dividers such as `border-border/40`.
- Theme choices use a responsive one-column-to-three-column grid, large clickable selection tiles, clear selected/unselected border states, and icons contained in restrained tinted circles. Keep selected state clear without relying on color alone.
- Forms use shared Label/Input/Select/Textarea components, labels above controls, and consistent vertical spacing. Destructive operations should use an explicit confirmation dialog.
- Save/reset actions are grouped in a footer area with a subtle muted surface and top border; the preferences screen currently uses a sticky footer. Check viewport height, keyboard focus, and small-screen wrapping so actions remain reachable without covering content.
- Use the actual project's dark/light semantic tokens. Do not hard-code the currently observed color values into components; update tokens only when explicitly asked to change the design system.
- Settings interactions must accurately reflect persistence. Do not use fake delayed saves or success toasts when a backend write has not completed successfully; report any mock/incomplete behavior instead of polishing it into a misleading flow.

### How to use these patterns in other projects
- Treat them as interaction and composition references, not a mandate to use the exact Scops dimensions in every application.
- First inspect the target repository's own navigation, responsive breakpoints, tokens, and motion implementation. Translate the principle—compact desktop rail, dedicated mobile navigation, coherent settings cards—into the target project's conventions.
- If a user asks to preserve a specific animation/layout, do not approximate it from memory. Read the source component and preserve the actual values and behavior.


## Typography: Scops font system

Verified in Scops `src/app/layout.tsx` and `src/app/globals.css`. When building Scops itself, preserve this exact system unless the user explicitly requests a change:
- **Inter** — primary body and UI font, loaded as `--font-inter` and mapped to Tailwind `--font-sans`.
- **Manrope** — headings/display font, loaded as `--font-manrope` and mapped to `--font-heading`.
- **Geist Mono** — monospace/technical font, loaded as `--font-geist-mono` and mapped to `--font-mono`.

### Typography rules
- Inspect the font loader and CSS mappings before changing typography.
- In Scops, reuse the existing `next/font/google` imports, CSS variables, and semantic font classes. Do not load duplicate fonts or introduce another font package.
- Use Manrope for headings, Inter for normal interface/body copy, and Geist Mono only for technical text or values that benefit from a monospace treatment.
- Keep hierarchy deliberate and readable; do not apply one font indiscriminately to every element.
- Do not replace these fonts with “similar” alternatives merely to simplify implementation.
- For unrelated future projects, treat this trio as a Scops-inspired reference, not a forced requirement. Inspect and preserve that repository's own font system unless the user explicitly asks to adopt Scops typography.
