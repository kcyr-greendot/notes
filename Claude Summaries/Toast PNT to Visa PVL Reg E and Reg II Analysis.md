---
type: claude-summary
session_id: local_26be0cfd-b52c-46b9-aac7-9e4b2a109923
session_title: Reg E applicability payment instrument change
last_synced: 2026-10-12
status: active
tags: [claude-summary, reg-e, durbin-reg-ii, toast]
---
# Toast PNT to Visa PVL: Reg E and Reg II Analysis

## Context
Karl tested whether changing the Toast program's payment instrument from Green Dot PNT to a Visa private-label (PVL) credential with Apple Pay changes Reg E or Durbin/Reg II applicability. The program is an aggregated gift card product and is currently treated as Reg E exempt. The goal was to set out a firm position with clear criteria that Green Dot Compliance can respond to.

## Artifacts
None

## Key findings
- Program facts (Karl's position): the account is not reloadable. It is funded by buying individual, non-reloadable gift cards, which are digitally aggregated into one balance. Spend is accepted only at Toast-affiliated merchants (closed loop). Only the payment instrument changes.
- The PVL is private label running on Visa rails, not Visa-branded or open loop. Visa-side and Green Dot-side rules enforce closed loop. Apple Pay inherits the card's acceptance limits.
- Reg E: the gift card exclusion (12 CFR 1005.2(b)(3)) depends on program characteristics, not instrument type. Claude conceded that its earlier "aggregation breaks the merchant nexus" risk was speculation. The remaining exam risk is whether the aggregated balance could be read as "reloadable." The defense: each purchase is a discrete, non-reloadable card, and aggregation is a UX feature, not a reload mechanism.
- Logic equivalency, judged True: KYC and Reg E exemptions both come from the same "prepaid account" classification. So if Compliance finds no KYC for the new model, Reg E should also not apply. This holds only if the no-KYC basis is the gift card / non-prepaid classification and not some other carve-out.
- Durbin: Green Dot is under $10B in assets, so the small issuer exemption removes the interchange cap. The §235.7 network exclusivity and routing rules apply to all issuers regardless of size.
- Reg II "debit card" (§235.2) is defined broadly and includes prepaid. Unlike Reg E, it has no clean closed-loop gift card exclusion. A PVL on Visa rails likely meets "issued through a payment card network." The second network must be unaffiliated (Interlink does not count; STAR, NYCE or Pulse would). A second network also cannot route to closed-loop Toast merchants, so the requirement is operationally impractical. Even so, "functionally difficult" does not mean "legally exempt."
- Purpose argument: the dual-network rule exists to let merchants route to cheaper interchange. Toast is effectively on both sides (program sponsor and acquirer/merchant), so the transactions are likely on-us with nominal or zero interchange. That supports the view that Reg II was not meant to reach this structure.

## Decisions
- Route the question through Green Dot Compliance with a firmly stated position. Do not leave it open-ended.
- Treat Reg E as not affected by the instrument change. Treat Reg II §235.7 as the real open risk.

## Open questions
- Is Compliance's no-KYC basis the gift card / non-prepaid classification? (Compliance)
- How does Visa classify PVL transactions for Reg II, and does it treat sponsor-is-acquirer PVL as on-us / zero interchange? (Visa issuer relations or legal)
- Does the dual-network requirement attach to a closed-loop PVL? This needs a formal legal opinion, not just a compliance determination. (Green Dot Legal)

## Next steps
- Draft a compliance memo setting out the program-characteristics position, the aggregation-is-not-reload argument and the KYC/Reg E equivalency.
- Add the Reg II §235.7 analysis and the purpose argument, with a request for a legal opinion.
- Ask Visa for PVL classification and interchange treatment.

## Key sources
- 12 CFR Part 1005 (Reg E), §1005.2(b)(3) and Subpart E
- 12 CFR Part 235 (Reg II), §§235.2, 235.7

## Resume prompt
> I'm Karl (PSE, Green Dot). We're moving the Toast closed-loop aggregated gift card program from Green Dot PNT to a Visa private-label (PVL) credential with Apple Pay. The program is non-reloadable, funded by individual gift card purchases aggregated into one balance, and accepted only at Toast-affiliated merchants. My position: only the instrument changes, so the Reg E gift card exclusion still holds, and if Compliance confirms no KYC, Reg E also doesn't apply. Green Dot is under $10B, so the Durbin cap doesn't apply. The open risk is Reg II §235.7 dual unaffiliated network routing, since Reg II has no clean closed-loop exclusion. Counter-argument: Toast is both sponsor and acquirer (on-us, near-zero interchange), so the purpose of the rule doesn't apply. Pending: Compliance memo, Legal opinion on §235.7, Visa's PVL classification. Please help me with: [drafting the compliance/legal memo].
