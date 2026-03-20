# Account Servicing

## Overview

The account-servicing domain covers the ongoing lifecycle management of customer accounts after onboarding. This includes account maintenance, statements, alerts, fee management, and account closure.

## Boundaries

### This Domain Covers

- Account maintenance (address changes, contact updates, mandate changes)
- Statement generation and delivery
- Account alerts and notifications
- Fee calculation and application
- Interest calculation and posting
- Account dormancy management
- Account closure and migration
- Multi-entity account structures (pooling, sweeping)

### This Domain Does NOT Cover

- Initial account opening (see `onboarding`)
- Loan account management (see `lending`)
- Card account management (see `cards`)
- Payment processing (see `payments`)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |

## Regulatory Considerations

- Statement delivery requirements and retention periods
- Dormant account regulations
- Fee transparency and disclosure requirements
- Data protection for account information

## Related Domains

| Domain | Relationship |
|---|---|
| `onboarding` | Upstream — receives new accounts from onboarding |
| `payments` | Bidirectional — payment transactions affect account balances |
| `lending` | Related — lending products linked to current accounts |
| `cards` | Related — card spend impacts account balances |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **Pooling** | Consolidating balances across multiple accounts for interest or reporting |
| **Sweeping** | Automated transfer of funds between accounts based on rules |
| **Dormancy** | An account with no customer-initiated transactions for a defined period |
| **Mandate** | The signing authority rules governing who can operate an account |
