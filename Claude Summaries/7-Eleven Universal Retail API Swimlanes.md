---
type: claude-summary
session_id: local_a79a61e3-0db9-4463-9a34-5f9e88d59768
session_title: 7-Eleven retail integrations
last_synced: 2026-10-12
status: active
tags: [claude-summary, 7-eleven, retail-api, universal-reload]
---
# 7-Eleven Universal Retail API Swimlanes

## Context
Karl asked for a summary of Taylor's Miro board on 7-Eleven retail integrations. Claude in Chrome was not connected, so Karl uploaded a PDF export instead. The document is a swimlane diagram dated March 4, 2026 covering 7-Eleven POS, Green Dot, Customer, Associate and Card Network.

## Artifacts
- Miro board (Taylor): https://miro.com/app/board/uXjVHsBz0QI=/
- PDF: "7-Eleven Universal Retail API - Phase 1 & 2 Swimlanes (03042026).pdf" (uploaded to the session)

## Key findings
- Authentication: Microsoft OAuth2. Health check is `GET /system/ping`.
- Use Case 1, swipe reloads:
  - GDN card: `POST /card/details` confirms GDN membership and validates the amount, then `POST /reload/execute` completes the reload.
  - Non-GDN card: `/card/details` returns `InvalidAccount`, then Green Dot attempts a "universal reload" via `POST /pointofbanking/payment` using Mastercard Send or Visa Direct push. Green Dot doesn't know whether the card is loadable until the push is attempted.
- Use Case 2, barcode reloads: the customer shows a dynamic single-use barcode. `POST /barcode/details` validates it and looks up the account, then `POST /barcode/payment` executes the load.
- Use Case 3, retail card sales (MoneyPak): `GET /package/details` returns cost and limits, then `POST /package/sale` marks the card sold and returns activation instructions printed on the receipt.
- Big picture: the new Retail API replaces 7-Eleven's legacy integration. Universal reload to non-GDN cards over network push rails is a net-new capability.

## Decisions
None recorded.

## Open questions
- How should non-GDN universal reload failures (card not push-eligible) be handled and messaged at the POS?
- Which use cases are Phase 1 and which are Phase 2? This was not broken out in the summary.

## Next steps
- Review the phasing and the error-handling paths with Taylor.
- Connect Claude in Chrome if direct Miro reads are needed in future.

## Key sources
- Miro board above (internal)

## Resume prompt
> I'm Karl (PSE, Green Dot). Taylor's swimlanes (Mar 4, 2026) for the 7-Eleven Universal Retail API cover three use cases. (1) Swipe reload: GDN cards go through /card/details then /reload/execute; non-GDN cards get InvalidAccount, then a universal reload via /pointofbanking/payment over Mastercard Send / Visa Direct. (2) Barcode reload: /barcode/details then /barcode/payment. (3) MoneyPak sale: /package/details then /package/sale. Auth is Microsoft OAuth2, with /system/ping as the health check. Open items: phase 1 vs. 2 split, handling of non-loadable non-GDN cards. Please help me with: [next task].
