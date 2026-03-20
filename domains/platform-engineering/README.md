# Platform Engineering

## Overview

The platform-engineering domain covers infrastructure, CI/CD pipelines, observability, developer experience, and platform services that support all product domains.

## Boundaries

### This Domain Covers

- Cloud infrastructure and provisioning
- CI/CD pipelines and deployment automation
- Observability (logging, monitoring, alerting, tracing)
- Developer experience and tooling
- API gateway and service mesh
- Container orchestration and runtime platforms
- Secret management and certificate management
- Performance engineering and capacity planning
- Disaster recovery and business continuity infrastructure

### This Domain Does NOT Cover

- Application-level shared services (see `enabling-functions`)
- Business logic or product features (belong in respective product domains)
- Security policy and identity management (see `security` — TBD)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |

## Regulatory Considerations

- Cloud hosting and data residency requirements
- Operational resilience regulations
- Third-party risk management for cloud providers
- Change management and deployment controls
- Backup and recovery requirements

## Related Domains

| Domain | Relationship |
|---|---|
| All product domains | Upstream dependency — all domains run on the platform |
| `enabling-functions` | Related — shared application services run on the platform |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **IaC** | Infrastructure as Code — managing infrastructure through version-controlled definitions |
| **SRE** | Site Reliability Engineering — practices for maintaining reliable systems |
| **SLA/SLO/SLI** | Service Level Agreement/Objective/Indicator — reliability targets |
| **MTTR** | Mean Time to Recovery — average time to restore service after an incident |
| **RPO/RTO** | Recovery Point Objective / Recovery Time Objective — disaster recovery targets |
