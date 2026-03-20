# BH-hatstand — Agent Instructions

## Project Overview

BH-hatstand is a specification-first repository for a banking organisation. It contains structured markdown specifications (epics, features, stories, architecture decisions, designs) — NOT source code. All specifications use YAML frontmatter for metadata.

## Build & Test

This repository has no build or test commands. Validation is done through pull request review and (planned) CI linting.

## Project Structure

```
BH-hatstand/
├── architecture/          # Bank-wide architecture (ADRs, BDRs, C4 diagrams, standards)
├── domains/               # 23 business domains, each with epics/features/stories
├── knowledge/             # Glossary, personas, customer segments
├── templates/             # Templates for all artefact types
├── CLAUDE.md              # Claude-specific agent instructions
├── AGENTS.md              # This file
└── README.md              # Full framework documentation
```

## Code Style

- All specifications are markdown with YAML frontmatter
- Slugs: lowercase, hyphen-separated (e.g., `mobile-document-upload`)
- ADR/BDR numbering: three-digit zero-padded (`adr-001-slug.md`)
- Status values: draft, review, approved, implemented, deprecated

## Key Conventions

1. **Use templates** from `templates/` when creating new files
2. **Never edit** `jira_key` or `jira_status` fields in frontmatter
3. **No binary files** — .docx, .pptx, .xlsx must be converted to markdown/YAML
4. **Flat domain structure** — domains are never nested
5. **Declare dependencies** in frontmatter using relative file paths

## Boundaries

- Do not create source code files in this repository
- Do not modify the top-level directory structure
- Do not rename domain folders without updating all references
- Do not reuse ADR/BDR numbers

## References

See `README.md` for complete documentation including frontmatter schemas, lifecycle, and governance workflow.
