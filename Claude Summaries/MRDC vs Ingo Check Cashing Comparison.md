---
type: claude-summary
session_id: local_e1d62547-5bbb-4691-b733-c2c114c6ed8f
session_title: MRDC and Ingo check cashing comparison
last_synced: 2026-10-12
status: active
tags: [claude-summary, mrdc, ingo, check-deposit]
---
# MRDC vs Ingo Check Cashing Comparison

## Context
Karl asked for a sales-oriented comparison of Green Dot's MRDC (vSoft model) and Ingo check cashing: what they share, how they differ and which use cases fit each. The answer drew on Product team Confluence pages and is meant for partner and deal conversations.

## Artifacts
- vSoft Model (Original/Legacy MRDC): https://greendot.atlassian.net/wiki/spaces/PROD/pages/2868150273
- Ingo SDK Update PRD: https://greendot.atlassian.net/wiki/spaces/PROD/pages/1303021644/Ingo+SDK+Update
- Mobile Check Deposit (MRDC) by Ingo: https://greendot.atlassian.net/wiki/spaces/CBS/pages/95981585/Mobile+Check+Deposit+MRDC+by+Ingo
- MRDC Feature Map: https://greendot.atlassian.net/wiki/spaces/QABEMM/pages/74974726/MRDC+-+Feature+Map

## Key findings
- What they share: in both, the customer photographs the check front and back in the app, and Mitek handles capture and duplicate detection. Both require a verified customer with an active card. Internally, both are often called "MRDC" (the Ingo flow is labeled "Cash a Check (MRDC)" in the app).
- MRDC (vSoft):
  - True remote deposit. Green Dot carries fraud and return risk.
  - MRDC-V3 scoring: OFAC, AML, IDV, payroll direct deposit history (70 days, at least 4 deposits) and a recent card-present purchase.
  - Limits: 3 checks or $3K per day. Anything over $1K goes to manual review.
  - Funds are instant if the check is under 75% of the customer's lowest recent payroll deposit; otherwise a 5-day hold.
  - Clears through Green Dot's Jaguar system (image file to the Fed).
  - No consumer fee. Green Dot handles support.
  - Users: GO2bank, Green Dot direct, Wealthfront, Amazon Flex.
- Ingo:
  - Digital check cashing in which Ingo buys the check and absorbs fraud and return losses.
  - Ingo sets the limits. Green Dot requires only an active personalized card.
  - Funds "In Minutes" for a fee, or free in 10 days. The fee is revenue-shared; the PRD projects more than $600K in 2026 contribution.
  - Integrated via the Ingo SDK and APIs. Green Dot Care hands check-cashing questions to Ingo.
  - Not available in NY.
  - Users: GO2bank, Walmart MoneyCard.
- Caveats:
  - Exposing Ingo to BaaS partners is a PRD requirement but is not confirmed live.
  - The current Ingo SDK is unsupported, and Android loses the feature from Aug 2026 without the upgrade.
  - The vSoft page's "Legacy" label suggests a newer MRDC model may exist.

## Decisions
- Positioning reframe, which Karl accepted: MRDC is not "more robust," just more gated. It is a deposit feature for established account holders with direct deposit. Ingo is a fast-cash and risk-transfer feature for new or thin-history customers, urgent needs, or unproven partner bases. For full neobanks, pitch both.
- Describe customers by need (e.g., "no direct deposit history yet"), not by market tier.

## Open questions
- Is Ingo available to BaaS partners via API/Developer Portal yet? (Product: Chrissy Cagle / Smitha Jonnala)
- What is the status of the Ingo SDK upgrade ahead of the Aug 2026 Android deadline? (Product)
- Is there a newer MRDC model replacing vSoft? (Product)

## Next steps
- Optional: turn this into a one-page battlecard, or add it to a partner's Program Discovery doc when a deal comes up.

## Key sources
- The Confluence pages listed under Artifacts

## Resume prompt
> I'm Karl (PSE, Green Dot). I compared MRDC (vSoft) and Ingo check cashing. MRDC: Green Dot carries the risk; MRDC-V3 scoring requires payroll direct deposit history (70 days, at least 4 deposits); limits are 3 checks or $3K per day with manual review over $1K; free, and instant if under 75% of the lowest payroll deposit, otherwise a 5-day hold. Ingo: Ingo buys the check and absorbs losses; fee for "In Minutes" or free in 10 days; revenue share projected over $600K in 2026; not in NY. Positioning: MRDC for established direct deposit customers, Ingo for fast cash and risk transfer, both for full neobanks. Open with Product (Chrissy Cagle / Smitha Jonnala): Ingo for BaaS partners, SDK upgrade before the Aug 2026 Android deadline, newer MRDC model. Please help me with: [building a battlecard].
