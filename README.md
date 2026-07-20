# HSBC Bank Australia (hsbc-australia)

HSBC Bank Australia Limited is the Australian banking subsidiary of the global HSBC Group (HSBC Holdings plc), operating as an APRA-regulated Authorised Deposit-taking Institution (ADI). It is a wholly owned, shareholder-owned bank offering home loans, everyday and savings accounts, credit cards, term deposits, and business and international banking. As a designated data holder under Australia's Consumer Data Right (CDR / Open Banking), HSBC Australia exposes a public, unauthenticated Product Reference Data (PRD) API conforming to the DSB Consumer Data Standards.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/hsbc-australia/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/hsbc-australia/refs/heads/main/apis.yml)

## Tags

- Financial
- Banks
- Open Banking
- CDR
- Consumer Data Right
- Consumer Banking
- Australia
- Product Reference Data

## Timestamps

- **Created:** 2026-07-20
- **Modified:** 2026-07-20

## APIs

### HSBC Bank Australia CDR Product Reference Data API

Public, unauthenticated Consumer Data Right Product Reference Data (PRD) API. Confirmed live (HTTP 200, x-v 5) returning a `data.products` array of HSBC Australia banking products - home loans, deposit accounts, credit cards, and term deposits - with rates, fees, features, and eligibility. Conforms to the DSB Consumer Data Standards (CDR Banking API); the Get Products and Get Product Detail (`{productId}`) endpoints require no authentication.

- **Human URL:** [https://www.hsbc.com.au/help/open-banking/](https://www.hsbc.com.au/help/open-banking/)
- **Base URL:** `https://public.ob.hsbc.com.au/cds-au/v1`

#### Tags

- CDR
- Open Banking
- Product Reference Data
- Banking
- Public

#### Properties

- [Documentation](https://www.hsbc.com.au/help/open-banking/)
- [API Reference](https://public.ob.hsbc.com.au/cds-au/v1/banking/products)
- [OpenAPI](openapi/hsbc-australia-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [Website](https://www.hsbc.com.au/)
- [Documentation](https://www.hsbc.com.au/help/open-banking/)
- [Privacy Policy](https://www.hsbc.com.au/privacy/)
- [GitHub Organization](https://github.com/hsbc)
- [LinkedIn](https://www.linkedin.com/company/hsbc)
- [Support](mailto:openbankingsupport@hsbc.com)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
