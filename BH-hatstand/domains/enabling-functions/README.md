# Enabling Functions

## Overview

The enabling-functions domain covers shared internal capabilities that are consumed by multiple product domains. These are cross-cutting services that do not belong to a single business domain.

## Boundaries

### This Domain Covers

- Notification services (email, SMS, push, in-app)
- Document generation and templating
- Audit logging and trail management
- Workflow engine and task management
- Search and indexing services
- File storage and document management
- Scheduling and job management
- Feature flagging and configuration management

### This Domain Does NOT Cover

- Infrastructure and platform services (see `platform-engineering`)
- Business-specific logic (belongs in respective product domains)
- Customer-facing channels (see `digital-channels` — TBD)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |

## Regulatory Considerations

- Audit trail retention and immutability requirements
- Notification delivery and proof-of-delivery for regulatory communications
- Document archival requirements

## Related Domains

| Domain | Relationship |
|---|---|
| All product domains | Upstream dependency — all domains consume enabling functions |
| `platform-engineering` | Related — shared infrastructure layer |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **Cross-cutting concern** | A capability that spans multiple domains (e.g., logging, notifications) |
| **Shared service** | A reusable service consumed by multiple domains |
| **Feature flag** | A configuration toggle to enable/disable functionality without deployment |
