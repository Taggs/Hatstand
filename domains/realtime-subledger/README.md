# Realtime Subledger

## Overview

The realtime-subledger domain covers the core accounting engine that records, classifies, and balances every financial transaction in real time. The subledger is the authoritative book of record for customer and internal account balances, providing an immutable, double-entry ledger that feeds the general ledger (GL), regulatory reporting, and downstream analytics.

This domain is foundational — almost every product domain (payments, lending, cards, account-servicing) depends on the subledger to post entries, query balances, and reconcile positions.

## Boundaries

### This Domain Covers

- Real-time double-entry transaction posting (debit/credit)
- Account balance management (available, ledger, hold, pending)
- Multi-currency balance tracking and position keeping
- Subledger-to-general-ledger (GL) reconciliation and feeds
- Transaction journaling and immutable audit trail
- Balance snapshot and point-in-time queries
- Interest accrual posting and calculation triggers
- Fee and charge posting
- Transaction reversal, correction, and adjustment entries
- Internal account and suspense account management
- Intraday liquidity position tracking
- Event-driven balance change notifications
- Idempotent posting guarantees (exactly-once semantics)

### This Domain Does NOT Cover

- Payment routing and scheme integration (see `payments`)
- Loan origination and lifecycle (see `lending`)
- Card transaction authorisation (see `cards`)
- Account opening and KYC (see `onboarding`)
- Account servicing UX — statements, alerts, address changes (see `account-servicing`)
- General ledger ownership and chart of accounts (see GL / finance systems)
- Regulatory reporting aggregation (see `compliance` — TBD)
- Credit risk and scoring (see `credit-decisioning`)

## Key Stakeholders

| Role | Name/Team | Responsibility |
|---|---|---|
| Domain Lead | TBD | Overall domain ownership |
| Product Owner | TBD | Requirements and priorities |
| Tech Lead | TBD | Architecture and implementation |
| Finance/Accounting | TBD | GL reconciliation, chart of accounts alignment |
| Risk | TBD | Intraday liquidity and exposure monitoring |

## Regulatory Considerations

- **Accounting standards**: Entries must comply with IFRS / local GAAP requirements for recognition, measurement, and disclosure
- **Immutability**: Posted entries must never be deleted — corrections are made via reversal entries only
- **Audit trail**: Full traceability of every balance change with timestamp, initiator, and source event
- **Data retention**: Transaction records must be retained for the period mandated by local regulation (typically 7-10 years)
- **Reconciliation**: Daily reconciliation between subledger balances and GL must be provable and auditable
- **Real-time reporting**: Regulators increasingly require intraday liquidity reporting (e.g., BCBS 248)
- **Multi-currency**: FX revaluation entries must be posted at regulatory-prescribed rates and frequencies
- **Operational resilience**: Subledger availability is critical path — downtime directly halts all transaction processing

## Related Domains

| Domain | Relationship |
|---|---|
| `payments` | Upstream — payment processing posts debit/credit entries to the subledger |
| `lending` | Upstream — disbursements, repayments, interest accruals post to the subledger |
| `cards` | Upstream — card authorisations create holds; settlements post entries |
| `account-servicing` | Downstream consumer — reads balances for statements, alerts, and account views |
| `onboarding` | Trigger — new account creation initialises subledger accounts |
| `credit-decisioning` | Related — available balance is an input to credit decisions |
| `enabling-functions` | Dependency — event bus for balance change notifications |
| `platform-engineering` | Dependency — high-availability infrastructure, low-latency data stores |

## Architecture Characteristics

The realtime subledger has distinctive non-functional requirements that shape its architecture:

| Characteristic | Target | Rationale |
|---|---|---|
| **Availability** | 99.99%+ | Subledger downtime halts all transaction processing |
| **Latency (p99)** | < 50ms per posting | Real-time balance updates required for instant payments |
| **Throughput** | 10,000+ TPS | Peak volumes during payroll runs, batch settlements |
| **Consistency** | Strong | Double-entry invariant (debits = credits) must never be violated |
| **Durability** | Zero data loss | Every posted entry must survive any single failure |
| **Idempotency** | Exactly-once | Duplicate posting requests must be safely deduplicated |
| **Immutability** | Append-only | No UPDATE or DELETE on posted journal entries |

## Current Epics

| Epic | Status | Description |
|---|---|---|
| — | — | No epics created yet |

## Domain Glossary

| Term | Definition |
|---|---|
| **Subledger** | A subsidiary ledger that records detailed transactions for a specific category (e.g., customer accounts), feeding summary entries to the general ledger |
| **General Ledger (GL)** | The master accounting record that aggregates all subledger balances for financial reporting |
| **Double-entry** | Accounting principle where every transaction creates equal and opposite debit and credit entries |
| **Journal entry** | A single accounting record consisting of one or more debit/credit line items that must balance to zero |
| **Posting** | The act of recording a journal entry to the subledger |
| **Available balance** | The balance a customer can use for transactions (ledger balance minus holds plus pending credits) |
| **Ledger balance** | The balance of all settled/posted transactions (excludes holds and pending items) |
| **Hold** | A temporary reservation against available balance (e.g., card authorisation, cheque hold) |
| **Reversal** | A correcting entry that negates a previously posted entry (never deletion) |
| **Suspense account** | An internal account used to temporarily hold entries that cannot yet be allocated to a final account |
| **Reconciliation** | The process of verifying that subledger balances match the corresponding GL accounts |
| **Accrual** | Recognition of revenue or expense before the cash flow occurs (e.g., interest accrual) |
| **Idempotency key** | A unique identifier attached to a posting request to prevent duplicate entries |
| **Position** | The net balance of an account or set of accounts at a point in time |
| **FX revaluation** | Adjusting multi-currency balances to reflect current exchange rates |
| **Chart of accounts** | The hierarchical classification scheme mapping subledger accounts to GL accounts |
| **Settlement** | The process of converting a pending/authorised transaction into a final posted entry |
| **Memo posting** | A provisional entry visible to the customer but not yet settled (e.g., pending card transaction) |
| **End-of-day (EOD)** | Batch processing window for interest calculation, GL feeds, and reconciliation |
| **Intraday liquidity** | Real-time tracking of cash positions throughout the business day |
