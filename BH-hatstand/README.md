# BH-hatstand — AI-First Specification Framework for Banking

> *Part of the BlueHat AI Method*

**BH-hatstand** is a specification-first repository structure that turns markdown files into the single source of truth for a banking organisation's entire product development lifecycle. AI agents read these specifications to generate implementation artefacts; humans author, review, and approve the specifications.

The name reflects the methodology: every "hat" you wear in the development lifecycle — architect, product owner, developer, tester — is augmented by AI. The specifications in this repository are the shared language between human intent and AI execution.

---

## Table of Contents

- [1. What is BH-hatstand?](#1-what-is-bh-hatstand)
- [2. Why Spec-Driven, AI-First Development?](#2-why-spec-driven-ai-first-development)
- [3. Core Principles](#3-core-principles)
- [4. Repository Structure](#4-repository-structure)
- [5. Domain Catalogue](#5-domain-catalogue)
- [6. Domain Folder Anatomy](#6-domain-folder-anatomy)
- [7. Work Item Hierarchy](#7-work-item-hierarchy)
- [8. Specification Frontmatter Standard](#8-specification-frontmatter-standard)
- [9. Ownership Model — Git vs Jira](#9-ownership-model--git-vs-jira)
- [10. Jira Sync Protocol](#10-jira-sync-protocol)
- [11. Allowed File Types](#11-allowed-file-types)
- [12. Naming Conventions](#12-naming-conventions)
- [13. Architecture Artefacts](#13-architecture-artefacts)
- [14. AI Agent Integration](#14-ai-agent-integration)
- [15. Sample AI Prompts](#15-sample-ai-prompts)
- [16. Lifecycle — Idea to Implementation](#16-lifecycle--idea-to-implementation)
- [17. Cross-Domain Dependencies](#17-cross-domain-dependencies)
- [18. Governance and Review Workflow](#18-governance-and-review-workflow)
- [19. Templates Reference](#19-templates-reference)
- [20. Getting Started](#20-getting-started)
- [21. Gaps and Recommended Improvements](#21-gaps-and-recommended-improvements)

---

## 1. What is BH-hatstand?

BH-hatstand is the specification layer of the **BlueHat AI Method** — an AI-first development methodology designed for regulated industries such as banking and financial services.

Instead of writing code first and documenting later, BH-hatstand inverts the process:

1. **Humans write structured specifications** in markdown (epics, features, stories, architecture decisions)
2. **AI agents consume those specifications** to generate implementation artefacts (code, tests, API contracts, deployment configs)
3. **Humans review and approve** both the specifications and the generated output

This approach draws from several emerging industry practices:

| Methodology | Key Idea | How BH-hatstand Applies It |
|---|---|---|
| **Spec-Driven Development** (GitHub, Thoughtworks) | Write specs before code; specs are the source of truth | Epic → Feature → Story hierarchy with YAML frontmatter |
| **Intent-Driven Development** (KodeNerds) | Specification quality determines output quality | Structured templates with required fields enforce clarity |
| **BMAD-METHOD** (Open Source) | Agent-as-Code personas in markdown | CLAUDE.md and AGENTS.md provide agent-readable conventions |
| **AGENTS.md Standard** (Linux Foundation) | Markdown as governance layer for AI agents | Repository structure is machine-readable communication |
| **AI-Native SDLC** (ArXiv, AWS) | Four-stage cycle: Prompt → Orchestrate → Review → Deploy | Lifecycle section maps directly to this model |

---

## 2. Why Spec-Driven, AI-First Development?

### The quality of AI output is bounded by specification quality

AI agents cannot infer business intent from vague descriptions. A well-structured specification with clear acceptance criteria, scope boundaries, and dependency declarations produces dramatically better output than a conversational prompt.

### Banking demands traceability

Regulated industries require audit trails for every decision and requirement. By storing specifications in Git:

- Every change is tracked with author, timestamp, and diff
- Pull request reviews create an approval record
- Architecture Decision Records (ADRs) capture the "why" behind technical choices
- Jira integration provides workflow traceability without duplicating content

### Markdown is the universal interface

- **For humans**: readable, reviewable, writable without special tools
- **For AI agents**: parseable, structured (via YAML frontmatter), navigable via file paths
- **For Git**: diffable, mergeable, lightweight
- **For CI/CD**: lintable, validatable, automatable

### Reduced team sizes, higher consistency

Research on Intent-Driven Development reports complex projects delivered with approximately 30% of traditional team sizes. The constraint is specification quality, not headcount.

---

## 3. Core Principles

1. **Specification before implementation** — No code is written until a spec exists and is approved
2. **Markdown is the interface** — Between humans and AI; between requirements and implementation
3. **Git owns requirements; Jira owns workflow** — Content lives in Git, planning lives in Jira
4. **Flat domain structure** — Domains are peers, never nested within each other
5. **Slugs are identity** — Folder and file names are the canonical identifier (not Jira keys)
6. **AI agents are first-class consumers** — Repository structure, naming, and frontmatter are designed for machine readability
7. **Allowed file types only** — No binary office documents; everything must be diffable and AI-parseable
8. **Architecture decisions are immutable** — Once accepted, ADRs are appended to, never edited (supersede with a new ADR)

---

## 4. Repository Structure

```
BH-hatstand/
├── architecture/                  # Bank-wide architecture
│   ├── c4/
│   │   └── containers/            # C4 model system/container diagrams
│   ├── adrs/                      # Architecture Decision Records (bank-wide)
│   ├── bdrs/                      # Business Decision Records
│   └── standards/                 # API standards, security patterns, coding guidelines
│
├── domains/                       # Flat domain folders (23 domains)
│   ├── onboarding/
│   ├── account-servicing/
│   ├── lending/
│   ├── cards/
│   ├── payments/
│   ├── credit-decisioning/
│   ├── relationship-management/
│   ├── beyond-banking/
│   ├── enabling-functions/
│   ├── platform-engineering/
│   └── ... (23 total)
│
├── knowledge/                     # Shared reference material
│   ├── glossary.md                # Standard terminology
│   ├── personas/                  # User archetypes
│   └── customer-segments/         # SME, Commercial, Corporate clusters
│
├── templates/                     # Templates for all artefact types
│   ├── epic.md
│   ├── feature.md
│   ├── story.md
│   ├── adr.md
│   ├── bdr.md
│   ├── hld.md
│   ├── lld.md
│   ├── domain-readme.md
│   └── api-spec.yaml
│
├── CLAUDE.md                      # AI agent instructions (Claude Code)
├── AGENTS.md                      # AI agent instructions (cross-platform)
└── README.md                      # This file
```

### Top-Level Directories

| Directory | Purpose | Scope |
|---|---|---|
| `architecture/` | Bank-wide architectural artefacts shared across all domains | Organisation |
| `domains/` | One folder per business domain containing all specs for that domain | Domain |
| `knowledge/` | Reference material consumed by both humans and AI agents | Organisation |
| `templates/` | Starter templates for every artefact type | Organisation |

---

## 5. Domain Catalogue

| # | Domain Slug | Description |
|---|---|---|
| 1 | `onboarding` | Customer onboarding, KYC, identity verification |
| 2 | `account-servicing` | Account lifecycle management, statements, alerts |
| 3 | `lending` | Loan origination, management, collections |
| 4 | `cards` | Credit and debit card products, issuing, disputes |
| 5 | `payments` | Payment processing, transfers, standing orders |
| 6 | `credit-decisioning` | Credit risk assessment, scoring, decisioning engines |
| 7 | `relationship-management` | Customer relationship tracking, CRM integration |
| 8 | `beyond-banking` | Non-traditional banking services, marketplace, lifestyle |
| 9 | `enabling-functions` | Shared internal capabilities (notifications, document generation) |
| 10 | `platform-engineering` | Infrastructure, CI/CD, observability, platform services |
| 11 | `realtime-subledger` | Core accounting engine — real-time double-entry ledger and balance management |
| 12-23 | *To be defined* | Remaining domains to be added based on organisational structure |

### Adding a New Domain

1. Create the folder: `domains/{domain-slug}/`
2. Copy `templates/domain-readme.md` to `domains/{domain-slug}/README.md` and fill it in
3. Create the subdirectory structure (see [Domain Folder Anatomy](#6-domain-folder-anatomy))
4. Add the domain to this catalogue table
5. Open a PR for review

---

## 6. Domain Folder Anatomy

Every domain follows an identical internal structure:

```
domains/{domain}/
├── README.md                          # Domain overview, ownership, key contacts
├── epics/
│   └── {epic-slug}/
│       ├── epic.md                    # Epic specification
│       └── features/
│           └── {feature-slug}/
│               ├── feature.md         # Feature specification
│               └── stories/
│                   └── {story-slug}.md  # User story
├── blueprints/                        # Solution designs spanning multiple epics
├── architecture/
│   ├── adrs/                          # Domain-scoped Architecture Decision Records
│   ├── bdrs/                          # Domain-scoped Business Decision Records
│   ├── hlds/                          # High-Level Design documents
│   ├── llds/                          # Low-Level Design documents
│   └── api-specs/                     # OpenAPI 3.x specifications
└── knowledge/                         # Domain-specific reference material
```

### Subdirectory Purposes

| Directory | Contains | When to Use |
|---|---|---|
| `epics/` | Epic → Feature → Story hierarchy | All product work items |
| `blueprints/` | Solution designs that span multiple epics | Cross-cutting concerns within the domain |
| `architecture/adrs/` | Architecture decisions scoped to this domain | When a technical choice affects only this domain |
| `architecture/bdrs/` | Business decisions scoped to this domain | When a business/product choice affects only this domain |
| `architecture/hlds/` | High-level designs | System context, component diagrams, data flows |
| `architecture/llds/` | Low-level designs | Class/module structure, sequence diagrams, data models |
| `architecture/api-specs/` | OpenAPI specifications | API contracts for services in this domain |
| `knowledge/` | Domain-specific reference material | Regulatory requirements, vendor docs, domain glossary extensions |

---

## 7. Work Item Hierarchy

```
Epic
└── Feature
    └── Story
```

### Path Convention

```
domains/{domain}/epics/{epic-slug}/epic.md
domains/{domain}/epics/{epic-slug}/features/{feature-slug}/feature.md
domains/{domain}/epics/{epic-slug}/features/{feature-slug}/stories/{story-slug}.md
```

### Level Definitions

| Level | Purpose | Typical Size | Example |
|---|---|---|---|
| **Epic** | A large body of work that delivers a business outcome | Weeks to months | `customer-onboarding` |
| **Feature** | A distinct capability within an epic | Days to weeks | `mobile-document-upload` |
| **Story** | A single implementable unit of work | Hours to days | `capture-id-photo` |

### Identity Rule

The **slug** (folder/file name) is the canonical identifier. Jira keys (e.g., `BANK-123`) are stored in frontmatter but never used as file or folder names. This ensures specifications remain meaningful and navigable without access to Jira.

---

## 8. Specification Frontmatter Standard

Every specification file uses YAML frontmatter. Fields marked with `*` are required.

### Epic Frontmatter

```yaml
---
title: "Customer Onboarding" *
slug: customer-onboarding *
domain: onboarding *
status: draft *                    # draft | review | approved | implemented | deprecated
jira_key: null                     # Populated by Jira sync — never edit manually
jira_status: null                  # Populated by Jira sync — never edit manually
owner: "@handle" *
created: 2026-03-20 *
updated: 2026-03-20 *
dependencies: []                   # Paths to dependent artefacts
tags: []
---
```

### Feature Frontmatter

```yaml
---
title: "Mobile Document Upload" *
slug: mobile-document-upload *
domain: onboarding *
epic: customer-onboarding *        # Parent epic slug
status: draft *
jira_key: null
jira_status: null
owner: "@handle" *
created: 2026-03-20 *
updated: 2026-03-20 *
dependencies: []
tags: []
---
```

### Story Frontmatter

```yaml
---
title: "Capture ID Photo" *
slug: capture-id-photo *
domain: onboarding *
epic: customer-onboarding *
feature: mobile-document-upload *  # Parent feature slug
status: draft *
jira_key: null
jira_status: null
owner: "@handle" *
created: 2026-03-20 *
updated: 2026-03-20 *
acceptance_criteria: [] *          # List of testable criteria
dependencies: []
tags: []
---
```

### Status Lifecycle

```
draft → review → approved → implemented → deprecated
```

- **draft**: Initial authoring, not yet ready for review
- **review**: Submitted via PR for team review
- **approved**: Accepted by reviewers, ready for implementation
- **implemented**: Code has been written and verified
- **deprecated**: Superseded or no longer relevant

---

## 9. Ownership Model — Git vs Jira

| Aspect | Git Owns | Jira Owns |
|---|---|---|
| **Requirements** | Title, acceptance criteria, scope, dependencies | — |
| **Planning** | — | Priority, PI, iteration, sprint |
| **Workflow** | — | Status, assignee, points |
| **Identity** | Slug (folder/file name) | Key (BANK-123) |

### Why This Split?

- **Git** is the system of record for **what** needs to be built. Specifications are version-controlled, diffable, and reviewable through pull requests.
- **Jira** is the system of record for **when and who**. Sprint planning, priority, and assignment are inherently mutable and temporal — they belong in a project management tool, not in versioned files.

This prevents the common problem of duplicated, divergent sources of truth. The specification content lives in one place (Git); the workflow metadata lives in another (Jira).

---

## 10. Jira Sync Protocol

### Sync Fields

Two frontmatter fields are managed exclusively by the sync process:

```yaml
jira_key: null       # e.g., BANK-123 — written by sync, never by hand
jira_status: null    # e.g., "In Progress" — written by sync, never by hand
```

### Sync Direction

| Direction | What Syncs |
|---|---|
| **Git → Jira** | Title, acceptance criteria, scope, dependencies |
| **Jira → Git** | `jira_key`, `jira_status` only |

### Rules

1. Never manually edit `jira_key` or `jira_status` in frontmatter
2. Leave both fields as `null` when creating new specs — sync will populate them
3. The sync process runs on merge to the main branch (not on every commit)
4. Sync tooling is a roadmap item — see [Gaps](#21-gaps-and-recommended-improvements)

---

## 11. Allowed File Types

| Allowed | Extensions | Use For |
|---|---|---|
| Yes | `.md` | All specs, docs, ADRs, READMEs |
| Yes | `.yaml`, `.yml`, `.json` | API specs, schemas, configuration |
| Yes | `.png`, `.jpg`, `.svg`, `.gif` | Diagrams, screenshots, wireframes |
| No | `.txt`, `.xlsx`, `.csv` | Convert to markdown or YAML before committing |
| No | `.docx`, `.pptx` | Convert to markdown before committing |

### Rationale

- **Markdown and YAML** are natively parseable by AI agents, diffable in Git, and readable by humans
- **Images** are necessary for diagrams but should be accompanied by text descriptions for AI consumption
- **Binary office formats** are not diffable, not AI-parseable, and create merge conflicts

---

## 12. Naming Conventions

### Slugs

- Lowercase, hyphen-separated, no special characters
- Descriptive and human-readable
- Examples: `mobile-document-upload`, `real-time-payments`, `customer-onboarding`

### File Names

| Artefact | Pattern | Example |
|---|---|---|
| Epic | `epic.md` (always this name) | `epics/customer-onboarding/epic.md` |
| Feature | `feature.md` (always this name) | `features/mobile-document-upload/feature.md` |
| Story | `{story-slug}.md` | `stories/capture-id-photo.md` |
| ADR | `adr-{NNN}-{slug}.md` | `adr-001-use-event-sourcing.md` |
| BDR | `bdr-{NNN}-{slug}.md` | `bdr-001-offer-premium-tier.md` |
| HLD | `hld-{slug}.md` | `hld-payment-gateway.md` |
| LLD | `lld-{slug}.md` | `lld-payment-gateway-api.md` |
| API Spec | `{service-name}.yaml` | `payment-service.yaml` |

### Numbering

ADRs and BDRs use three-digit zero-padded sequential numbers (`001`, `002`, `003`). Numbers are never reused, even if a record is deprecated.

---

## 13. Architecture Artefacts

### ADR — Architecture Decision Record

Format follows the [Michael Nygard style](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions):

```markdown
---
title: "Use Event Sourcing for Payment Audit Trail"
slug: use-event-sourcing
number: 1
status: accepted              # proposed | accepted | deprecated | superseded
domain: payments              # or "bank-wide" for architecture/adrs/
created: 2026-03-20
superseded_by: null            # slug of replacing ADR, if any
---

## Context

What is the issue that we're seeing that is motivating this decision?

## Decision

What is the change that we're proposing and/or doing?

## Consequences

What becomes easier or more difficult to do because of this change?
```

### BDR — Business Decision Record

Same structure as ADR but for business and product decisions:

```markdown
---
title: "Offer Premium Tier for SME Customers"
slug: offer-premium-tier
number: 1
status: accepted
domain: account-servicing
created: 2026-03-20
superseded_by: null
---

## Context
## Decision
## Consequences
```

### HLD — High-Level Design

```markdown
---
title: "Payment Gateway High-Level Design"
slug: payment-gateway
domain: payments
status: draft
created: 2026-03-20
updated: 2026-03-20
---

## System Context
## Component Diagram
## Data Flow
## Integration Points
## Non-Functional Requirements
## Open Questions
```

### LLD — Low-Level Design

```markdown
---
title: "Payment Gateway API Low-Level Design"
slug: payment-gateway-api
domain: payments
status: draft
created: 2026-03-20
updated: 2026-03-20
related_hld: payment-gateway
---

## Module Structure
## Sequence Diagrams
## Data Models
## Error Handling
## API Contracts
## Security Considerations
```

### API Specifications

Use OpenAPI 3.x format in YAML. Place in `architecture/api-specs/` (domain-level) or `architecture/standards/` (bank-wide).

---

## 14. AI Agent Integration

### CLAUDE.md

Located at the repository root (`BH-hatstand/CLAUDE.md`), this file instructs Claude Code on:

- Repository purpose and structure
- File placement rules (which artefacts go where)
- Frontmatter requirements (required fields, allowed values)
- Naming conventions (slug format, numbering rules)
- Domain boundaries (what belongs in which domain)
- What never to do (edit jira_key, commit binary files, nest domains)

Claude Code loads this file automatically at the start of every session.

### AGENTS.md

Located at the repository root (`BH-hatstand/AGENTS.md`), this file provides equivalent guidance for other AI tools (GitHub Copilot, Cursor, Windsurf, etc.) following the [AGENTS.md standard](https://agents.md/).

### Per-Domain Context

Each domain's `README.md` provides domain-specific context that AI agents use when working within that domain. This includes:

- Domain purpose and boundaries
- Key stakeholders and contacts
- Regulatory constraints
- Related domains and integration points

### How AI Agents Navigate This Repository

1. **Start with** `CLAUDE.md` or `AGENTS.md` for conventions
2. **Read** `README.md` (this file) for structure overview
3. **Navigate to** the target domain's `README.md` for domain context
4. **Read** the relevant epic/feature/story for requirements
5. **Check** `architecture/` for constraints and decisions
6. **Reference** `knowledge/` for terminology and personas
7. **Use** `templates/` when creating new artefacts

---

## 15. Sample AI Prompts

Open your AI assistant (GitHub Copilot, Claude Code, Cursor) and use prompts like these:

### Create a Feature

> Create a feature for mobile document upload in the onboarding domain. Customers should be able to photograph ID documents and upload them during onboarding. Part of the customer-onboarding epic.

### Create a New Epic

> Create a new epic called "real-time-payments" in the payments domain. The epic should cover instant payment processing for domestic transfers with real-time confirmation.

### Write an ADR

> Write an architecture decision record for the payments domain recommending event sourcing for the payment audit trail. The main alternative considered was traditional CRUD with audit tables.

### Break a Feature into Stories

> Read the feature spec at domains/onboarding/epics/customer-onboarding/features/mobile-document-upload/feature.md and break it into implementable user stories with acceptance criteria.

### Generate an API Spec

> Based on the feature spec at domains/payments/epics/real-time-payments/features/instant-transfer/feature.md, generate an OpenAPI 3.x specification for the transfer service API.

### Review a Spec for Completeness

> Review the epic at domains/lending/epics/loan-origination/epic.md against the epic template. Identify any missing required fields, unclear acceptance criteria, or undeclared dependencies.

### Create a Domain README

> Using the domain-readme template, create a README for the credit-decisioning domain. It covers credit risk assessment, scoring models, and automated decisioning engines.

### Identify Cross-Domain Dependencies

> Analyse the onboarding domain's epics and identify all dependencies on other domains. List them with the specific artefact paths.

---

## 16. Lifecycle — Idea to Implementation

```
1. Ideation          Business stakeholder describes intent
       ↓
2. Epic Creation     Architect/PO creates epic.md in the appropriate domain
       ↓
3. Feature           AI or architect decomposes epic into features
   Decomposition
       ↓
4. Story             AI generates stories from feature specs
   Generation        with acceptance criteria
       ↓
5. Architecture      HLD/LLD/ADR artefacts created as needed
       ↓
6. Review            Human review of specs via pull request
       ↓
7. Jira Sync         Approved specs sync to Jira for sprint planning
       ↓
8. Implementation    AI agents read specs to generate code
                     (in separate implementation repositories)
       ↓
9. Validation        Tests and acceptance criteria verified
       ↓
10. Closure          Status updated to "implemented"
```

### Key Points

- **Steps 1-6 happen in this repository** (BH-hatstand)
- **Step 8 happens in implementation repositories** — BH-hatstand is specs only, not code
- **AI agents participate in steps 2-5** as generators and in **step 8** as implementers
- **Humans are reviewers at step 6** and validators at **step 9**
- The lifecycle is not strictly linear — steps 3-5 often iterate

---

## 17. Cross-Domain Dependencies

Dependencies between domains are declared in frontmatter:

```yaml
dependencies:
  - domains/payments/epics/real-time-payments/epic.md
  - architecture/adrs/adr-003-event-bus.md
```

### Rules

1. Dependencies reference artefacts by their **file path** relative to the BH-hatstand root
2. A dependency means "this artefact cannot be fully implemented without the referenced artefact"
3. Circular dependencies should be flagged and resolved (usually by extracting shared concerns to `architecture/` or `enabling-functions`)
4. CI validation should check that all dependency paths resolve to existing files

---

## 18. Governance and Review Workflow

### Pull Request Process

All specification changes go through pull requests:

1. **Author** creates or modifies specs on a feature branch
2. **PR** is opened with a description of what changed and why
3. **Reviewers** are automatically assigned via CODEOWNERS
4. **Review** checks: completeness, consistency, frontmatter validity, naming conventions
5. **Merge** to main triggers Jira sync

### Required Reviewers

| Artefact Type | Required Reviewers |
|---|---|
| Epic | Domain lead + Product owner |
| Feature | Domain lead |
| Story | Domain lead or delegate |
| ADR (domain) | Domain lead + Architecture representative |
| ADR (bank-wide) | Architecture guild (2+ approvals) |
| BDR | Domain lead + Business stakeholder |
| HLD/LLD | Domain lead + Architecture representative |
| API Spec | Domain lead + API standards team |

### CODEOWNERS

A `CODEOWNERS` file at the repository root maps domain folders to responsible teams:

```
# Domain ownership
domains/onboarding/       @team-onboarding
domains/payments/         @team-payments
domains/lending/          @team-lending
# ... etc

# Bank-wide architecture requires architecture guild review
architecture/             @architecture-guild
```

---

## 19. Templates Reference

All templates are in the `templates/` directory. Use them when creating new artefacts.

| Template | File | Creates |
|---|---|---|
| Epic | `templates/epic.md` | A new epic specification |
| Feature | `templates/feature.md` | A new feature specification |
| Story | `templates/story.md` | A new user story |
| ADR | `templates/adr.md` | An architecture decision record |
| BDR | `templates/bdr.md` | A business decision record |
| HLD | `templates/hld.md` | A high-level design document |
| LLD | `templates/lld.md` | A low-level design document |
| Domain README | `templates/domain-readme.md` | A domain overview |
| API Spec | `templates/api-spec.yaml` | An OpenAPI 3.x specification |

### Usage

Copy the template to the correct location, rename as needed, and fill in the content:

```bash
# Example: create a new epic
cp templates/epic.md domains/onboarding/epics/customer-onboarding/epic.md
```

Or ask an AI agent:

> Create a new epic called "customer-onboarding" in the onboarding domain using the epic template.

---

## 20. Getting Started

### For New Contributors

1. **Clone** this repository
2. **Read** this README end-to-end
3. **Read** `CLAUDE.md` or `AGENTS.md` for AI agent conventions
4. **Find your domain** in `domains/` and read its `README.md`
5. **Browse** `templates/` to understand artefact formats
6. **Check** `knowledge/glossary.md` for standard terminology
7. **Create** new artefacts using templates
8. **Open a PR** for review

### For AI Agents

1. Load `CLAUDE.md` or `AGENTS.md` (done automatically by most tools)
2. Read the target domain's `README.md` for context
3. Read existing specs in the domain to understand patterns and scope
4. Use templates and frontmatter standards when creating new artefacts
5. Declare dependencies explicitly
6. Never edit `jira_key` or `jira_status` fields

---

## 21. Gaps and Recommended Improvements

This section documents known gaps in the current framework, prioritised by impact.

### P1 — Blocking Effective Use

| # | Gap | Recommendation | Status |
|---|---|---|---|
| 1 | ~~No CLAUDE.md / AGENTS.md~~ | ~~Create root-level files with all conventions~~ | Done |
| 2 | ~~No templates~~ | ~~Create 9 template files~~ | Done |
| 3 | ~~No frontmatter standard~~ | ~~Define schemas in README and enforce in templates~~ | Done |
| 4 | ~~Empty domain READMEs~~ | ~~Populate using domain-readme template~~ | Done |
| 5 | Only 11 of 23 domains scaffolded | Identify and scaffold remaining 13 domains | Open |

### P2 — Required for Multi-Team Adoption

| # | Gap | Recommendation | Status |
|---|---|---|---|
| 6 | ~~No glossary content~~ | ~~Populate knowledge/glossary.md with banking terminology~~ | Done |
| 7 | ~~No persona definitions~~ | ~~Create persona files in knowledge/personas/~~ | Done |
| 8 | ~~No customer segment definitions~~ | ~~Create segment files in knowledge/customer-segments/~~ | Done |
| 9 | No CODEOWNERS | Create CODEOWNERS mapping domains to team owners | Open |
| 10 | No naming convention enforcement | Add CI linting step (markdownlint + frontmatter validator) | Open |

### P3 — Important for Maturity

| # | Gap | Recommendation | Status |
|---|---|---|---|
| 11 | No CI/CD validation pipeline | GitHub Actions workflow to validate frontmatter, naming, file types, broken links | Open |
| 12 | No versioning strategy | Add `version` field to frontmatter; use semver for API specs | Open |
| 13 | No test strategy integration | Add `acceptance-tests/` or `test-strategy.md` to domain structure | Open |
| 14 | No MCP server integration | Document how MCP tools (Linear, Jira, Git) read/write to the repo | Open |
| 15 | No cross-domain dependency validation | CI check that all `dependencies` paths resolve to existing files | Open |
| 16 | No Jira sync tooling | Build automated sync between frontmatter and Jira | Open |

### Remaining Domain Identification

The framework calls for 23 domains. Currently 11 are named. The remaining 12 should be identified through stakeholder workshops covering all lines of business. Candidate domains to explore:

- `savings` — Savings accounts and fixed deposits
- `investments` — Investment products and portfolio management
- `insurance` — Insurance product distribution
- `foreign-exchange` — FX and currency services
- `trade-finance` — Trade finance and letters of credit
- `treasury` — Treasury management services
- `compliance` — Regulatory compliance and reporting
- `fraud-detection` — Fraud prevention and detection
- `customer-communications` — Notifications, correspondence, templates
- `digital-channels` — Mobile app, internet banking, chatbots
- `data-analytics` — Reporting, BI, data warehouse
- `security` — Identity, access management, encryption
- `open-banking` — Open banking APIs, PSD2 compliance
