---
type: claude-summary
session_id: local_2efc3b6a-cc74-4031-a0b3-8855024522a7
session_title: Platform rewards and loyalty capabilities
last_synced: 2026-10-12
status: active
tags: [claude-summary, rewards-loyalty, platform-capabilities, merchant-funded-rewards]
---
# BaaS Rewards and Loyalty Capabilities

## Context
Karl asked what rewards and loyalty capabilities the GD platform supports (cash back, points, third-party integrations, per-program configuration) so he can position them in partner conversations. The summary was published as a PSE KB article. He then asked about merchant-funded rewards (Kard) and whether that was actually built.

## Artifacts
- Confluence (new): BaaS Rewards & Loyalty Capabilities, page 2739044660, a child of Platform Capabilities Overview in the PSE space
- Sources used: Platform Capabilities Overview (2458550453) and Business Overview: Cash Back Rewards (personal space page 2231042105)
- Kard one-pager, the SDEA pages, and the BaaS AGW merchant rewards API page in Confluence

## Key findings
- **Cash back is the only productized reward:** It calculates and posts automatically as cash to the balance 1 to 3 business days after settlement. ATM, quasi-cash, wallet funding, gambling and money orders are excluded.
- **Configurable per product:** Rate (5%, 2%, partner-defined such as Amscot), annual cap ($125 on GD programs; none on GD Unlimited online), eligibility and MCC exclusions, and distribution-channel restrictions (Walmart, CVS, Kroger, Walgreens 2x2 variants). Caps reset on January 1.
- **Not supported:** Points, third-party loyalty integration (airline, Epsilon and similar), merchant-specific bonus rates, tiered rewards, real-time earn notifications, referral bonuses, a rewards marketplace, and customer-controlled redemption.
- **Kard merchant-funded rewards:** The contract was signed around late 2024. GO2bank was the first program, with BaaS expansion planned (WMMC, PLS, Amazon), each subject to partner approval. The split is 40% to the customer, 25% to GD and 35% to Kard. National offers need no opt-in; local offers do. It includes real-time notifications, a merchant map SDK (50-mile radius), auto opt-out after 90 days of inactivity with a zero balance, and Kard reimbursing GD within 30 days of month-end.
- **Kard build status:** SDEA finished by March 2025. The BaaS AGW endpoint `/api/{programCode}/merchantrewards/offers/get` is documented (last updated Aug 29, 2025), but its examples point to Kard's test environment. No launch or go-live evidence was found against the Q2/Q3 2025 target. Treat it as built, with launch status unclear.
- The PERQS project (IQ Ventures, Aug 2026) is not related. Its Kard mention is ODS template boilerplate.

## Decisions
- Published the capabilities summary as its own PSE KB article, linked to the source pages.
- Do not present Kard as a live capability to partners until its status is confirmed.

## Open questions
- Is Kard live in production for GO2bank, and is it available for BaaS? Route to Smitha Jonnala (Product Owner) or the GO2bank product team.
- The offer to add a Kard section to the KB article was not yet accepted.

## Next steps
- Confirm Kard status with Smitha Jonnala.
- Once confirmed, add a merchant-funded rewards (Kard) section to page 2739044660.

## Key sources
- https://greendot.atlassian.net/wiki/spaces/PSE/pages/2739044660/BaaS+Rewards+Loyalty+Capabilities
- https://greendot.atlassian.net/wiki/spaces/PSE/pages/2458550453/Platform+Capabilities+Overview
- https://greendot.atlassian.net/wiki/spaces/~aalexscigalszky/pages/2231042105/Business+Overview+Cash+Back+Rewards
- http://getkard.com/

## Resume prompt
> I'm documenting GD platform rewards and loyalty capabilities for PSE. Cash back is the only productized reward. It is configurable per product (rate, annual cap, eligibility/MCC, channel), and there are no points, tiers, third-party loyalty integrations or marketplace. The summary is published at PSE page 2739044660. Merchant-funded rewards through Kard (40/25/35 split, GO2bank first, BaaS later with partner approval) has a documented AGW API endpoint, but launch status is unclear because the docs still reference Kard's test environment. Next: confirm Kard status with Smitha Jonnala and add a Kard section to the KB article. Please help me with: [next task].
