---
type: claude-summary
session_id: local_e0a7777a-1e5c-4e6c-9f04-2aac8ebe4165
session_title: ACH and Direct Deposit in KYC-exempt prepaid
last_synced: 2026-10-12
status: active
tags: [claude-summary, prepaid-access-rule, kyc-cip, dayforce]
---
# ACH and Direct Deposit in KYC-Exempt Prepaid

## Context
Karl asked whether ACH pull or direct deposit can be offered on a KYC-exempt, closed-loop prepaid product. He then asked Claude to independently check Sarah C's claim that Dayforce is KYC-exempt and accepts ACH funding. The goal is accurate positioning for partner deals.

## Artifacts
- Confluence pages consulted (none created):
  - Dayforce – Green Dot Partnership Summary (BAASPO; labeled AI-generated, "not a source of truth")
  - Dayforce GPR Card for Foreign Nationals – Lite PRD (RISK)
  - Dayforce (Ceridian) Support (NOC)

## Key findings
- **FinCEN Prepaid Access Rule, 31 CFR 1010.100(ff)(4):**
  - A closed-loop card capped at $2,000 per device per day stays excluded from "prepaid program" status only if it does not allow international transfers, P2P transfers, or reloads from non-depository sources.
  - ACH pull from a consumer's bank and direct deposit from an employer's bank are depository sources, so on their own they don't break the exclusion.
  - Funds routed through non-bank intermediaries (another prepaid program, a wallet, a pooled-funds fintech) are murkier.
- **Risks that remain even if the exclusion holds:**
  - Bank CIP (31 CFR 1020.220) and the 2016 interagency prepaid CIP guidance, where reloadability is a main trigger.
  - Issuing routing and account numbers makes the product look more like a deposit account.
  - Wage deposits can make it a Reg E payroll card account. The wage exclusion in (ff)(4)(i)(D)(1) has the same three conditions and doesn't remove Reg E duties.
  - Nacha authorization rules, including WEB debit account validation.
  - ATO and money-mule risk, so expect velocity limits and monitoring.
- **Dayforce claim, only partly verified:**
  - The Dayforce Wallet Mastercard (issued by Green Dot Bank) is open-loop, not closed-loop.
  - It runs as two products on BaaS: a DDA for employees who pass KYC, and a "Limited"/light-CIP GPR card for employees who fail CIP, plus some instant-issue, minor and foreign-national cases.
  - The Limited GPR has no IDV/CIP because the employer is treated as the "customer of record." Name and OFAC screening still run. This is a different legal theory from the closed-loop exclusion.
  - The Lite PRD says: "Only payroll funds can be added to the account through Dayforce." So the reduced-KYC tier doesn't accept ACH.
  - ACH pull exists elsewhere in the program (NOC runbooks), likely on the KYC'd DDA. The full PRD limits table wouldn't load, so this is unconfirmed.

## Decisions
- Positioning: Dayforce shows a reduced-KYC payroll-only card is possible. It does not show that a no-KYC card can accept ACH pull. When comparing to Dayforce, the honest version is "payroll-only Limited GPR; KYC unlocks ACH."

## Open questions
- Which Dayforce tier has ACH pull enabled, and with what limits? Route to the BaaS Product owner for Dayforce.
- Final view on exemption status for any proposed structure: route to BSA/AML Compliance and Legal.

## Next steps
- Confirm the Limited GPR funding rules with the Dayforce BaaS Product owner and BSA/Compliance.
- Close the loop with Sarah C on the corrected framing.
- For any partner proposal, document load sources, daily and lifetime caps, reloadability, whether an account number is issued, and whether funds are wages. Then send it to Compliance.

## Key sources
- https://greendot.atlassian.net/wiki/spaces/BAASPO/pages/2503409709/Dayforce+-+Green+Dot+Partnership+Summary
- https://greendot.atlassian.net/wiki/spaces/RISK/pages/2108293197/Dayforce+GPR+Card+for+Foreign+Nationals+-+Lite+PRD
- https://greendot.atlassian.net/wiki/spaces/NOC/pages/77723393/Dayforce+Ceridian+Support
- https://s203.q4cdn.com/998886067/files/doc_news/2024/12/FINAL-Press-release-Wallet-5B-Milestone-and-Direct-to-Bank-Pay.pdf

## Resume prompt
> I'm Karl (Director of Product Sales Engineering, Green Dot Bank). We looked at whether ACH pull or direct deposit can go on a KYC-exempt closed-loop prepaid card. Under 31 CFR 1010.100(ff)(4), depository-source reloads don't break the $2,000/day closed-loop exclusion, but bank CIP, Reg E payroll, Nacha and fraud risks remain. Sarah C claimed Dayforce is KYC-exempt and accepts ACH. Internal Confluence shows Dayforce Wallet is open-loop: a DDA for KYC passes and a Limited GPR (employer as customer of record, OFAC/name screening only) that accepts payroll funds only. ACH pull likely sits on the DDA but is unconfirmed. Please help me with: drafting a note to the Dayforce BaaS Product owner and BSA/Compliance to confirm which tier supports ACH pull and the Limited GPR funding rules.
