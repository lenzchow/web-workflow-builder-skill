---
name: markdown-web-builder
description: Use when a user asks to generate a new webpage and wants an existing design style, architecture approach, or UI language reused through editable Markdown.
---

# Markdown Web Builder

## Role

This Skill is the router for webpage generation. It selects a style web-prompt, confirms the choice with the user, inspects the target project's architecture, and coordinates code plus page Markdown generation.

## Modes

### Mode 1: Generate a webpage

1. Confirm the requested page style with the user.
2. Select and read the matching file in `references/web-prompts/`.
3. Inspect the target project's framework, build tool, component library, and existing Markdown.
4. Decide whether the page is new or should reuse an existing architecture.
5. For a new page, create program code and page Markdown together in the target project.
6. For an existing project, reuse and adjust its Markdown first; change code only when the existing renderer lacks a required capability.
7. Run the target project's renderer and self-checks.

### Mode 2: Evolve a web-prompt

Use this mode only when the user asks to preserve the style of a completed webpage or to update a reusable web-prompt.

1. Inspect the completed target project, including its code, page Markdown, screenshots, and design decisions.
2. Separate reusable design principles from page-specific content, fields, copy, sections, and business logic.
3. Decide whether the result is a small update to an existing web-prompt or a genuinely new style.
4. Present the proposed changes to the user; do not overwrite a web-prompt before approval.
5. After approval, update the existing file or create `references/web-prompts/<style-name>.md`.
6. Run the web-prompt self-check and record the change in the repository history.

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
- Do not automatically promote every page-level adjustment into a web-prompt.
- Mode 2 may update `references/web-prompts/`, but it must not modify `SKILL.md` unless the workflow itself changes.

## References

- `references/markdown-driven-web-prompt.md` — code and page Markdown collaboration rules.
- `references/web-prompts/` — selectable page style templates.
- `references/markdown-spec.md` — page Markdown boundaries.
- `references/workflow.md` — generation sequence.
- `references/self-checklist.md` — verification checklist.
