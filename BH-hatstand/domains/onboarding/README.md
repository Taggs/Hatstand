# Onboarding

## Overview

The onboarding domain covers the end-to-end process of acquiring new customers and setting up their initial banking relationships. This includes identity verification (KYC), document collection, account opening, and initial product activation.

## Boundaries

### This Domain Covers

- Customer identity verification and KYC processes
- Document upload and validation (ID, proof of address, etc.)
- New-to-bank account opening (retail, SME, corporate)
- Additional product activation during onboarding
- Regulatory compliance checks (AML, sanctions screening)
- Digital and branch onboarding journeys

### This Domain Does NOT Cover

- Ongoing account management (see `account-servicing`)
- Credit assessment and approval (see `credit-decisioning`)
- Card issuance post-onboarding (see `cards`)
- Ongoing KYC refresh / periodic review (see `compliance` — TBD)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |

## Regulatory Considerations

- KYC/AML regulations require identity verification before account activation
- Data protection (GDPR) governs handling of personal documents and data
- Record retention requirements for onboarding documents
- Accessibility requirements for digital onboarding journeys

## Related Domains

| Domain | Relationship |
|---|---|
| `account-servicing` | Downstream — receives newly created accounts |
| `credit-decisioning` | Dependency — credit checks during onboarding |
| `cards` | Downstream — card issuance triggered by onboarding |
| `payments` | Downstream — initial payment setup (direct debits, standing orders) |
| `enabling-functions` | Dependency — document generation, notifications |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **KYC** | Know Your Customer — identity verification process |
| **CDD** | Customer Due Diligence — risk assessment of new customers |
| **EDD** | Enhanced Due Diligence — additional checks for high-risk customers |
| **PEP** | Politically Exposed Person — requires enhanced screening |
| **eIDV** | Electronic Identity Verification |
