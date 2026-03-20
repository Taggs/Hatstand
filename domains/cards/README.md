# Cards

## Overview

The cards domain covers credit and debit card products, including issuance, lifecycle management, transaction processing, disputes, and rewards programmes.

## Boundaries

### This Domain Covers

- Card product configuration and pricing
- Card issuance (physical and virtual)
- Card lifecycle management (activate, freeze, replace, renew, cancel)
- Card transaction authorisation and processing
- Dispute management and chargebacks
- Rewards and loyalty programmes
- Card fraud detection rules (in coordination with fraud-detection domain)
- 3D Secure and strong customer authentication for cards
- Corporate card and expense management

### This Domain Does NOT Cover

- Merchant acquiring and POS terminal management (see domain TBD)
- General payment processing (see `payments`)
- Credit risk assessment for card applications (see `credit-decisioning`)
- General fraud detection systems (see domain TBD)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |

## Regulatory Considerations

- PCI DSS compliance for card data handling
- Strong Customer Authentication (SCA) under PSD2
- Interchange fee regulations
- Chargeback rights and timelines (card scheme rules)
- Contactless transaction limits

## Related Domains

| Domain | Relationship |
|---|---|
| `onboarding` | Upstream — card issuance triggered during onboarding |
| `account-servicing` | Related — card spend impacts account balances |
| `payments` | Related — card transactions are a payment method |
| `credit-decisioning` | Dependency — credit card applications require approval |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **BIN** | Bank Identification Number — first 6-8 digits identifying the issuing bank |
| **PAN** | Primary Account Number — the full card number |
| **CVV/CVC** | Card Verification Value/Code — security code on the card |
| **3DS** | 3D Secure — authentication protocol for online card payments |
| **Chargeback** | Reversal of a card transaction initiated by the cardholder |
| **Interchange** | Fee paid by the merchant's bank to the cardholder's bank per transaction |
