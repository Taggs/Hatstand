# Lending

## Overview

The lending domain covers loan origination, management, and collections across all customer segments. This includes personal loans, mortgages, business loans, asset finance, and structured lending facilities.

## Boundaries

### This Domain Covers

- Loan application and origination workflows
- Loan product configuration and pricing
- Loan disbursement and drawdown
- Repayment scheduling and processing
- Loan restructuring and modifications
- Collections and recovery processes
- Collateral management
- Lending reporting and analytics

### This Domain Does NOT Cover

- Credit risk assessment and scoring (see `credit-decisioning`)
- Credit card lending (see `cards`)
- Trade finance facilities (see domain TBD)
- Investment products (see domain TBD)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |

## Regulatory Considerations

- Consumer credit regulations and affordability checks
- Interest rate disclosure and APR calculations
- Collections and forbearance regulatory requirements
- Collateral registration and perfection
- Large exposure reporting for corporate facilities

## Related Domains

| Domain | Relationship |
|---|---|
| `credit-decisioning` | Dependency — credit approval required before disbursement |
| `account-servicing` | Downstream — loan repayments debited from current accounts |
| `payments` | Dependency — disbursement and repayment processing |
| `onboarding` | Upstream — new lending customers onboarded first |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **Origination** | End-to-end process of creating a new loan |
| **Drawdown** | Disbursement of loan funds to the borrower |
| **Facility** | A credit arrangement (e.g., term loan, revolving credit) |
| **Forbearance** | Temporary relief measures for borrowers in difficulty |
| **LTV** | Loan-to-Value ratio — loan amount as percentage of collateral value |
| **APR** | Annual Percentage Rate — total cost of borrowing expressed annually |
