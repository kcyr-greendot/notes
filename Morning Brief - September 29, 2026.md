**Good morning, Karl — Tuesday, September 29, 2026**

**📅 Today's Calendar** (ET)
- *All day* — Lisa @ ACI Workshop (Lisa Roberts; final day)
- 12:00–12:30 — 7-11 & GD Direct Connect // Weekly Project Status (Veronica; 7-Eleven team: Jithesh, Veena, Chad, Willie) — *tentative*
- 12:00–1:00 — Working Group: Payment Systems Risk (T. Watkins; ~130 attendees, so nobody will miss you) — *tentative, conflicts with 7-11*
- 1:00–1:25 — M2020 planning (L. Gonzalez; Willis, Tony, Taylor, Shannon)
- 1:30–2:00 — Regular 1:1 synch up (Taylor Driggs)
- 3:30–4:00 — Amscot F&F Testing Checkpoint (J. Golden) — *tentative*
- 4:05–5:00 — PayPal Disbursements_Alignment — draft PRD review (Mano; Taylor, Irena, Erik) — *tentative*
- 5:00–5:25 — Karl / Lisa

**📬 Emails Worth Attention**
- **Willis Beal → Snap Finance** (cc you) — *Snap Finance <> Green Dot | Introductory meeting.* Next steps from the 9/14 call: Snap to name focus areas, GD to map synergies/gaps and propose solutioning sessions, dev portal shared, mobile-wallet provisioning flow attached, prelim pricing offered. Translation: the gap map probably lands on your desk.
- **Stuart Bain (Alacriti)** — *Re: Bill payment – UI discussion.* Sent the functional design doc (OBP EBPP Cash Payments Retail Functional, .docx) referenced on yesterday's call. Required reading before anyone commits to a UI direction.
- **Shannon Yonai → Visa** (cc you) — *RE: Private Label Discussion.* Still chasing whether Visa Token Service fees hit issuer or merchant acquirer, plus an all-in issuer cost per txn to close the financial model. Third-plus nudge; Visa is apparently in no hurry.
- **Danny Fong** — *Danny PTO.* FYI only.

**📓 Notes from Yesterday (9/28)**
- **Alacriti** (Tony, Tim, Taylor / Stuart): Tony pushed for Alacriti to build its own UI. Stuart balked — it competes with a 2027 UI initiative and "isn't a big part of what we do." Their counter: cap the max payment-method amount at the bill amount (sidesteps the refund problem).
- **REAL** (Ray, Paul, Emily Westphal, Taylor Lamb): Emily and Taylor sitting in for Sarah. That's the whole note — riveting stuff.

**🔗 Relevant Notes for Today's Agenda**
- **7-Eleven:** Standing asks are test data and a stable version to test against; void + timeout-reversal support across all products is a hard requirement; site-to-site connectivity concern vs. internet-facing APIM gateway.
- **PayPal Disbursements:** Fee at $0.25/txn — Crystal wants fee-free, which held up the PRD in August. PayPal won't support W2 payroll payouts (contractor/commission OK); Rapid! positioning ("already-earned wages") was pending PayPal compliance. PayPal set up as a vendor in LogicGate, not a partner.
- **Amscot:** As of 9/22, ~50% through test cases with lots of defects; overdraft testing needs help. [Master Test Plan](https://greendot.atlassian.net/wiki/spaces/PROD/pages/2146664451/Amscot+F+F+Master+Test+Plan).
- **Taylor 1:1 / ACI:** Taylor's 9/25 take — the question isn't *can* we do ACI, it's what market opportunity it opens. GD has its own cloud ACI instance without full control. MBR deck was on the list. Five open items from Taylor's note are below — good 1:1 fodder.

**☑️ Open Items (TODO)**
Sync: closed 1 (Remitly funds flow), added 0 from 0 notes.
- [ ] I will share a sample Payload call for an Auth request — Q2 — 9/25/2026
- [ ] set up time with Nikhil to understand the ACI integration — Taylor — 9/25/2026
- [ ] put together to-do list for documentation needs — Taylor — 9/25/2026
- [ ] run through Taylor feedback on Retailer cheat sheet doc — Taylor — 9/25/2026
- [ ] what's the desired end state — Taylor — 9/25/2026
- [ ] create collateral for this offering - use Disbursements sell sheet as a model — Taylor — 9/25/2026
- [ ] incorporate full workflow — PSE Opportunity Manager — 9/25/2026
- [ ] SOW skill — PSE Opportunity Manager — 9/25/2026
- [ ] Create Solution Guide for Q2 — Q2 — 9/25/2026

**🤝 PSE Pipeline** ([Dashboard](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2884534408/Solution+Opportunities+Dashboard))
Active (ex-Delivery), ARC + GDN: **Discovery 8 · Design 2 · Alignment 6 · Contracting 3** = 19

Hot deals:
- *Alignment:* Toast (ARC, Shannon) — DSC business case next, Durbin routing open · TikTok Wallet + TikTok Disbursements (ARC, Willis) · Jackson Hewitt (ARC, Ray) · T-Mobile & Metro (GDN, Frank) · JP Morgan Concourse (GDN, Ray)
- *Contracting:* Real (ARC, Ray) — program limit increase approvals outstanding · Alacriti (GDN, Tony) — "proceeding on GD Hosted UI" · Avant (GDN, Tony)

Other notes: Remitly (both) — 1% remittance excise tax unavoidable · Fetch — new, intro call set · Dollar General — "heating up soon" (per Adam, since 9/22) · Q2 — Solution Guide in progress.

**📝 Tracker Updates to Consider**
- **Alacriti** — Card says "Proceeding on GD Hosted UI," but yesterday Tony pushed Alacriti to build its own UI and Stuart floated capping payment amount to the bill. Plus a new functional design doc. That note is now fiction — update it.
- **Snap Finance** — Willis' follow-up sets concrete next steps (gap map, solutioning sessions, prelim pricing). Card last touched 9/18 with no note.
- **Toast** (probably — Shannon's Visa private label thread) — Visa Token Service fee allocation is still an open item worth noting next to Durbin routing. Confirm it's Toast before logging.
- **PayPal Disbursements** — Alignment meeting today, but no card on the dashboard. Add it, or accept that it lives off-book.
- **Q2** — Solution Guide still open in TODO; link it to the card once it exists.

**✅ On Your Radar**
1. Pick one for noon: 7-11 status or the 130-person risk working group. (Hint: only one has your name in the notes.)
2. Skim Alacriti's functional design doc before the UI debate goes another round, then fix the card.
3. Bring the Taylor-note open items (ACI/Nikhil, documentation to-do list, collateral, cheat-sheet feedback) to the 1:30 1:1.
4. Prep for the PayPal PRD review at 4:05: fee-free vs. $0.25 and the W2 payout question are the likely hot spots.
5. Get with Willis on who owns the Snap synergies/gaps map.
