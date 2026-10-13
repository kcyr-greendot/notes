---
type: claude-summary
session_id: local_6bb34f39-5d0f-43b1-b1a4-5792844684a8
session_title: SOW roles and responsibilities review
last_synced: 2026-10-12
status: active
tags: [claude-summary, sow-review, money-movement, baas-partners]
---
# SOW Appendix B R&R Review

## Context
Karl reviewed the latest draft of "SOW Appendix B – GD vs Partner R&R (API Partner)," a matrix of Green Dot vs. partner roles and responsibilities. He asked Claude for opinions on specific line items. He also plans to produce a 1–3 slide summary and deeper topic explainers (e.g., ACH Pull).

## Artifacts
- Uploaded PDF: "SOW Appendix B - GD vs Partner R&R (API Partner).pdf" (session upload; not saved to notes).
- No simplified PPT version was found. Claude offered to search SharePoint/Teams, but no search was run.

## Key findings
- **ACH Pull, "NACHA-compliant authorization" (p.6):**
  - For WEB/PPD debits, the Originator must get and keep the consumer's authorization and produce Proof of Authorization (POA) if disputed.
  - Green Dot, as ODFI, is liable if the partner fails to do this.
  - Possible clearer wording: "Obtains and retains written consumer authorization (per applicable NACHA SEC code requirements) before initiating ACH debits against an external account."
  - The Partner cell bundles authorization, aggregator account validation, retention and return-rate management.
- **Debit pull / Instant Transfer In, "submits risk model to GD quarterly":** This is too onerous for fintechs relying on Green Dot's expertise. Suggested wording: "Maintains and can evidence fraud controls for external debit card funding (e.g., velocity limits, device fingerprinting, 3DS), and provides documentation to GD upon request or as part of the annual program review." Annual review with a right to request more often.
- **Debit push / OCT, "GD performs OFAC screening":** This likely overclaims. Green Dot screens its own sending customer at enrollment, and the receiving bank screens the recipient. There is nuance if the partner collects the recipient's name. Suggested wording: "Performs OFAC screening on the sending customer. Receiving bank is responsible for OFAC screening of the recipient." Confirm with Compliance, since examiners may test any control the document claims.
- **Idempotency (p.4):** This is an API implementation detail, not an R&R item. Move it to API or developer docs.

## Decisions
- Keep "NACHA-compliant authorization" as is in the SOW; build the detail in separate explainer content.
- Remove the idempotency line.
- Soften the debit pull risk-model requirement (Karl agreed it's onerous; final wording pending).
- Correct the OFAC wording for debit push (pending Compliance confirmation).

## Open questions
- Who wrote the quarterly risk-model requirement (Compliance/Risk or a prior deal)? This affects how much it can be softened.
- What OFAC screening does Green Dot actually perform in the OCT flow? Route to Compliance.
- Does a simplified PPT version of the R&R matrix already exist?

## Next steps
- Send the redline comments (risk model, OFAC, idempotency) to the SOW owner.
- Search SharePoint/Teams for an existing R&R summary deck. If none exists, build a 1–3 slide summary.
- Draft an ACH Pull explainer covering NACHA authorization, POA and how to validate it.

## Key sources
- None external.

## Resume prompt
> I'm Karl (Director of PSE, Green Dot Bank), reviewing "SOW Appendix B – GD vs Partner R&R (API Partner)." Decided so far: keep "NACHA-compliant authorization" on ACH Pull (detail goes in a separate explainer); remove the idempotency line (API detail); soften the debit pull "quarterly risk model" requirement to "maintain and evidence fraud controls, documentation on request or at annual review"; change the debit push OFAC wording to cover the sending customer only, with the receiving bank screening the recipient (confirm with Compliance). Open: whether a simplified PPT of this matrix already exists. Please help me with: searching SharePoint/Teams for an existing R&R summary deck, or drafting a 1–3 slide summary of the appendix.
