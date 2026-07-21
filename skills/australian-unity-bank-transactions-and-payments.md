---
name: Retrieve Australian Unity Bank transactions and payment arrangements
description: Read a consenting member's transactions, direct debits, scheduled payments, instalment plans, and saved payees via Australian Unity Bank's CDR consumer-data endpoints.
api: openapi/australian-unity-bank-cds-banking-openapi.json
operations: [listBankingTransactions, getBankingTransactionDetail, listDirectDebits, listScheduledPayments, listInstalmentPlans, listBankingPayees, getBankingPayeeDetail]
---

# Retrieve transactions and payment arrangements

Consumer-authorised endpoints — requires ADR accreditation, member consent, and a
CDR security-profile token. Scopes: `bank:transactions:read`,
`bank:regular_payments:read`, `bank:payees:read`
(scopes/australian-unity-bank-scopes.yml).

## Base
`https://open-banking.australianunity.com.au/cds-au/v1`

## Steps
1. List an account's transactions with `listBankingTransactions`
   (`GET /banking/accounts/{accountId}/transactions`). Filter with `oldest-time`,
   `newest-time`, `min-amount`, `max-amount`, `text`; paginate with `page`/`page-size`.
2. Drill into one with `getBankingTransactionDetail`
   (`GET /banking/accounts/{accountId}/transactions/{transactionId}`).
3. Read payment arrangements: `listDirectDebits`
   (`GET /banking/accounts/{accountId}/direct-debits`), `listScheduledPayments`
   (`GET /banking/accounts/{accountId}/payments/scheduled`), and `listInstalmentPlans`
   (`GET /banking/accounts/{accountId}/payments/plans`).
4. Read saved payees with `listBankingPayees` (`GET /banking/payees`) and
   `getBankingPayeeDetail` (`GET /banking/payees/{payeeId}`).

## Rules
- `x-v` header mandatory on every call; FAPI headers as in the accounts skill.
- Invalid/unavailable accountId returns the `404` CDR authorisation errors.
- All operations are read-only; the CDS Banking surface exposes no write/payment-initiation.
