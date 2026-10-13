---
type: claude-summary
session_id: local_2bceb928-4f09-4326-97f7-4d8dc4f398de
session_title: Toast Cash gift card aggregation code
last_synced: 2026-10-12
status: active
tags: [claude-summary, toast-cash, closed-loop-prepaid, aft-funding]
---
# Toast Cash Gift Card Aggregation Architecture

## Context
Karl traced the end-to-end Toast Cash architecture (loads, spend auth, balance, FIFO gift card aggregation) across Confluence, Jira, and Datadog to find the owning repos. The end goal is to argue to business/compliance that Toast can add a tokenized private-label Visa credential (Apple Pay tap-to-pay) without changing the KYC-exempt account structure.

## Artifacts
- Confluence: KT - [Toast] AccountGiftCard Processor (BAASPO 1355810067); Toast NPNR technical design (BAASPO 340722392) and V2 FIFO doc (BAASPO 359760178); Toast API (BAASPO 402751557); TOAST Systems Integration and Workflows (CBS 95986240); Toast Phase 2 (PROD 834928752); Digital Funding to Toast Accounts (BAASPO 74023668); GBOS-207188 IFT spike (QABEMM 2579726383)
- Jira: GBOS-158437 (promo credits, disabled), GSS-64405, GSS-65577, GSS-66147, GSS-69381 (toastaft migration), SAMSUNGIMP-11/-14 (AFT decline examples), CBS-31639 / GBOS-206729 (ACI CMM upgrade)
- Datadog trace of a sample $50 load (APM trace 6a7b939c00000000402bfe9ea3a78b7a)

## Key findings
- Repos: `GBOS-BAT-PnReconciliation` (batch FIFO engine, 3x/day, T-2 data; jobs LoadAccountGiftCardTransactions, AccountGiftCardReconciliation); `GdAccountGiftCardProcessor` (near-real-time credit-side records via RabbitMQ/FeedProcessor); `GSS-MMSSVC-GlobalFundTransfer` and `GSS-MMSSVC-ExternalCardTransfer` (load path; Datadog `gss.mmssvc.*`, on-prem DC1, Fiserv RapidConnect raw TCP not visible in APM); `GBOS-COM-InstantFundTransfer` (IFT); `GBOS-RH-RequestHandler` (enrollment and Private Network Transactions API); `GBOS-BOS-CoreAPI`; ACI integration: `GBOS-COM-CBSProcessorManager`, `CBS-APIM-ACIProxy`, `Common-CoreBanking.Domain`.
- Tables: AccountGiftCard, GiftCardSpend, DailyGiftCardBatch(Account), PostTransactionPostInternal_Staging; TransClass keys 76 (load), 287, 73 (purchase), 79 (reversal).
- One BaaS account per Toast user (ToastAccountIdentifier) with one primary purse; GSS customer + link + linked card records. Auth checks only aggregate `purse.availableBalance`; gift cards are reconstructed retroactively (FIFO) for the non-reloadable KYC exemption (31 CFR 1010.100(ff)(4)(iii)(A)). Karl's framing: retroactive "legal fiction" scaffolding, not designed-in.
- PNT: Toast calls `POST /baas/v1/programs/toast/payments/authorize`; RequestHandler maps to ISO 8583 (MTI 1200, reversals 400/401) over persistent socket (1804/1814 handshake) to ACI BASE24-EPS. ACI source is a black box.
- Loads: `toastaft` is a GSS routing config created for the Phase 2 AFT migration; prod ECT config has `AFTProgramCodes: ["toast","toastaft"]`, no fallback/resend for Toast. Stale `EnableAFTCards` whitelist still in prod config [redacted – card BIN/last4 data] (cleanup debt for GSS).
- Per Shannon: Fiserv approved AFT but Visa refused, so GD systems log AFT while Fiserv likely processes as ecomm (MCC 6540). Mismatch only provable via Fiserv settlement/interchange reports.
- GD is a self-processor to the networks but runs ACI BASE24 software (reconciles Pawel's "ACI is not our processor").
- Datadog tip: quote UUIDs as bare strings; `@field` only for faceted attributes.

## Decisions
- Treat credential as "key" and account as "lockbox"; proposal is a Toast-only private-label Visa virtual card tokenized to device wallets, leaving the account untouched.

## Open questions
- Does a merchant-restricted private-label Visa card preserve closed-loop status? Route to Legal/Compliance.
- Confirm actual Fiserv processing (AFT vs ecomm) via settlement data; whether to clean up AFT config.
- Visa auth/tokenization path for a GD-issued Visa card and economics vs PNT (ask Pawel).

## Next steps
- Ask Pawel for the open-loop Visa auth flow and token service enablement path.
- Draft key/lockbox explainer for business and Compliance.
- Flag the AFT/ecomm mismatch and stale whitelist to GSS engineering.

## Key sources
- https://greendot.atlassian.net/wiki/spaces/BAASPO/pages/1355810067/KT+-+Toast+AccountGiftCard+Processor
- https://greendot.atlassian.net/wiki/spaces/BAASPO/pages/340722392/Toast+NPNR+technical+design
- https://greendot.atlassian.net/wiki/spaces/PROD/pages/834928752/Toast+Phase+2
- https://greendot.atlassian.net/wiki/spaces/QABEMM/pages/2579726383/GBOS-207188+Spike+IFT+Investigate+IFT+and+document+the+Flow
- https://greendot.atlassian.net/wiki/spaces/CBS/pages/95986240/TOAST+Systems+Integration+and+Workflows

## Resume prompt
> I'm working on Toast Cash architecture at Green Dot. One BaaS account/purse per user; spend auth via PNT API (GBOS-RH-RequestHandler to ACI BASE24-EPS over ISO 8583) checks aggregate balance only; FIFO "gift cards" are rebuilt retroactively by GBOS-BAT-PnReconciliation to support the non-reloadable KYC exemption. Loads route via GSS GlobalFundTransfer/ExternalCardTransfer to Fiserv under `toastaft` AFT config, but Visa refused AFT, so Fiserv likely processes as ecomm. GD is a network self-processor running ACI BASE24. Goal: show a Toast-only private-label Visa virtual card tokenized to Apple Pay can be added without changing the account; compliance determination is pending with Legal/Compliance. Please help me with: [next task].
