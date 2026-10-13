---
type: claude-summary
session_id: local_eb45f2d3-4c8d-43f3-82ae-4f8a96036cef
session_title: Qualia RFI competitive assessment
last_synced: 2026-10-12
status: active
tags: [claude-summary, rfi, escrow-accounts, baas]
---
# Qualia RFI competitive assessment

## Context
Karl uploaded Qualia's confidential RFI, "Specialty Accounts for Title & Escrow" (Aug 2026), and asked for a requirements summary plus an opinion on whether Green Dot is competitive. The response deadline was August 26, 2026.

## Artifacts
- Uploaded: [Confidential] Qualia RFI_ Specialty Accounts for Title & Escrow - Aug 2026.pdf

## Key findings
- Qualia, a real estate closing platform, wants an API-first bank partner for embedded escrow/title specialty accounts. Secondary ask (Section F): possibly take over its existing FBO payments program. Qualia would act as program manager.
- Account structures: on-core DDAs in each title company's name/TIN, or FBO-per-customer with virtual subledgers.
- Requirements: API account opening (KYC to account number in under 24 hours); rails for ACH, same-day ACH, domestic and international/FX wires, RTP/FedNow, check print-and-mail, Check21, RDC, Zelle, stablecoins, and book transfers; per-file virtual account numbers; real-time and intraday sub-ledger reporting; ISO 20022 end-to-end IDs; IOLTA-approved institution by state with interest remittance to bar foundations; setoff waivers; overdraft rejection; IntraFi reciprocal deposits; dormancy/escheatment; sweeps; FBI Financial Fraud Kill Chain and FinCEN Rapid Response participation.
- Scale: $750M deposits in Year 1, rising to $2.5B by Year 3. RDC is about 295K+ transactions per year in Year 1.
- Assessment: partial fit. Strengths are API-first BaaS, FBO/virtual subledgers, ACH, domestic wires, webhooks, KYC delegation, and Section F.
- Significant gaps: IOLTA approval (charter/regulatory status, potential blocker), international/FX wires, Zelle (GD not a participant), RDC, and IntraFi.
- To verify: extended wire hours, check print-and-mail at scale, ISO 20022 IDs, API-based check positive pay, sweeps.

## Decisions
- Recommendation: respond only if GD can be transparent about current state vs roadmap and its IOLTA position is defensible. Otherwise deprioritize.

## Open questions
- GD's IOLTA approval status by state (route to Legal/Compliance; Section D review recommended immediately).
- Capability confirmation for the "verify" items (route to product/payments teams).
- Whether a response was submitted by Aug 26.

## Next steps
- Confirm go/no-go and the outcome of the submission.
- If pursuing, build a gap and roadmap matrix by RFI section.

## Key sources
- Qualia RFI PDF (confidential, uploaded)

## Resume prompt
> I'm Karl (PSE, Green Dot). I assessed Qualia's RFI for embedded title/escrow specialty accounts (due Aug 26, 2026; $750M deposits Y1 to $2.5B Y3; DDA or FBO+virtual subledger; Qualia as program manager; option to take over its FBO payments program). Assessment: partial fit. Strong on API BaaS/FBO/ACH/domestic wires. Gaps: IOLTA approval, intl/FX wires, Zelle, RDC (~295K/yr), IntraFi. To verify: wire hours, check print/mail, ISO 20022, positive pay, sweeps. Legal/Compliance review of Section D was recommended. Please help me with: [next task].
