**Good morning, Karl — Monday, September 28, 2026**

**📅 Today's Calendar** (all times EDT)
- All day — **Julien OOO** (FYI)
- All day (Mon–Tue) — **Lisa @ ACI Workshop** (FYI; Lisa's traveling to ACI on the processor migration)
- 11:30–12:00 PM — **Discuss REAL SLX limit increase request** — Ray Taddeo, Paul Cathcart, S. Burns, T. Lamb, E. Westphal
- 12:00–12:45 PM — **Amscot F&F Testing Checkpoint** (tentative) — J. Golden + roughly half the company
- 2:00–2:30 PM — **Bill payment – UI discussion** (Alacriti, tentative) — Tony Phillips, Stuart Bain & Jonathan Berger (Alacriti), T. Driggs, T. Weible
- 2:30–3:30 PM — **PERQS – Cross Functional Team Status** (tentative) — J. Golden, cast of ~120

**📬 Emails Worth Attention**
A quiet weekend. Nearly everything is newsletters, which is one kind of win.
- **Lisa Roberts — "New Time Proposed: Karl - Lisa"**: She's at ACI Mon–Tue and wants to move your 1:1 to Thursday. It needs an accept or decline.
- **MCO — OPSCOM-1365109 Cardholder Service Disruption (INITIAL/RESOLVED)**: Intermittent processing issue on Saturday, already resolved. Worth a skim in case Amscot/Perqs testers bring it up at noon.
- **Checkpoint — Quarantine notice**: 2 emails were quarantined. It's probably spam, but check that nothing from a partner got caught.
- Everything else is PYMNTS and Datadog digests. Nubank bidding $13B for Monzo is your trivia for the day.

**📓 Notes from Yesterday (Fri 9/25 + recently touched notes)**
- **Taylor 1:1 (9/25):** Set up time with Nikhil on the ACI integration. It's our own cloud instance, but we don't fully control it. Taylor's real question is less "can we do it" and more "what market does it open up." The MBR deck is also on the list.
- **Alacriti (9/23):** Payments that would need a refund have to be rejected at authorization, since there are no refunds post-commit. Proceeding on the GD Hosted UI.
- **Toast (9/23):** Fergal's main concern is all-in pricing. Shannon was presenting the packaged pricing on 9/24. Toast has a small, known list of MIDs.
- **Remitly (9/21):** Remitly is on Lead Bank's waitlist and has relationships with Lead and Coastal. Funds flow for Frank is still owed.
- **Q2:** "Create Solution Guide" is floating at the top of the note. The sample Auth payload promise (from 9/1) is still open.
- **PSE Opportunity Manager:** Dashboard is done. Full workflow and the SOW skill are next.
- Bakkt, Meijer and REAL notes were touched Friday but had no new dated entries.

**🔗 Relevant Notes for Today's Agenda**
- **REAL SLX (11:30):** From 9/2: redlines are active, Visa agreement is done, and REAL wants to sign with GD at the same time, targeting September. BD Review (9/14) said "very close, end-of-month close." Jonathan flagged non-standard reporting and net-float pricing customization. A limit-increase ask two days before month-end is either a closing signal or a new redline.
- **Amscot F&F (12:00):** As of 9/22, testing was only ~50% through test cases. There are lots of defects, overdraft testing needs help, and Jeff is working on a funding request for your test account. Plan: [Amscot F&F Master Test Plan](https://greendot.atlassian.net/wiki/spaces/PROD/pages/2146664451/Amscot+F+F+Master+Test+Plan)
- **Alacriti Bill Pay UI (2:00):** GD Hosted UI is the path. Tony has called that UX "old and archaic," and Alacriti is "OK with it (maybe)." Reject-at-auth is the key design rule. Legal previously raised MTL concerns. Volume is 1.8MM payments/month across 908 billers.
- **PERQS (2:30):** Nov 2 F&F, Dec 1 launch. It's GD-branded and cloned from the Amscot product in ACI/GBOS. Whatever breaks at noon in Amscot is a preview of Perqs.

**☑️ Open Items (TODO)**
Sync: nothing to close, nothing new to add (0 closed, 0 added, 0 notes touched). Your checkboxes are either all handled or all still open.
- [ ] I will share a sample Payload call for an Auth request — Q2 — 9/25/2026
- [ ] set up time with Nikhil to understand the ACI integration — Taylor — 9/25/2026
- [ ] put together to-do list for documentation needs — Taylor — 9/25/2026
- [ ] run through Taylor feedback on Retailer cheat sheet doc — Taylor — 9/25/2026
- [ ] what's the desired end state — Taylor — 9/25/2026
- [ ] create collateral for this offering - use Disbursements sell sheet as a model — Taylor — 9/25/2026
- [ ] incorporate full workflow — PSE Opportunity Manager — 9/25/2026
- [ ] SOW skill — PSE Opportunity Manager — 9/25/2026
- [ ] Create Solution Guide for Q2 — Q2 — 9/25/2026
- [x] Create Funds Flow and share with Frank — Remitly — 9/25/2026

**🤝 PSE Pipeline** ([Dashboard](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2884534408/Solution+Opportunities+Dashboard))
Active (excl. Delivery): **18**. Discovery 8 · Design 2 · Alignment 6 · Contracting 2
- **Contracting:** Real (ARC, Consumer DDA, Ray) · Alacriti (GDN, Cash Bill Pay, Tony)
- **Alignment:** Toast (ARC, Prepaid/Closed Loop, Shannon) · TikTok ×2 (ARC, Wallet DDA + Disbursements, Willis) · Jackson Hewitt (ARC, DDA, Ray) · T-Mobile & Metro (GDN, Cash Loads Bill Pay, Frank) · JP Morgan (GDN, Concourse Cash Bill Pay, Ray)
- **Notes flagged:** Toast (9/24 DRC OK'd proceeding at $500k–$750k DSC; next step is the DSC business case; Durbin still open) · Alacriti (reject-at-auth, GD Hosted UI, docs linked) · Q2 (Solution Guide in progress) · Remitly (funds flow in progress) · Dollar General ("heating up soon") · Fetch Rewards (new; Ray scheduling intro)

**📝 Tracker Updates to Consider**
- **Real:** The SLX limit-increase meeting is today. The card has no notes and was last updated 9/18, even though "end-of-month close" is Wednesday. Add a note after 11:30.
- **TikTok (both cards):** BD Review said TikTok set a *September* decision deadline. It's 9/28, and both cards are blank and haven't been updated since 9/18. Either something happened or someone should ask Willis.
- **Alacriti:** The card says the refund/UI call was "9/24," but your note is dated 9/23. Fix one of them, and add today's UI discussion outcome.
- **Amscot / Perqs (Delivery):** Consider adding the ~50% test completion and the Perqs Nov 2 F&F / Dec 1 dates to the notes.

**✅ On Your Radar**
1. Before 11:30, get up to speed on REAL SLX: open redlines, what "limit increase" means (load/spend/balance), and whether it moves the signing date.
2. Reply to Lisa's reschedule. While ACI is top of mind, knock out "set up time with Nikhil re: ACI."
3. Alacriti UI call at 2:00: bring the reject-at-auth rule and a view on Hosted UI tradeoffs, so "old and archaic" doesn't turn into a scope change.
4. Q2 has owed a sample Auth payload since 9/1 and needs its Solution Guide. Four weeks is long enough that it's now a character trait.
5. Remitly funds flow for Frank: it's been open a week, and it's the only Discovery item with a named deliverable.
