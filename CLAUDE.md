# BH-hatstand — Claude Code Instructions

You are working in the **BH-hatstand** specification repository, part of the **BlueHat AI Method**. This repository contains structured markdown specifications for a banking organisation — NOT source code. Your role is to help author, review, and maintain specifications.

## Repository Purpose

BH-hatstand is a spec-first repository where markdown files are the single source of truth for product requirements, architecture decisions, and design documents across 23 banking domains.

## Critical Rules

1. **Never edit `jira_key` or `jira_status` frontmatter fields** — these are managed by automated Jira sync
2. **Never commit binary office files** (.docx, .pptx, .xlsx) — convert to markdown or YAML first
3. **Never nest domains** — all domains are flat peers under `domains/`
4. **Always use templates** from `templates/` when creating new artefacts
5. **Always include required frontmatter fields** — see README.md section 8 for schemas
6. **Use slugs for identity** — lowercase, hyphen-separated, no special characters
7. **Set status to `draft`** for all new artefacts

## File Placement Rules

| Artefact | Location |
|---|---|
| Epic | `domains/{domain}/epics/{epic-slug}/epic.md` |
| Feature | `domains/{domain}/epics/{epic-slug}/features/{feature-slug}/feature.md` |
| Story | `domains/{domain}/epics/{epic-slug}/features/{feature-slug}/stories/{story-slug}.md` |
| Domain ADR | `domains/{domain}/architecture/adrs/adr-{NNN}-{slug}.md` |
| Bank-wide ADR | `architecture/adrs/adr-{NNN}-{slug}.md` |
| Domain BDR | `domains/{domain}/architecture/bdrs/bdr-{NNN}-{slug}.md` |
| Bank-wide BDR | `architecture/bdrs/bdr-{NNN}-{slug}.md` |
| HLD | `domains/{domain}/architecture/hlds/hld-{slug}.md` |
| LLD | `domains/{domain}/architecture/llds/lld-{slug}.md` |
| API Spec | `domains/{domain}/architecture/api-specs/{service-name}.yaml` |
| Blueprint | `domains/{domain}/blueprints/{slug}.md` |

## Allowed File Types

- `.md` — specs, docs, ADRs, READMEs
- `.yaml`, `.yml`, `.json` — API specs, schemas
- `.png`, `.jpg`, `.svg`, `.gif` — diagrams only

## Frontmatter Requirements

Every `.md` specification file must have YAML frontmatter with at minimum:
- `title` (string)
- `slug` (string, matching the file/folder name)
- `status` (one of: draft, review, approved, implemented, deprecated)
- `created` (date in YYYY-MM-DD format)

See `README.md` section 8 for full schemas per artefact type.

## Naming Conventions

- Slugs: `lowercase-hyphen-separated`
- ADRs/BDRs: `adr-001-slug-name.md` (three-digit zero-padded, sequential, never reused)
- Epics and features use `epic.md` and `feature.md` as filenames (identity is in the parent folder slug)
- Stories use `{story-slug}.md` as filenames

## When Creating New Artefacts

1. Copy the appropriate template from `templates/`
2. Place it in the correct directory per the file placement rules above
3. Create any necessary parent directories
4. Fill in all required frontmatter fields
5. Leave `jira_key` and `jira_status` as `null`
6. Write substantive content — do not leave template placeholder text

## Domain Context

Before working in a domain, read:
1. The domain's `README.md` for boundaries, stakeholders, and regulatory context
2. Existing epics/features to understand current scope
3. `knowledge/glossary.md` for standard terminology
4. `knowledge/personas/` for user archetypes

## Cross-Domain Work

If your work spans multiple domains, check for dependencies and declare them in frontmatter:
```yaml
dependencies:
  - domains/payments/epics/real-time-payments/epic.md
```
