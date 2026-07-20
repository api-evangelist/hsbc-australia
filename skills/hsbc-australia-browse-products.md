---
name: Browse HSBC Australia banking products
description: List the banking products HSBC Australia openly offers to the market (home loans, deposit accounts, credit cards, term deposits) via the public, unauthenticated CDR Product Reference Data API.
api: openapi/hsbc-australia-cds-banking-products-openapi.yml
operations: [listBankingProducts]
---

# Browse HSBC Australia banking products

The HSBC Australia Product Reference Data API is **public and unauthenticated** —
no API key, no OAuth. It follows the DSB Consumer Data Standards (CDR Banking).

## Base URL
`https://public.ob.hsbc.com.au/cds-au/v1`

## Steps

1. Call **`listBankingProducts`** — `GET /banking/products`.
   - You MUST send the version header `x-v: 5` (supported: 4 and 5). Omitting it
     returns `400 urn:au-cds:error:cds-all:Header/Missing`; an unsupported value
     returns `406 urn:au-cds:error:cds-all:Header/UnsupportedVersion`.
   - Optional query params:
     - `effective` = `CURRENT` (default) | `FUTURE` | `ALL`
     - `updated-since` = RFC3339 date-time
     - `product-category`, `brand`
     - `page` (1-based) and `page-size` (default 25)
2. Read `data.products[]` — each item is a product summary (`productId`,
   `productCategory`, `name`, `description`, `brand`, `lastUpdated`).
3. **Paginate**: use `meta.totalPages` / `meta.totalRecords` and the `links.next`
   URL until `links.next` is absent.
4. To drill into a product, pass its `productId` to the
   `getBankingProductDetail` flow.

## Conventions
- Version via the `x-v` request header; the response echoes `x-v`.
- Errors use the CDS envelope `{ errors: [ { code, title, detail } ] }` with
  `urn:au-cds:error:...` codes (see `errors/hsbc-australia-problem-types.yml`).
- Read-only surface — no idempotency key needed.
