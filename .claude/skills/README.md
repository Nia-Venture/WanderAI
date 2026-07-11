# Claude Code Agent Skills

This directory contains Agent Skills, installed so that Claude Code can use
them automatically when a task matches a skill's description.

Each subdirectory is a self-contained skill with a `SKILL.md` (the instructions
Claude reads) plus any supporting scripts, references, and templates.

## Installed skills

| Skill | Purpose |
| --- | --- |
| `docx` | Create, read, and edit Microsoft Word (`.docx`) documents. |
| `pdf` | Read, create, merge/split, fill forms, watermark, OCR, and otherwise manipulate PDFs. |
| `pptx` | Create and edit PowerPoint (`.pptx`) presentations. |
| `xlsx` | Create, read, and edit Excel (`.xlsx`) spreadsheets. |
| `pdf-reading` | Lightweight text/table extraction from PDF files. |
| `file-reading` | Read and extract content from a variety of file formats. |
| `frontend-design` | Guidance for building polished front-end / UI designs. |
| `product-self-knowledge` | Reference knowledge about Claude and Anthropic products. |
| `ui-ux-pro-max` | UI/UX design intelligence: styles, color palettes, font pairings, and UX guidelines across common front-end stacks. |

## How skills are used

Claude Code discovers these automatically. When a request matches a skill's
`description` frontmatter (for example, "turn this into a PowerPoint" →
`pptx`), the skill's instructions are loaded and followed. No manual invocation
is required.

## Source & license

Most skills here come from Anthropic's official skills collection
(<https://github.com/anthropics/skills>). Each skill keeps its own
`LICENSE.txt`; refer to those files for the exact terms.

`ui-ux-pro-max` comes from a third-party collection
(<https://github.com/nextlevelbuilder/ui-ux-pro-max-skill>, MIT licensed)
rather than Anthropic's official skills repo.

## Updating

Re-copy the desired skill directory from the upstream source to update it.
Keep the directory layout (`<skill-name>/SKILL.md`) intact so Claude Code can
continue to discover the skill.
