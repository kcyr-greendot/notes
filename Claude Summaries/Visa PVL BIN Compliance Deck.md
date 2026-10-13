---
type: claude-summary
session_id: local_d1c3e3a6-b425-4b2d-942c-8738bad6ea0f
session_title: Visa PVL BIN compliance deck
last_synced: 2026-10-12
status: active
tags: [claude-summary, toast-cash, kyc-exemption, private-label-bin]
---
# Visa PVL BIN Compliance Deck

## Context
Built a deck for Green Dot Compliance explaining exactly what changes if the Toast Cash closed-loop program moves to a Visa private label (PVL) BIN. Goal: get a definitive decision on whether changing only the payment credential affects the program's compliance stance; Karl's premise is that it does not. Builds on the earlier "Toast Cash gift card aggregation code" thread.

## Artifacts
- 17-slide GD-branded .pptx (generated via python-pptx after pptxgenjs failed; skill gd-greendot-pptx-template), presented in session outputs
- Source: existing KYC Exemption Analysis memo and Karl's memory file

## Key findings
- Existing memo referenced a Mastercard private label BIN (MDES tokenization); Karl chose Visa PVL as working example, with an assumption slide stating network choice doesn't alter the analysis.
- Deck structure: program today (Toast Cash, two-factor KYC exemption, five guardrails); proposed change (what the PVL BIN does and doesn't do); side-by-side comparison with only three form-factor/credential items changing; statutory analysis; Reg E risk flag and rebuttal; Visa vs. Mastercard assumption; recommended decision (four action items: Decision Gate / Pre-Launch / Separate Track); dark summary slide.
- Core argument: 31 CFR 1010.100(kkk) and 1010.100(ff)(4)(iii)(A) turn on where funds can be spent (Toast-only) and maximum value (up to $2,000); both are silent on network and credential type. Gate item: Compliance must confirm BIN configuration doesn't break the merchant-restriction test under Reg E.
- Key refinement: reloadability is not a disqualifier in the statutory text. Gift card purchase/aggregation exists to avoid a transfer from an external account (AFT/ACH push), not to avoid reloads. Purchase of stored value is a commercial sale; AFT signals a prepaid deposit / money transmission product with different Reg E, FinCEN, and state licensing implications.

## Decisions
- Use Visa PVL as the example network; note network-agnostic assumption explicitly.
- Reframe constraint as "can accumulate value repeatedly; cannot accept bank-to-card transfers," replacing "no reloads" language.

## Open questions
- Compliance sign-off on whether PVL BIN configuration affects merchant restriction under Reg E (routed to Green Dot Compliance)
- Final network choice (Visa vs. Mastercard)

## Next steps
- Revise deck and memo funding-model language to replace "no reloads" with the purchase-vs-transfer distinction
- Present deck to Compliance and obtain decision

## Key sources
- 31 CFR 1010.100(kkk) and 1010.100(ff)(4)(iii)(A) (FinCEN prepaid access / closed-loop definitions)

## Resume prompt
> I'm Karl (PSE, Green Dot). I built a 17-slide GD-branded deck for Compliance arguing that moving Toast Cash (closed-loop, Toast-only, up to $2,000, KYC-exempt under 31 CFR 1010.100(kkk) and (ff)(4)(iii)(A)) to a Visa private label BIN changes only the credential, not the compliance stance. Gate item: Compliance must confirm the BIN doesn't break merchant restriction under Reg E. We clarified that the gift card purchase/aggregation model exists to avoid AFT/bank-to-card transfers, not reloads; reloading via purchases is fine. Deck still needs language updated from "no reloads" to the purchase-vs-transfer framing. Please help me with: [next task].
