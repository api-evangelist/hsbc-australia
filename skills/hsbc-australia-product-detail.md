---
name: Get HSBC Australia product detail
description: Resolve a specific HSBC Australia banking product to its full detail — rates, fees, features, constraints, and eligibility — via the public CDR Product Reference Data API.
api: openapi/hsbc-australia-cds-banking-products-openapi.yml
operations: [listBankingProducts, getBankingProductDetail]
---

# Get HSBC Australia product detail

Public, unauthenticated CDR Product Reference Data. Base URL
`https://public.ob.hsbc.com.au/cds-au/v1`.

## Steps

1. (If you do not already have a `productId`) call **`listBankingProducts`** —
   `GET /banking/products` with header `x-v: 5` — and pick the target product's
   `productId` from `data.products[]`.
2. Call **`getBankingProductDetail`** — `GET /banking/products/{productId}` with
   header `x-v: 5`.
   - A missing/unknown `productId` returns `404
     urn:au-cds:error:cds-all:Resource/NotFound`.
3. Read the detail payload (`data`): summary fields plus `bundles`, `features`,
   `constraints`, `eligibility`, `fees` (with nested `discounts`), `depositRates`
   and `lendingRates` (with rate `tiers`). See
   `data-model/hsbc-australia-data-model.yml` for the full entity graph.

## Conventions
- `x-v: 5` version header is required on both operations; the response echoes `x-v`.
- Errors use the CDS `ResponseErrorListV2` envelope with `urn:au-cds:error:...`
  codes (`errors/hsbc-australia-problem-types.yml`).
- Read-only — no idempotency key. Product data contains no consumer data.
