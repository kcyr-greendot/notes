---
type: claude-summary
session_id: local_4ddb5954-df88-41c0-8e47-1fd61b35837f
session_title: Embedded finance retail positioning
last_synced: 2026-10-12
status: active
tags: [claude-summary, embedded-finance, retail-partners, closed-loop-wallet]
---
# Embedded Finance Retail Partner Positioning

## Context
Prep and live support for an August 2026 offsite on embedded finance for Green Dot retail partners (e.g., embedded wallet for Meijer, full DDA for 7-Eleven). Core question: how to position what GD can legitimately deliver in the next 6 months with little to no platform dev. Audience: Retail Sales Execution team, product, BD.

## Artifacts
- Whitepaper: "Retailer embedded account white paper draft August 2026 v1" (tdriggs OneDrive; uploaded as PDF)
- Offsite agenda/tracker: "Embedded_Account_Overview_offsite 8_7_26.xlsx" (RetailSalesExecutionTeam SharePoint)
- GTM deck: "Retailer embedded account solution and implementation considerations offsite 081326.pptx"
- Meijer deck (July 2026) found via SharePoint search
- "Onboarding_Form_GD Program_03.26.xlsm" (Perqs implementation onboarding config form, from Perqs product lead)

## Key findings
- Karl corrected several overstatements; what actually exists today: GDN cash loads at retail; GD-branded DDA (GBOS/Arc); a Toast-style headless closed-loop no-KYC account that is a bespoke "hack" with no packaged GTM.
- NOT built (only proposals/mockups in partner decks): one-tap linking of existing GD accounts to partner loyalty; any loyalty/rewards integration; EBT/Forage balance display.
- GD is shifting from white-label apps to GD-branded experiences: lose partner brand connection, gain faster onboarding, dev pace, brand trust.
- Whitepaper reframe: closed-loop wallet is "a customer-identification and prefunding project," not a payments project. Barcode is the right US POS answer; tap-to-pay is roadmap.
- GTM deck POS auth options: Direct GD Retail API 2.0 (PNT) 9-12+ mo, zero per-txn cost; Visa/MC private label 3-6 mo, interchange applies; Incomm/Blackhawk gift rails 4-6 mo. Integration models: GD Hosted webview (only credible 6-mo option), Embedded SDK 9-12 mo, headless API 12-18 mo.
- Partner status from tracker: Walgreens most active (loyalty platform in 12-18 mo redesign); CVS consumer interest strong, leadership not bought in, Universal Reload Amendment 3 investment at risk; 7-Eleven has competing existing wallet, franchise settlement/breakage allocation is real blocker; Dollar General best fit but Ibotta/DG Cash Back contracting complexity; Meijer BHN agency agreement is a commercial barrier.
- Compliance flag: P2P in a closed-loop wallet independently triggers CFPB prepaid account status; needs Legal before committing.
- Perqs onboarding form (25 config domains) shows per-partner configurability without dev: product code/name (Perqs product 41008), distinct card stock, multiple plan tiers (Tier1/Tier2/Employee) with own fee and limit groups, MMF and waiver thresholds, overdraft toggle, Cash Back Rewards toggle, per-device feature flags, PartnerPromo/PartnerPromoReversal adjustments (batch ledger credits for partner-funded rewards), retail fee splits, event webhooks (AccountUpdated, Transaction, etc.).
- Form confirms SupportPoints = False and SupportAmm = False for all products; no closed-loop scope in the form.

## Decisions
- Strategy template (Karl): Phase 1 compelling, easy closed-loop offering mixing promotional and customer-funded spend inside the brand's existing app; Phase 2 roadmap to GD financial services tied to partner program but under GD brand (e.g., Meijer-branded debit card with loyalty tie-ins, serviced via GD app/web).
- Honest DDA pitch today: partner-branded GD debit card with configurable fees/tiers/CBR, PartnerPromo credits, and webhooks; loyalty integration is the partner's build.

## Open questions
- What is the minimum viable productized version of the Toast-like closed-loop capability? (product team)
- Can partner branding appear in GD-branded onboarding? Per-partner rewards beyond CBR without dev? (product)
- P2P in closed-loop wallet regulatory treatment (Legal/Compliance)
- 7-Eleven: GD as bank vs. powering their stored-value program; KYC tolerance; who owns loyalty integration.

## Next steps
- Clarify GD-branded DDA customization limits with product, using Perqs form as baseline
- Define MVP and GTM for productized closed-loop wallet
- Optional: turn findings into one-pager/talking points

## Key sources
- Internal docs listed under Artifacts (no external links cited)

## Resume prompt
> I'm Karl (PSE, Green Dot). We're positioning embedded finance for retail partners (Meijer, 7-Eleven, Walgreens, CVS, Dollar General) with a 6-month, near-zero-dev constraint. Reality today: GDN cash loads, GD-branded DDA on GBOS/Arc, and a Toast-style headless closed-loop no-KYC account that isn't packaged. No loyalty integration, no one-tap account linking, no EBT/Forage display. Strategy: Phase 1 closed-loop wallet in the partner's app (promo + customer-funded); Phase 2 partner-branded GD debit card serviced in GD app. Perqs onboarding form shows configurable product code, card stock, tiers, MMF/waivers, CBR, OD, PartnerPromo credits, webhooks; SupportPoints and AMM are off. Open: closed-loop MVP definition, DDA brand customization limits, P2P compliance. Please help me with: [next task].
