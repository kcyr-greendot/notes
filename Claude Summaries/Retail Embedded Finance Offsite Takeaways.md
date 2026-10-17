---
type: claude-summary
session_id: local_3c43ba75-b5f9-4afd-afc2-9435a293e2d8
session_title: Retail embedded finance offsite summary
last_synced: 2026-10-16
status: active
tags: [claude-summary, retail-embedded-finance, closed-loop-wallet, product-strategy]
---
# Retail Embedded Finance Offsite: PSE Takeaways

## Context
Karl attended the retailer embedded finance offsite on Aug 13, 2026 remotely and had a poor experience. He uploaded a transcript that was low quality and mostly didn't say who was speaking. He asked for takeaways from a PSE point of view to inform product positioning and roadmap investment. He then proposed three product ideas and four technical challenges for Claude to sort against the offsite themes.

## Artifacts
- An uploaded transcript: `transcript from retail embedded finance offsite 08132026.docx`. Local only.
- No Confluence pages, Jira issues or files were created.

## Key findings (offsite)
- **Who spoke:** Crystal Bryant Minter (primary voice), David Kring, Shane Reekstin and Adam Evans.
- **Retailers discussed:** Walgreens, CVS, Dollar General, 7-Eleven, Meijer.
- **GD-branded beats white label.** Only Walmart and Target made white-label retailer cards work. Consumers trust retailers to sell them goods, not to be their bank.
- **The wallet is an acquisition channel, not a profit center** (compared to Apple Pay and Samsung Pay). The goal is acquiring direct-deposit customers.
- **Reward tiers:**
  - A base cash-back reward on in-store spend, funded by the retailer.
  - A higher reward when the customer meets a monthly load threshold. A lower threshold was favored for the DG customer base.
  - The subscription fee waived when the customer meets the load threshold (Go2bank precedent).
  - The benefits are presented as coming from the retailer. Keep it simple.
- **Off-rack card that enrolls the buyer in the retailer's loyalty program.** This was Kring's idea: buying a card off the rack triggers or links loyalty enrollment, which gives the retailer a reason to sell GD cards. 7-Eleven has heard the pitch.
- **Private label Visa/Mastercard is favored** because it needs no POS changes. Crystal is following up.
- **Economics:** three-sided (customer, retailer, GD). Levers include interchange savings put toward rewards, breakage (whether to share it as with Walmart), a retailer marketing commitment at launch, and a per-account launch bounty. Specific figures: [redacted – non-public financial data].
- **Gaps on the roadmap:**
  - Per-retailer UI configuration in the GD app.
  - Linking off-rack cards to retailer loyalty programs.
  - Closed-loop load routing and ACI integration.

## Key findings (Karl's product family)
1. **Rewards wallet on network private label.** Add tap-to-pay and Apple Pay virtual cards to existing wallets such as 7Rewards and mPerks. Rewards and eGift funds sit together in a KYC-exempt prepaid ledger, with no POS integration needed. This is the entry point.
2. **Off-rack co-branded GD Bank card** (for example, with 7-Eleven branding). It is linked to the retailer's loyalty account and adds premium perks such as a points boost. This is the full-DDA step up.
3. **Retailer subscription included for direct-deposit customers** (for example, DG+ or 7-Eleven Gold Pass). Claude suggested the retailer comp the subscription, paid for out of interchange savings, rather than GD crediting the fee back.

How Claude worked the challenges:
- **The current closed-loop wallet (the Toast Cash solution) is a hack.** Moving to network private label fixes it. Reframe the product as a "preferred spend" card.
- **Showing rewards inside GD:** a configurable rewards widget in the GD app with a standard data contract each retailer implements.
- **Earn-side data:** a daily batch file of qualifying transactions on day one. Target state is a real-time webhook when a transaction posts.
- **Holy grail (one swipe drawing on both the DDA and rewards balances):**
  - Near term: convert rewards to a real-time credit on the GD account at authorization, using the same "charge and credit" plumbing discussed for fee waivers.
  - V2: true split tender, which needs POS changes on the retailer side.

## Decisions
- Present the three ideas as a funnel: wallet upgrade, then co-branded DDA, then the direct-deposit subscription perk for retention.
- Lead with real-time earn as the target and batch as the day-one implementation.
- Lead with pre-conversion for combined spend; don't promise split tender on day one.

## Open questions
- What engineering would need to build for closed-loop wallet versus private label V/MC (to ACI and engineering).
- Whether private label is feasible (Crystal Bryant Minter is following up).
- Whether to share breakage with retailers.
- How to show rewards generically across partners.

## Next steps
- Validate the private label build delta and the ACI routing with engineering.
- Create a template for a three-sided economic model for retailer pitches.
- Feed this into the closed-loop wallet product discovery KR in H2 (see [[2026 PSE OKRs H1 Review and H2 Plan]]).
- Draft a widget/data contract spec for showing rewards in the app and for the earn-side feed.

## Key sources
- The internal offsite transcript from Aug 13, 2026. It is not stored here.

## Resume prompt
> I'm continuing work on the retail embedded finance strategy coming out of the Aug 13, 2026 offsite. The offsite concluded that GD-branded beats white label, the wallet is a DD acquisition channel, private label V/MC needs no POS changes, and economics have to work for customer, retailer and GD.
> My product family:
> (1) network private label tap-to-pay upgrade for retailer rewards wallets (7Rewards, mPerks) on a KYC-exempt prepaid ledger;
> (2) an off-rack co-branded GD Bank card linked to retailer loyalty;
> (3) a retailer subscription comped for DD customers.
> Proposed approaches: a configurable rewards widget in the GD app, a batch earn feed moving to a real-time webhook, and real-time rewards-to-balance credit at authorization before any split tender.
> Open: build delta versus the Toast Cash closed-loop setup, ACI routing, and breakage sharing. Please help me with: [next task].
