---
type: claude-summary
session_id: local_fcdd69c2-f341-4f35-8c1b-52645b63cced
session_title: 2026 career goals and OKRs
last_synced: 2026-10-16
status: active
tags: [claude-summary, okrs, pse-strategy, planning]
---
# 2026 PSE OKRs: H1 Review and H2 Plan

## Context
Karl wanted concrete goals for the rest of 2026 so Product Sales Engineering (PSE) keeps moving forward while the company waits on larger corporate events. The thread went through the H1 OKR doc one KR at a time, appended an H1 progress section to it, and drafted a new H2 OKR doc. The H2 objectives were later realigned to Taylor's three PSE priorities.

Note: the individual KR status grades and Karl's self-assessment of his own performance are left out of this note under Green Dot policy: [redacted – employee performance/comp data]. Only program-level objectives, KRs and initiatives are included here.

## Artifacts
- `Karl 2026 OKRs.docx`: the original H1 doc with 3 objectives and 12 KRs. An H1 progress summary was appended as pages 4–6. Local upload; it was not kept in the session.
- A new H2 OKR doc ("H2" in the title, same format as the original). It has 10 KRs, and each one names an artifact. It was rebuilt after the objectives were realigned and the Obj 3 title was updated.
- These files live only in Karl's local Cowork outputs. Nothing was published to Confluence.

## Key findings (program-level initiatives)
- **Solution Guides:** GDN (which covers Cash Loads and Bill Pay) and Arc templates are live at the alignment gate. EWA was dropped as a category.
- **Scope control is moving to the SOW.** Karl helped Tony and Taylor on the CheckFreePay SOW, which the partner accepted without revisions. He is also working with Paul Cathcart and Nicol P on a tighter appendix of SOW requirements for BaaS deals.
  - Scope-change case studies: Perqs (white-label/hosted changed to GD-branded like Amscot, plus a custom "teller incentives" feature that wasn't in the original scope) and Bakkt (requirements keep changing).
  - There is no formal tracker yet.
  - "Post-LOI" is a poor signal because GD doesn't use LOIs consistently. The SOW is effectively the point where scope is locked.
- **Developer experience:** Karl and Nicholas are overhauling the Disbursements developer guides, with API recipes up next.
- **AI workflows:**
  - A Claude–Confluence agent creates Product Discovery templates and keeps its own knowledge base updated. It cut template time from about 1 hour to about 15 minutes.
  - Claude handles research and RFPs.
  - Claude Code is used to research code paths, which replaced the Copilot KR.
  - The gap: none of this is written down. The know-how sits with Karl and Taylor.
- **Must-win deals supported:** TikTok, 7-Eleven, Meijer, Toast, JPMC.
- **Product proposals that came from deals:**
  - PayPal for disbursements: in development, driven by TikTok.
  - Network private label cards for closed-loop wallets: proposal pending (Toast, 7-Eleven, Meijer).
  - Componentized partner widgets in the GD app, such as rewards balances or EBT balances via Forage (Meijer, 7-Eleven).

## Decisions
- **Final H2 objectives:**
  1. Be an indispensable partner to Business Development in achieving their bookings and launch targets.
  2. Shape Green Dot's product future by converting market signal into platform capability.
  3. Drive partner success by being the easiest partner to choose, build and stay with. Taylor wanted a partner-centric framing; Karl reworded it.
- **H2 KRs:**
  - Obj 1: PSE leads solution definition on 100% of strategic opportunities (reworded from "Karl leads"). Support 100% of must-win deals. Hold at least 3 deal-financials learning sessions with BD/Finance experts and turn them into a deal-assessment guide. Explore and recommend an AI-assisted demo capability.
  - Obj 2: Lead product *discovery* (not "development") for the closed-loop wallet / retailer value chain, ending in a capability and market brief for leadership. Take the Disbursements docs live on the public developer site and publish API recipes.
  - Obj 3: Disbursements and Closed Loop Wallet Solution Guides. Use the BaaS SOW appendix in at least 2 deals and write a Perqs/Bakkt lessons brief. Publish an AI workflow playbook. Add at least 1 new AI workflow.
- **Visibility comes from artifacts.** There is no separate "be visible" KR; each KR produces a shareable artifact instead.

## Open questions
- Whether the "net-new AI workflow" KR is realistic given bandwidth.
- Whether the closed-loop wallet KR should aim for a formal roadmap proposal or for "define and socialize."
- The DX benchmark versus fintech peers from the H1 KR5 wasn't carried forward explicitly.

## Next steps
- Get Taylor's sign-off on the final H2 doc.
- Write the AI workflow playbook in Confluence.
- Finish the Disbursements docs and publish them on the public developer site.
- Schedule the deal-financials sessions with BD/Finance.
- Begin the closed-loop wallet capability brief (see [[Retail Embedded Finance Offsite Takeaways]]).

## Key sources
- Internal only: `Karl 2026 OKRs.docx` and the H2 OKR doc.

## Resume prompt
> I'm continuing work on my 2026 PSE OKRs (Director, Product Sales Engineering, Green Dot). The H2 doc has three objectives aligned to Taylor's PSE priorities:
> (1) Be an indispensable partner to BD in achieving bookings and launch targets.
> (2) Shape GD's product future by converting market signal into platform capability.
> (3) Drive partner success by being the easiest partner to choose, build and stay with.
> It has 10 KRs, each tied to an artifact. Key ones: closed-loop wallet product discovery brief, Disbursements docs live plus API recipes, Disbursements and Closed Loop Wallet Solution Guides, the BaaS SOW appendix (with Paul Cathcart and Nicol P) used in at least 2 deals plus a Perqs/Bakkt lessons brief, an AI workflow playbook, an AI demo recommendation, and at least 3 deal-financials sessions with BD/Finance. Keep individual performance ratings and comp out of the chat. I'll upload the H2 doc. Please help me with: [next task].
