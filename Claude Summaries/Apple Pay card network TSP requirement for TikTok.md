---
type: claude-summary
session_id: local_cf2626bc-b936-438b-bfe2-1d3feb573dcf
session_title: Apple Pay card network requirements
last_synced: 2026-10-12
status: active
tags: [claude-summary, apple-pay, tokenization, tiktok]
---
# Apple Pay card network TSP requirement for TikTok

## Context
TikTok (contact referenced as Victoria) asked why their card must go through a card network to be in Apple Pay. Karl had researched this before for Toast. The session sourced documentation and refined an external statement for TikTok.

## Artifacts
- Final statement text for TikTok (drafted by Karl and reviewed; summarized below)

## Key findings
- Apple Pay provisioning flow: issuer -> network TSP (Visa VTS / Mastercard MDES) -> Apple, which issues a device token (DPAN). Transactions route over network rails.
- Apple Issuer Functional Requirements v3.5 says: "Apple does not provide tokenization services... issuers can use their own tokenization services or integrate with tokenization systems from payment schemes or from qualified third party providers," and "Any Card Issuer that integrates with a certified third party that offers tokenization technology can offer Apple Pay." So networks are not the only theoretical TSPs.
- In practice, all Apple Pay TSPs are networks or national-scale schemes (China UnionPay, Interac, eftpos). Becoming one requires an EMVCo TSP Code ($11,500, and EMVCo says that alone is not sufficient), Apple certification and contract, and full tokenization infrastructure. This is not commercially viable for a BaaS issuer.
- `privateLabel` in Apple's supported networks is a card-type designation for store-branded cards. They still use a network TSP; Mastercard was first to tokenize private label cards in 2015. Apple Card runs on Mastercard.
- Apple Wallet passes can do NFC via the VAS protocol, but only at VAS-certified readers, not as Apple Pay at standard contactless terminals. Transit (e.g., MTA) is a carve-out with no payment-card equivalent.

## Decisions
- Final statement: Apple certifies only network-scale TSPs (link to supported networks); passes can use NFC via VAS but not the Apple Pay experience; GD cards are Visa/Mastercard affiliated and support VTS/MDES on all programs; GD is partnering with networks on Apple Pay for private-label closed-loop programs; no path exists for a fully private, non-network card.
- Edits applied: replaced "exclusive access" with "designated tokenization infrastructure for Apple Pay"; corrected the NFC claim to VAS; fixed the "and and" typo.
- Karl says the private-label partnering claim is accurate but will clear it with internal stakeholders before sending.

## Open questions
- Internal sign-off on the private-label Apple Pay claim (Karl to route).

## Next steps
- Get internal stakeholder approval, then send the statement to TikTok.

## Key sources
- https://register-media.cdn-apple.com/Apple_Pay_Partner_Docs/Apple_Pay_Specifications-Issuer_Functional_Requirements_Version_3.5.pdf
- https://developer.apple.com/documentation/applepayontheweb/supported-networks
- https://developer.visa.com/use-cases/blog/in-app-provisioning-and-digital-tokenization
- https://www.emvco.com/processes/token-service-provider-registration-programme-2/
- https://www.businesswire.com/news/home/20150615005232/en/MasterCard-Becomes-First-Network-to-Add-Tokenization-Support-for-Private-Label-Credit-Cards-for-Use-in-Digital-Wallets

## Resume prompt
> I'm Karl (PSE, Green Dot). TikTok asked why Apple Pay requires a card network. Research: Apple's Issuer Functional Requirements v3.5 allows "certified third party" TSPs, but in practice only networks and national schemes (Visa VTS, Mastercard MDES, UnionPay, Interac) are certified. Becoming a TSP needs an EMVCo TSP code, Apple certification, and full token infrastructure. privateLabel is a card type that still uses a network TSP. Wallet passes can do NFC via VAS but not Apple Pay. I finalized a 3-paragraph statement (GD cards support VTS/MDES; GD partnering with networks on private-label Apple Pay; no path for non-network cards), pending internal sign-off on the private-label claim. Please help me with: [next task].
