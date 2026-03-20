# Credit Decisioning

## Overview

The credit-decisioning domain covers credit risk assessment, scoring models, affordability checks, and automated decisioning engines used across all lending and credit products.

## Boundaries

### This Domain Covers

- Credit scoring models and engines
- Affordability assessment
- Automated credit decisioning rules
- Manual underwriting workflows
- Credit policy management
- Bureau data integration (credit reference agencies)
- Decisioning analytics and MI
- Model governance and validation

### This Domain Does NOT Cover

- Loan product management and origination (see `lending`)
- Card product management (see `cards`)
- Collections and recovery (see `lending`)
- Fraud detection (see domain TBD)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |

## Regulatory Considerations

- Consumer credit regulations for affordability assessment
- Model risk management (SR 11-7 or equivalent)
- Fair lending and anti-discrimination requirements
- Right to explanation for automated decisions
- Credit reference agency data handling and reporting

## Related Domains

| Domain | Relationship |
|---|---|
| `lending` | Downstream consumer — lending calls decisioning for credit approval |
| `cards` | Downstream consumer — card applications require credit decisions |
| `onboarding` | Related — initial credit checks during onboarding |
| `relationship-management` | Related — existing relationship data informs decisions |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **Scorecard** | A statistical model producing a credit score |
| **Cutoff** | The score threshold for automatic approval or decline |
| **Bureau** | Credit reference agency (e.g., Experian, Equifax, TransUnion) |
| **DTI** | Debt-to-Income ratio — borrower's debt payments as percentage of income |
| **PD** | Probability of Default — likelihood a borrower will default |
| **LGD** | Loss Given Default — expected loss if default occurs |
