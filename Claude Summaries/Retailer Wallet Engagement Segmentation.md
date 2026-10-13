---
type: claude-summary
session_id: local_f2e6bb0a-0125-41b6-a5bd-88348adea60e
session_title: Retailer wallet engagement segmentation
last_synced: 2026-10-12
status: active
tags: [claude-summary, retail-loyalty, branded-wallet, customer-segmentation]
---
# Retailer Wallet Engagement Segmentation

## Context
Karl brainstormed the retailer value proposition for a branded wallet and a DDA/prepaid cross-sell. He built a segmentation of loyalty engagement levels (0/25/50/75/100%) with columns for obstacles and for the value of moving customers up. GD's two offerings are (1) a closed-loop wallet with a payment instrument (GD private network and/or private-label Visa tokenized into device wallets) and (2) a full GD debit card with retailer rewards integration and a complimentary retailer premium subscription. The goal is to align customer, retailer and GD incentives, with the retailer serving as a DD/DDA acquisition channel.

## Artifacts
- ARC white paper (project file) used as the base reference
- Offsite meeting transcript (project file). ASR speaker attribution is unreliable.
- Research synthesis document, written and presented in the session outputs (file name not visible in the transcript)
- Five parallel research sub-agents (the first run hit an API 529 error and was resumed)

## Key findings
- **Splitting zero-engagement customers:** Separate privacy-averse customers (will not convert) from effort-averse ones (can be captured passively by a card-linked program). Separate the same way between people who will never download an app on principle and people who will once there is a compelling reason. Add a dormant tier between 0% and 25%: enrolled but unaware, with consent already in place, so it can be reactivated.
- **Use two axes, not one ladder:** Loyalty engagement (the retailer's axis) and payment/financial engagement (GD's axis) are close to independent. No published framework uses a single composite tier. Bond's 2026 report with Visa describes five overlapping populations, warns about "artificial loyalty," and measures card-linked behavior separately. No framework tiers customers by funded balance or tender, so that is open white space.
- **The load side is GD's strongest lever:** ACH and cash loads cost fractions of a cent, versus about 1.75% + $0.20 for a card-funded load. Durable programs subsidize the load rather than the tender (Starbucks restructured this way in March 2026). GD owns ACH, RTP/FedNow, DD and the roughly 90,000-location cash network.
- **The second reload is the cliff:** About 75% of Dollar General reloaders reload only once. Paytronix's c-store benchmark (joined, then 2nd visit, then 4th visit, with a 90-day gate) shows the same drop-off, and gasoline-brand active rates fell 22 points while membership grew. Threshold auto-reload is the highest-value feature, and no one publishes adoption rates for it.
- **Tap and loyalty:** Apple VAS already supports one-tap payment plus loyalty on iOS, with the pass appended to the Apple Pay transaction. Google has no equivalent. The real constraint is terminal/POS certification. A true closed-loop NFC tap on iOS needs Apple's NFC & SE Platform agreement, so in practice closed-loop means a barcode in an app. Private-label Visa in Apple Pay suits the no-app segment. Kroger reaches over 95% loyalty tethering with plastic, so sell one-tap on convenience and economics, not identification rate.
- **Metrics:** Scan rate and wallet tender share predict value. Enrollment does not; 7-Eleven's 100M members is a vanity number.
- **Corrections:** The $381 Chime CAC figure is not a Chime disclosure (no EDGAR source). Dave's $19 counts gross signups. GD's gap between DD-active and total-active decline varies by quarter and is not structural (figures are in the GD quarterly decks).
- **Gold Pass mechanic (from the offsite):** The retailer bills the customer and GD credits it back in the same cycle, gated on qualifying DD, with the cost shared. This avoids paying for customers who have churned. Framing from the offsite: the wallet is an acquisition channel, not a P&L, so "start with the card, not the wallet."
- **New targets:** Albertsons has 51.2M members and no card product. Kroger dropped its prepaid Visa in August 2024, and GO2bank is now on its Money Services shelf.

## Decisions
- Restructure the matrix into two axes. Add columns for the product that serves the tier, the mechanic, who funds it (retailer margin, GD interchange or displaced payment cost), the proof metric, and who counts the tier as a win.
- Treat private-label Visa tokenization and closed-loop barcode as separate offerings.

## Open questions
- Are the wallet and card tracks both-or-either? This changes the matrix structure.
- Is the Gold Pass cost split negotiable per deal?
- Is it feasible to redirect platform cash-back into retailer loyalty currency? That would be an earn-side lever GD controls on its own. Route to Product.
- Should the debit card be GD-branded or co-branded, and should it live in a separate app with deep links? The paper favors that, given the Target Circle Reloadable and Tesco/Sainsbury's retrenchments.

## Next steps
- Answer the three open questions above, then build the two-axis matrix.
- Have someone who attended the offsite check the transcript attributions.
- Validate the per-tier mechanics against Kroger, Target and Walmart+ approaches.

## Key sources
- Bond Brand Loyalty 2026 report (with Visa)
- Paytronix c-store loyalty benchmark
- Apple VAS / Apple Pay loyalty pass documentation

## Resume prompt
> I'm designing the retailer value proposition for a GD branded wallet and debit card cross-sell. Research changed my single 0-100% loyalty ladder into two axes: loyalty engagement, which the retailer controls, and payment/financial engagement, which GD controls through load rails, DD and the cash network. Key insights: the second reload is the critical cliff (about 75% of DG reloaders reload only once), auto-reload is the top feature, Apple VAS one-tap works but terminal certification is the constraint, and Gold Pass works as a DD-gated same-cycle credit-back. Open items: whether wallet and card are both-or-either, whether the Gold Pass split is negotiable, and whether cash-back can be redirected into retailer loyalty currency. Possible targets: Albertsons and Kroger. Please help me with: [next task].
