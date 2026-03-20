---
title: "BH-hatstand Glossary"
description: "Standard terminology for the BH-hatstand specification framework and banking domain"
updated: 2026-03-20
---

# Glossary

Standard terminology used across all domains. Domain-specific terms should be defined in the domain's own `knowledge/` folder or `README.md` glossary section.

## Framework Terms

| Term | Definition |
|---|---|
| **BH-hatstand** | The specification repository and framework; part of the BlueHat AI Method |
| **BlueHat AI Method** | The overarching AI-first development methodology |
| **Artefact** | Any specification document (epic, feature, story, ADR, BDR, HLD, LLD, API spec) |
| **Slug** | A lowercase, hyphen-separated identifier used as folder/file names (e.g., `mobile-document-upload`) |
| **Frontmatter** | YAML metadata block at the top of every markdown specification file |
| **Domain** | A bounded business area with its own epics, architecture, and knowledge (e.g., payments, lending) |
| **Epic** | A large body of work delivering a business outcome; contains features |
| **Feature** | A distinct capability within an epic; contains stories |
| **Story** | A single implementable unit of work with acceptance criteria |
| **ADR** | Architecture Decision Record — documents a technical decision and its rationale |
| **BDR** | Business Decision Record — documents a business/product decision and its rationale |
| **HLD** | High-Level Design — system context, components, data flows, integration points |
| **LLD** | Low-Level Design — module structure, sequence diagrams, data models, error handling |
| **Blueprint** | A solution design document that may span multiple epics within a domain |
| **C4 Model** | A set of hierarchical diagrams (Context, Container, Component, Code) for software architecture |

## Banking Terms

| Term | Definition |
|---|---|
| **KYC** | Know Your Customer — regulatory process of verifying client identity |
| **AML** | Anti-Money Laundering — regulations and processes to prevent money laundering |
| **PSD2** | Payment Services Directive 2 — EU regulation for payment services and open banking |
| **Open Banking** | Regulatory framework requiring banks to share customer data with authorised third parties via APIs |
| **Onboarding** | The process of acquiring and setting up a new customer or account |
| **Origination** | The process of creating a new financial product (e.g., loan origination) |
| **Servicing** | Ongoing management and maintenance of customer accounts and products |
| **Decisioning** | Automated or semi-automated process of making credit, risk, or eligibility decisions |
| **SME** | Small and Medium Enterprise — a business customer segment |
| **Corporate** | Large corporate customers, typically with complex banking needs |
| **Commercial** | Mid-market business customers between SME and Corporate |
| **PI** | Program Increment — a planning period in SAFe (Scaled Agile Framework), typically 8-12 weeks |
| **AC** | Acceptance Criteria — testable conditions that define when a story is complete |
| **API** | Application Programming Interface — a contract defining how systems communicate |
| **STP** | Straight-Through Processing — automated end-to-end processing without manual intervention |
| **T+0 / T+1** | Same-day / next-day settlement timeframes |
| **IBAN** | International Bank Account Number |
| **SWIFT** | Society for Worldwide Interbank Financial Telecommunication — global messaging network |
| **PCI DSS** | Payment Card Industry Data Security Standard |
| **SOC 2** | Service Organization Control 2 — security compliance framework |
| **MFA** | Multi-Factor Authentication |
| **JWT** | JSON Web Token — a standard for securely transmitting information between parties |
| **OAuth 2.0** | Open standard for access delegation, commonly used for API authorisation |
| **RBAC** | Role-Based Access Control |
| **DDD** | Domain-Driven Design — software design approach organising around business domains |
