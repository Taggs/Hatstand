# Payments

## Overview

The payments domain covers all payment processing capabilities including domestic transfers, international payments, standing orders, direct debits, real-time payments, and bulk payment processing.

## Boundaries

### This Domain Covers

- Domestic payment processing (faster payments, BACS, CHAPS or equivalent)
- International/cross-border payments (SWIFT, SEPA)
- Real-time payment schemes
- Standing orders and scheduled payments
- Direct debit origination and collection
- Bulk/batch payment processing (payroll, supplier payments)
- Payment status tracking and notifications
- Payment routing and scheme selection
- Payment validation and sanctions screening

### This Domain Does NOT Cover

- Card transaction processing (see `cards`)
- Foreign exchange execution (see domain TBD)
- Trade finance payments (see domain TBD)
- Account balance management (see `account-servicing`)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |

## Regulatory Considerations

- Payment scheme rules and compliance (Faster Payments, SEPA, SWIFT)
- Sanctions screening requirements for all outbound payments
- PSD2 requirements for payment initiation and confirmation
- Real-time payment irrevocability
- Confirmation of Payee requirements

## Related Domains

| Domain | Relationship |
|---|---|
| `account-servicing` | Bidirectional — payments debit/credit accounts |
| `cards` | Related — card payments are a payment type |
| `lending` | Related — loan disbursements and repayments |
| `onboarding` | Downstream — payment setup during onboarding |
| `enabling-functions` | Dependency — notifications for payment status |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **FPS** | Faster Payments Service — UK real-time payment scheme |
| **BACS** | Bankers' Automated Clearing Services — UK batch payment scheme |
| **CHAPS** | Clearing House Automated Payment System — UK high-value payment scheme |
| **SEPA** | Single Euro Payments Area — EU payment integration scheme |
| **SCT Inst** | SEPA Credit Transfer Instant — real-time euro payments |
| **CoP** | Confirmation of Payee — name-checking service for payments |
| **STP** | Straight-Through Processing — automated payment processing |
