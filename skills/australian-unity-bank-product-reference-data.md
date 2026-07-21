---
name: Retrieve Australian Unity Bank product reference data
description: Fetch public banking product, rate, and fee data from Australian Unity Bank's CDR Product Reference Data (PRD) endpoints — no authentication required.
api: openapi/australian-unity-bank-cds-banking-openapi.json
operations: [listBankingProducts, getBankingProductDetail]
---

# Retrieve product reference data

Australian Unity Bank exposes public Product Reference Data (PRD) under the DSB
Consumer Data Standards. No OAuth/consent is required for these two operations.

## Base
`https://open-banking.australianunity.com.au/cds-au/v1`

## Steps
1. Call `listBankingProducts` (`GET /banking/products`). Always send the `x-v`
   header (e.g. `x-v: 3`). Optional filters: `product-category`, `effective`,
   `updated-since`, `brand`, plus `page` / `page-size`.
2. For each product of interest, call `getBankingProductDetail`
   (`GET /banking/products/{productId}`) with the `x-v` header to get full rate,
   fee, eligibility, and feature detail.

## Rules
- `x-v` is mandatory; omitting it returns `400 Header/Missing`, an unsupported
  value returns `406 Header/UnsupportedVersion` (see errors/australian-unity-bank-problem-types.yml).
- Paginate with `page`/`page-size` (max 1000); out-of-range page returns `422 Field/InvalidPage`.
- The host is WAF/geo/accreditation-gated — non-Australian or non-accredited
  callers may receive `403`.
