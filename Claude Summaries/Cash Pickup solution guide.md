---
type: claude-summary
session_id: local_e700f2d7-2979-4093-b481-7a4125619cac
session_title: Cash Pickup solution guide
last_synced: 2026-10-12
status: active
tags: [claude-summary, cash-pickup, solution-guide, disbursements]
---
# Cash Pickup solution guide

## Context
Karl is writing a partner-facing Solution Guide for Green Dot's Cash Pickup (cash-out/disbursement) solution himself. He wanted help identifying key content and checking his logic. The Narmi Cash Loads guide and a generic Solution Guide template were the models.

## Artifacts
- Narmi - Cash Loads Solution Overview - May 2026.docx (Karl's OneDrive; read successfully)
- Solution Guide Template - Generic.docx (Karl's OneDrive; could not be located via search)
- Uploaded: Green Dot Partner Cash Out Specifications v1.4 (PDF)
- Dev docs: https://developer.greendot.com/embedded-finance/docs/cashpickup-overview

## Key findings
- Cash Pickup is outbound (cash to customer), the opposite of Cash Loads. Two use cases: account withdrawal (partner debits customer ledger) and push payout to possibly unaccounted payees (gig, insurance, EWA; settles against program-level account). GD-side flow is the same for both; partner logic differs.
- Correction from Karl: Cash Pickup is ONLY supported at Walmart Money Centers (~4,700 US locations), not the full GDN retail network.
- Claim code flow (partner calls GD Transfer API): POST /customers/{customerid} -> POST /customers/{customerid}/links/type/cash -> POST /transfers/{transferid} (claim code/barcode) -> POST /transfers/confirm/{transferId} (cancel/void before redemption).
- Barcode Consumption API hosted by partner (GD calls it, REST). Spec v1.4 shows partner chooses 1-phase or 2-phase (dev docs only show 1-phase):
  - Always: GetAccessToken (Basic auth with ClientId/SecretKey; bearer token 1-2 hr recommended, 24 hr max; GD caches), Void (by originalAuthorizationId if commit timed out, or transactionReference if auth/authcommit timed out), Get Transaction Status (by claimcode or GD ref; not-found must return HTTP 2xx with code 954 / subcode 625, otherwise settlement mismatch alerts).
  - 1-phase: AuthCommit (returns authorizationId, Completed, Consumed).
  - 2-phase: Auth (Pending/Pending, reserve not debit) then Commit (originalAuthorizationId; returns confirmationId, Completed/Consumed). Uncommitted auth gets cancelled and the claim code becomes reusable.
  - Optional (1-phase): Notification after retailer confirms dispense; partner returns 200/204.
- Requirements: IP whitelisting of GD IPs; idempotency on transactionReference + claimCode; partner enforces transaction limits (subcodes 622-627).
- Customer verification: likely OFAC screening on payee data, not full KYC/CIP. Walmart may request ID at the counter above certain amounts. Recommended wording: "payee verification" or "identity verification for OFAC screening," not "KYC."
- No void window is defined in the spec or the dev docs.

## Decisions
- One unified flow diagram, with a Partner Responsibilities callout for the withdrawal vs payout differences.
- Describe the consumption service at a high level in the overview; put endpoint detail in the technical section or the spec handoff.

## Open questions
- Void window timing (route to GD product/engineering).
- Exact Customer Profile required fields and whether any verification goes beyond OFAC (route to GD compliance/product).
- Reconcile discrepancies between the dev docs and Spec v1.4.

## Next steps
- Finish the barcode consumption section using the endpoint list above.
- Confirm the void window and verification scope before sharing with a partner.

## Key sources
- https://developer.greendot.com/embedded-finance/docs/cashpickup-overview
- Green Dot Partner Cash Out Specifications v1.4 (PDF)

## Resume prompt
> I'm Karl (PSE, Green Dot) drafting a Cash Pickup Solution Guide modeled on the Narmi Cash Loads guide. Key facts: Cash Pickup is Walmart Money Centers only. Partner calls the GD Transfer API (customer -> cash link -> transfer/claim code -> confirm/cancel). Partner hosts a REST Barcode Consumption API: GetAccessToken, Void, Get Transaction Status (not-found = 2xx 954/625), plus AuthCommit (1-phase) or Auth+Commit (2-phase), with optional Notification. Requirements: IP whitelisting, idempotency on transactionReference+claimCode, partner-enforced limits (622-627). Verification is likely OFAC-only, not KYC. Open: void window, Customer Profile fields/verification scope, dev docs vs Spec v1.4 gaps. Please help me with: [next task].
