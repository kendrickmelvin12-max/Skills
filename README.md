# Scops Design System — Antigravity Skill

A reusable Agent Skill for applying Scops-inspired design principles to future UI builds in Google Antigravity and compatible Agent Skills tools.

## Files
- `scops-design-system/SKILL.md` — core instructions and activation metadata.
- `scops-design-system/references/design-principles.md` — supplementary design and QA checklist.

## Install globally

Antigravity App / IDE global skill path:
`~/.gemini/config/skills/scops-design-system/`

Antigravity CLI global skill path:
`~/.gemini/antigravity-cli/skills/scops-design-system/`

To enable it for one repository, copy the `scops-design-system` folder to:
`.agents/skills/scops-design-system/`

Antigravity's documented workspace path is `.agents/skills/<skill-folder>/`; global paths vary by Antigravity surface. See the official guide:
https://antigravity.google/docs/skills?tab=ide

## Use
The agent may activate the skill automatically when relevant. You can also explicitly ask:
“Use the `scops-design-system` skill. Inspect the existing design system first, preserve components and animation timing/easing, make only the requested changes, and verify responsive behavior, accessibility basics, and relevant checks.”

## Important
The skill intentionally does not hard-code brand tokens. It tells the agent to inspect each repository and reuse its actual tokens/components instead of inventing colors, fonts, spacing, or motion values.


## Typography and reusable prompts

The Scops font roles are **Inter** for body/UI, **Manrope** for headings, and **Geist Mono** for technical text. The skill documents how to preserve those roles and the existing desktop sidebar animation, mobile navigation/layout, and settings-card patterns.

Copy/paste Antigravity prompts are collected in [scops-design-system/PROMPTS.md](scops-design-system/PROMPTS.md), including prompts for ordinary builds, greenfield projects, scoped UI changes, sidebar/mobile/settings work, typography-only changes, and an audit-first polish review.
