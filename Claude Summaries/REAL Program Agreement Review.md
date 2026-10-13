---
type: claude-summary
session_id: local_a416a157-80dc-409b-b4f3-46c6b6161dfd
session_title: Real - Green Dot contract
last_synced: 2026-10-12
status: active
tags: [claude-summary, baas-contract, debit-networks, program-discovery]
---
# REAL Program Agreement Review

## Context
Karl reviewed the draft REAL / Green Dot Program Agreement (REAL draft 8/14/26) to answer two questions from Ray Taddeo (dedicated BIN; client selection of alternative debit networks). The thread then summarized the contract's program requirements, compared them with the January 2026 Program Discovery, and published a revised discovery page in the PSE Confluence space.

## Artifacts
- Contract draft: "REAL GreenDot Program Agreement (REAL draft 8_14_26).docx" (Ray Taddeo's OneDrive, plus an uploaded copy)
- Partner Implementation Checklist (July 2026), Basecamp SharePoint
- Confluence v1 (renamed): Real - Consumer DDA - Program Discovery (v1 - Initial Scope, Dec 2025), page 1755643905
- Confluence v2 (new): Real - Consumer DDA - Program Discovery (v2 - Revised per Contract Draft, Aug 2026), page 2766798876. Karl made some small corrections after publishing.
- Skill used: gd-program-discovery

## Key findings
- **Dedicated BIN:** The draft says nothing about BINs. Volume under 10k users is not what decides it. The deciding factors are whether REAL will pay the setup and maintenance cost, whether REAL wants to keep the BIN after termination (the termination language does not cover this), and how long Visa approval takes (GDC facilitates it under Sec 4.1).
- **Alternative debit networks:** This is about Durbin/Reg II, which requires at least two unaffiliated networks. The alternative networks are PIN/EFT networks such as PULSE, STAR, NYCE and Interlink. The draft defines "Network" as Visa plus any network GD/Bank chooses, and Bank controls memberships (Sec 4.1). Ray's proposed clause would give the client that choice, which departs from standard terms.
- **Network support is undocumented:** Searches of PSE Confluence, org-wide Confluence, SharePoint, the ARC site and the developer portal found nothing on which alternative networks GD supports. The only hit was a 2019 MOTXQA QA page listing NYCE as a legacy processor. The Platform Capabilities Overview lists only Mastercard, Visa or Closed Loop as BIN network options.
- **Contract model:** Standard ARC BaaS. REAL builds the UX and integrates by API (Exhibit 7.1 is the API TOS). GDC/Bank handle KYC, issuing, ACH (GDC as ODFI), Reg E, escheatment and all customer service (Exhibit 3.5 Option 1). REAL owns marketing, PCI DSS, SOC II, InfoSec and BCP/DR (Exh 3.14(d)/(g)/(k)). Crypto and cross-border are prohibited (3.14(k)). New features need GDC approval through PAAs. The term is 4 years, and the annual minimum survives termination.
- **Commercial terms:** The note leaves out the specific fee amounts (see the contract). Pricing covers implementation, per-card and same-day ACH fees. REAL earns tiered bps on average daily balance, but Exhibit 2.1 is blank. REAL also gets 50% of Net Interchange; the full "Net" definition was cut off in the copy read. Bank pays network membership fees.
- **Changes from the Jan 2026 discovery:** UX moved from GD-hosted to REAL-built API. CS moved from REAL white-glove Tier 1 to GDC/Bank handling all CS. The crypto.com integration is now prohibited. Private Network Transactions, wire and RTP are missing. The elevated limits from discovery (around $250K balances, $50K ACH) are not addressed.

## Decisions
- Keep v1 discovery (renamed) and publish v2 reusing v1 boilerplate. Change only where requirements differ materially.
- Record the BIN and network-selection questions as open items in v2.

## Open questions
- Which PIN/EFT networks are enabled on GD Visa debit cards, and can they be set per program? Route to Product, Network/Card Ops or the bank team.
- Exhibit 2.1 is blank (bps rates and tiers). Who populates it?
- Are PNT, wire/RTP and elevated limits needed through PAAs?
- What exactly is netted out of "Net Interchange"?
- What is the scope of exclusivity under Sec 2.6 (text was truncated)?
- If REAL gets a dedicated BIN, can they take it with them after termination?

## Next steps
- Ask Product/Network Ops about alternative network support and per-partner configurability, then reply to Ray.
- Reply to Ray on the BIN question: the issue is cost and portability, not volume.
- Use the v2 open-items table as the checklist for the next call with Ray.

## Key sources
- https://greendot.atlassian.net/wiki/spaces/PSE/pages/1755643905
- https://greendot.atlassian.net/wiki/spaces/PSE/pages/2766798876
- https://greendot.atlassian.net/wiki/spaces/PSE/pages/2458550453/Platform+Capabilities+Overview

## Resume prompt
> I'm working on the REAL / Green Dot BaaS Program Agreement (REAL draft 8/14/26). It is a standard ARC BaaS deal: REAL builds the UX and integrates by API, GDC/Bank handle KYC, issuing, ACH and all CS, crypto and cross-border are prohibited, and REAL gets 50% of Net Interchange plus tiered bps (Exhibit 2.1 is still blank). Ray Taddeo asked about a dedicated BIN. My answer is that volume is not the issue; cost and post-termination portability are. He also asked about a clause letting REAL pick the alternative (PIN/EFT, Reg II) debit networks. We could not find documentation anywhere of which alternative networks GD supports. Discovery v1 (page 1755643905) and v2 (page 2766798876) are in PSE Confluence. Open items: network support and configurability, Exhibit 2.1, PNT, wire/RTP, elevated limits, and the Net Interchange definition. Please help me with: [next task].
