# Australian Unity Bank (australian-unity-bank)

Australian Unity Bank Limited is the banking arm of Australian Unity, a member-owned Australian mutual founded in Melbourne in 1840 with origins in the friendly-societies movement. The wider Australian Unity group spans health insurance, wealth management, aged and home care, retirement living, and banking. The bank traces to Big Sky Credit Union, which merged with Australian Unity in 2012, became Big Sky Building Society Limited, and was later renamed Australian Unity Bank Limited. It is an APRA-authorised deposit-taking institution (ADI) covered by the Financial Claims Scheme, offering everyday transaction and savings accounts, term deposits, and home loans to members.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/australian-unity-bank/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/australian-unity-bank/refs/heads/main/apis.yml)

## Consumer Data Right (CDR) Posture

Under Australia's Consumer Data Right (Open Banking), every active ADI must expose a public, unauthenticated Product Reference Data (PRD) API at `https://<data-holder-host>/cds-au/v1/banking/products`, conforming to the Data Standards Body (DSB) Consumer Data Standards (CDS).

As of 2026-07-20, Australian Unity Bank is a genuine ADI but is **not** listed as an active data holder brand in the [CDR Register](https://api.cdr.gov.au/cdr-register/v1/banking/data-holders/brands/summary), and it has historically fallen under CDR exemption / deferred data-holder timelines. No live PRD endpoint could be confirmed (`https://api.australianunity.com.au/cds-au/v1/banking/products` returned HTTP 404). The bank publishes no developer portal or open-banking API documentation on its public website. The single API listed below is therefore the shared CDS standard surface, recorded as **unverified** for this bank.

## Tags

- Financial
- Banks
- Open Banking
- CDR
- Consumer Banking
- Australia
- Mutual
- Product Reference Data

## Timestamps

- **Created:** 2026-07-20
- **Modified:** 2026-07-20

## APIs

### Australian Unity Bank CDR Product Reference Data API

The Consumer Data Right Product Reference Data (PRD) API is the public, unauthenticated `GET /cds-au/v1/banking/products` (and `/products/{productId}`) surface that every active Australian ADI must expose under the DSB Consumer Data Standards. It returns product data — accounts, rates, fees, and eligibility — as JSON with an `x-v` version header. **Unverified for Australian Unity Bank:** no live endpoint returned HTTP 200, and the bank is not an active data holder in the CDR Register, so the base URL shown is the shared CDS path template, not a confirmed Australian Unity host.

- **Human URL:** [https://consumerdatastandardsaustralia.github.io/standards/#banking-products](https://consumerdatastandardsaustralia.github.io/standards/#banking-products)
- **Base URL:** `https://{dataHolderPublicBaseUri}/cds-au/v1/banking/products` (unverified — CDS template)

#### Tags

- Open Banking
- CDR
- Product Reference Data
- Banking
- Products

#### Properties

- [Documentation](https://consumerdatastandardsaustralia.github.io/standards/#banking-products)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#get-products)
- [Provenance](https://www.cdr.gov.au/for-providers/how-find-data-holders-product-data-request-service)

## Common Properties

- [Website](https://www.australianunity.com.au/)
- [LinkedIn](https://www.linkedin.com/company/australian-unity/)
- [Privacy Policy](https://www.australianunity.com.au/privacy-policy)
- [Terms of Service](https://www.australianunity.com.au/terms-and-conditions)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
