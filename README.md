# Australian Unity Bank (australian-unity-bank)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
