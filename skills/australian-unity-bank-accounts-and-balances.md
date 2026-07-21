---
name: Retrieve Australian Unity Bank accounts and balances
description: List a consenting member's authorised accounts and read their balances via Australian Unity Bank's CDR consumer-data endpoints (requires ADR accreditation + consent).
api: openapi/australian-unity-bank-cds-banking-openapi.json
operations: [listBankingAccounts, getBankingAccountDetail, listBankingBalancesBulk, listBankingBalancesSpecificAccounts, getBankingBalance]
---

# Retrieve accounts and balances

These are consumer-authorised endpoints. You must be an ACCC-accredited data
recipient (ADR), hold a valid member consent, and present a CDR security-profile
access token (OAuth2/OIDC/FAPI, mTLS sender-constrained). See
authentication/australian-unity-bank-authentication.yml and
scopes/australian-unity-bank-scopes.yml.

## Base
`https://open-banking.australianunity.com.au/cds-au/v1`

## Steps
1. Obtain a token with scope `bank:accounts.basic:read` (and `bank:accounts.detail:read`
   for detail).
2. Call `listBankingAccounts` (`GET /banking/accounts`) to enumerate authorised
   accounts. Filter with `open-status`, `is-owned`, `product-category`.
3. For balances, either call `listBankingBalancesBulk` (`GET /banking/accounts/balances`)
   for all accounts, `listBankingBalancesSpecificAccounts`
   (`POST /banking/accounts/balances` with an accountId list body), or
   `getBankingBalance` (`GET /banking/accounts/{accountId}/balance`) for one.
4. For full account detail call `getBankingAccountDetail`
   (`GET /banking/accounts/{accountId}`).

## Rules
- Send `x-v` on every request plus the FAPI headers (`x-fapi-interaction-id`,
  `x-fapi-auth-date`, `x-fapi-customer-ip-address` when customer-present).
- Unknown/unavailable accountId returns `404 Authorisation/InvalidBankingAccount`
  or `404 Authorisation/UnavailableBankingAccount`.
- The POST balance variant is a bulk *read* (account list in body), not a mutation —
  no idempotency key applies (conventions/australian-unity-bank-conventions.yml).
