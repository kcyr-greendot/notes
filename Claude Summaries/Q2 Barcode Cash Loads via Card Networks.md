---
type: claude-summary
session_id: local_0743e4be-2ec2-4623-8361-46f6bfd4d40d
session_title: Green Dot barcode cash loads integration
last_synced: 2026-10-12
status: active
tags: [claude-summary, q2, cash-loads, gdn]
---
# Q2 Barcode Cash Loads via Card Networks
## Context
Q2 wants barcode cash loads that push funds to any debit or prepaid card over the card networks, instead of a retail consumption (Auth/Commit) integration. This is shown on slides 28–30 of the GDN Use Case Flows deck. Karl researched precedent and where the capability might live in code, since the public v2 barcode API has no PAN or expiration fields.

## Artifacts
- [GDN Use Case Flows – Simple Version w Funds flow](https://greendot365.sharepoint.com/sites/GDNPartners/Shared%20Documents/GDN%20GTM%20Planning/5.%20Product%20Marketing%20(BD%20Sell%20Sheets,%20Case%20Studies,%20Simplified%20Flows)/GDN%20Use%20Case%20Flows%20-%20Simple%20Version%20w%20Funds%20flow.pptx). The server copy of the linked "Simple Version" deck only had 13 slides; confirm they match slides 28–30.
- [MMGDN-4862 (Jira)](https://greendot.atlassian.net/browse/MMGDN-4862)
- The Q2 Solution Overview in Karl's folder is outdated for this model: it describes Q2 answering Auth requests.

## Key findings
- **Deck model:**
  - The partner sends the card number, expiration, name and ZIP when generating the barcode.
  - On scan, Green Dot looks up the card, runs limit checks and pushes funds via Mastercard Send or Visa Direct. There is no Auth/Commit call to Q2.
  - Funds arrive in 30 minutes or less, versus 15 for a direct integration. Green Dot settles with the network, not Q2.
- **Precedent is swipe-based "POB" (Point of Banking):**
  - Q2 already has a live POB program (Credit Karma via Q2) using Mastercard Send, or Visa Direct depending on BIN (GSS-46281, 2024).
  - Tumoni "Processor Lookup" POB (MMGDN-4862, July 2025) was withdrawn. In that model Green Dot calls Q2 at transaction time for the name, ZIP and expiry tied to a card number. That could be a cleaner barcode design.
  - MoneyPak AnyDebit is the closest code-to-card precedent.
- **No evidence a barcode-to-card push has ever gone live.**
- **Mastercard rePower was retired 4/1/2026.** The live rails are MC Send and Visa Direct.
- **Risks:**
  - PCI scope: an undocumented endpoint taking card numbers. Options are raw PAN, link the card once and reuse a token (like the disbursement Link ID flow), or Processor Lookup.
  - Voids become reversals that can fail. This caused rePower settlement variances in 2021 and was flagged in the 2018 AnyDebit research.
  - BSA/AML and OFAC data needs should be confirmed with Compliance.
- **Code trail to search:**
  - Swipe path: `gss.rtlapp.reloadprocessor` → `gss.echsvc.swipeapi` → `lgy.soav3.cardtransfer`
  - Repo `Green-Dot-Corporation/MMGDN-SOAV3-CardTransfer`: the requestapplicationreferencetoken endpoint and the MCSendP2POnly/VisaDirectOnly rules
  - Perforce: `//DotNet/current/MMS/Service/CardTransfer/V1/` and `//GSS/Trunk/ECHAPP/Services/ECashProcessor/`
  - Tokenizer: `tknsvc/GDTokenizer/v1/Pan/Tokenize`
  - GSS eCash barcode service (behind `POST /v2/Barcode`); GDFNPartnerGateway
  - Config: `MMN.dbo.Bin.BinConfiguration` (FundingBusinessRule), `MMN.dbo.ProgramFundTransferService` (Q2 is present), and the `GssBarcodePattern` setting (MMGDN-266)
  - DART `DisbursementTransferRequest`
  - QA suites: `qa-readyapi-BE-MoneyMovement` (GSS_SwipeAPI Transfer-*) and `qa-readyapi-BE-RetailAPI`

## Decisions
- None formal. Research and exploration only.

## Open questions
- Does a barcode-to-PAN path exist? Ask Srikala Tangirala, Erik Dunn or Ashwin Arun Poothatta.
- Which card-data approach is preferred: raw PAN, token or Processor Lookup? (Engineering)
- Compliance data requirements.
- MMGDN-4862 appears to contain plaintext partner credentials and secret keys. Flag to InfoSec (security@greendot.com) so they can be rotated and removed. Not copied here.

## Next steps
- Search the code using the trail above. A GitHub connector would let Claude search for you.
- Update the Q2 Solution Overview once the model is confirmed.
- Report the MMGDN-4862 credential exposure to InfoSec.

## Key sources
- [GSS-46281 Visa Direct for GSS POB](https://greendot.atlassian.net/wiki/spaces/QABEMM/pages/74972672/GSS-46281+Spike+the+flow+to+add+Visa+Direct+as+a+processor+for+GSS+POB)
- [POB – FeatureMap](https://greendot.atlassian.net/wiki/spaces/QABEMM/pages/74971180/POB+-+FeatureMap)
- [Non-WMT PoB](https://greendot.atlassian.net/wiki/spaces/PROD/pages/94441977/Non-WMT+PoB)
- [RETIRED – MasterCard RePower](https://greendot.atlassian.net/wiki/spaces/NOC/pages/77702388/RETIRED+-+MasterCard+RePower+MC+Repower)
- [AnyDebit POS Swipe research](https://greendot.atlassian.net/wiki/spaces/PROD/pages/94439468/AnyDebit+POS+Swipe+Research+to+See+What+Changes+are+Needed+to+Support+AnyDebit+POS+Swipe)

## Resume prompt
> Q2 wants barcode cash loads pushed to any debit card via MC Send or Visa Direct, without an Auth/Commit integration (GDN Use Case Flows slides 28–30). Precedent so far:
> - Q2's live swipe POB (Credit Karma, GSS-46281)
> - Withdrawn Tumoni Processor Lookup (MMGDN-4862)
> - MoneyPak AnyDebit
>
> No proof a barcode version has gone live. Risks: PCI scope, voids becoming reversals, Compliance data needs. I'm tracing code through CardTransfer, the GSS eCash barcode service and the MMN config tables. Please help me with: [next task].
