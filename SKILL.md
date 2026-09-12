---
name: markdown-web-builder
description: Use when a user asks to generate a new webpage and wants an existing design style, architecture approach, or UI language reused through editable Markdown.
---

# Markdown Web Builder

## Role

This Skill is the router for webpage generation. It selects a style web-prompt, confirms the choice with the user, inspects the target project's architecture, and coordinates code plus page Markdown generation.

## Execution

1. Confirm the requested page style with the user.
2. Select and read the matching file in `references/web-prompts/`.
3. Inspect the target project's framework, build tool, component library, and existing Markdown.
4. Decide whether the page is new or should reuse an existing architecture.
5. For a new page, create program code and page Markdown together in the target project.
6. For an existing project, reuse and adjust its Markdown first; change code only when the existing renderer lacks a required capability.
7. Run the target project's renderer and self-checks.

## Boundaries

- Web-prompts describe reusable design, architecture, UI, interaction, and responsive principles; they do not define fixed page sections.
- Page Markdown and program code belong to the target project, never to this Skill's output directory.
- Do not assume React, Vue, HTML, Ant Design, or another fixed framework.
- When code adds a configurable capability, update the Markdown specification or example in the same change.

## References

- `references/markdown-driven-web-prompt.md` — code and page Markdown collaboration rules.
- `references/web-prompts/` — selectable page style templates.
- `references/markdown-spec.md` — page Markdown boundaries.
- `references/workflow.md` — generation sequence.
- `references/self-checklist.md` — verification checklist.

