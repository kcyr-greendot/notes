---
type: claude-summary
session_id: local_6cd63989-059c-4d9f-b8c6-1297ad4b21ea
session_title: Amscot test plan assessment
last_synced: 2026-10-12
status: active
tags: [claude-summary, amscot, uat-testing, fsc]
---
# Amscot F&F Test Plan Assessment
## Context
Karl asked for a status breakdown of the Amscot Friends & Family (F&F) Master Test Plan ahead of the 10/1 Go/No-Go. He also wanted the unexecuted test cases clustered by functionality and narrowed down to what UAT testers like himself can actually run. The Confluence page was too large to fetch directly, so Karl exported it to markdown. Row colors were lost in the export, so status was inferred from the result text.

## Artifacts
- [Amscot F&F Master Test Plan (Confluence)](https://greendot.atlassian.net/wiki/spaces/PROD/pages/2146664451/Amscot+F+F+Master+Test+Plan)
- Uploaded markdown export: "Amscot- F&F Master Test Plan.md"
- [Amscot Product Setup page](https://greendot.atlassian.net/wiki/spaces/PROD/pages/1397784641)

## Key findings
- **195 total test cases:**
  - 91 Pass (47%)
  - 68 Not executed (35%)
  - 7 Fail
  - 5 In Progress
  - 13 Blocked on Amscot (inferred)
  - 11 N/A
- **The 7 failures:**
  - CNP online purchase
  - Retail Locator API
  - ACH Pull (app)
  - Swipe Reload at FSC
  - Transaction History on web (ACH/Bill Pay)
  - MMF Tier 1 FirstUse waiver (online)
  - ODP opt-in (web)
- **Blocked on Amscot:** mostly in-store flows (activation, registration/IDV, cash/check initial load, reload/unload).
- **Owned by other teams, not UAT** (removed from the UAT backlog):
  - Ops: Accounting & Reporting (9), Fraud Ops (7), CES/contact center (7)
  - CRM: closure flows (5)
  - Settlement: placeholder rows (3)
  - Backend: IDV (2), OFAC (1), Store ID (1)
  - Needs physical Amscot POS: in-store acquisition (2), Swipe Reload (1)
- **True UAT backlog is 30, about 24 executable:**
  - ODP scenarios (6): need checking at $0 by moving funds into the Savings vault, multi-day sequences, and 24-hour grace periods. Row 29 ($250 tier assignment) is a quick win.
  - MMF fee scenarios (6): all gated by the billing cycle. The $3.95 Tier 1 fee test needs no purchases during the cycle. Negative-balance tests need ODP active or a backend adjustment. Confirm the 9/14 fix for the failed FirstUse waiver before running row 4.
  - IVR (5): Chrissie Hunter can run rows 3, 4, 7 and 8 in one or two call sessions. Row 6 is blocked because Amscot hasn't provided its partner phone number.
  - Lost/stolen (3): Jeff is covering these.
  - Self-service closure (2) and disputes (2)
- **Deferred/untestable in the F&F window:**
  - Savings interest posting, 1099-INT and 1042-S: interest moved to annual posting on 9/3, and owner Yamini has an open comment thread on it.
  - Expired card reissuance: needs backend intervention.
  - Two blank placeholder rows (Section 4, rows 19 and 36).

## Decisions
- Karl's role is mainly coordination and visibility rather than executing many tests.
- Recommend formally marking Savings tax/interest and expired card reissuance as deferred.

## Open questions
- The pre-prod Green Dot Bank web URL used for Amscot testing was not found. Check the Go-Live Readiness deck (SharePoint), the Product Setup page or the PRD, or ask Harmandeep Kaur or Megan Ackling.
- Amscot partner phone number (IVR row 6), plus Store ID and employee details for in-store tests.

## Next steps
- Possibly pick up: self-service closure, dispute intake via CRM, ODP row 29.
- Escalate the Amscot dependencies (phone number, store access).
- Clean up the placeholder rows and mark deferred tests in the tracker.

## Key sources
- [Amscot F&F Master Test Plan](https://greendot.atlassian.net/wiki/spaces/PROD/pages/2146664451/Amscot+F+F+Master+Test+Plan)
- [Amscot Product Setup](https://greendot.atlassian.net/wiki/spaces/PROD/pages/1397784641)

## Resume prompt
> I'm tracking Amscot F&F UAT ahead of the Go/No-Go (originally 10/1). Of 195 test cases: 91 pass, 68 not executed, 7 fail, 13 blocked on Amscot. After removing ops, backend and Amscot-POS work, the real UAT backlog is about 24 executable cases:
> - ODP scenarios (6)
> - MMF billing-cycle tests (6)
> - IVR (Chrissie; row 6 blocked on Amscot's phone number)
> - Lost/stolen (Jeff)
> - Closure and disputes
>
> Savings interest/tax and expired card should be deferred. I still need the pre-prod web URL for testing. Please help me with: [next task].
