---
type: claude-summary
session_id: local_ab4504c2-4fd1-432c-85f5-9fa59c9d0039
session_title: Customer spend data sharing considerations
last_synced: 2026-10-12
status: active
tags: [claude-summary, data-sharing, glba-privacy, partner-rewards]
---
# Customer Spend Data Sharing with Partners

## Context
Karl asked what to consider when sharing cardholder balance or spend data with a BaaS partner that wants to offer benefits based on balances or spending behavior. He then applied it to REAL: high-balance cardholders would get exclusive experience rewards, for example a Super Bowl party catered by Rao's for active customers holding at least $20,000. The goal is to scope the opportunity and build a discovery question list.

## Artifacts
- None.

## Key findings
- **The bank controls sharing.** In BaaS, the cardholder is Green Dot Bank's customer.
- **GLBA / Reg P basis for sharing NPI:**
  - §1016.14 (processing and administering the program) fits disclosed in-program benefits best.
  - §1016.13 (service provider or joint marketing) needs a contract and privacy-notice disclosure.
  - Use for the partner's own marketing likely needs opt-out; California (CalFIPA) and Vermont require opt-in.
  - §1016.11 limits reuse of shared data.
- **Balance-based benefits:**
  - May look like interest or a "bonus" under Reg DD (disclosures, advertising, possible 1099).
  - FDIC brokered deposit rules apply if the partner is paid on, or drives, balances; review the primary-purpose exception.
  - Check pass-through insurance and Reg E prepaid disclosures.
- **Spend-based benefits:** Visa/Mastercard rules on using transaction data; FCRA if the data drives eligibility decisions; fair lending/UDAAP if spending categories act as proxies for protected classes.
- **Best pattern: share the result, not the data.** The bank computes eligibility and returns yes/no. This reduces GLBA, network-rule and security exposure and keeps the partner out of PCI scope. If more is needed, use summaries rather than raw feeds.
- **TPRM:** use restrictions, retention/destruction, no onward sharing, SOC 2, breach SLAs, and audit rights (2023 Interagency TPRM Guidance).
- **Section 1033** open banking rule is under reconsideration; confirm its status with Legal.
- **REAL design:**
  - The customer starts the check in the REAL app ("Check eligibility") using the existing program token, not SSN or DOB.
  - Green Dot returns eligible: yes/no per offer, with no batch lists.
- **REAL-specific risks:**
  - A yes/no answer is still NPI.
  - REAL's other relationships with the customer are the main misuse risk; prohibit use outside the offer by contract.
  - "Not eligible" should be generic, with no reason codes, so it doesn't reveal holds or compliance flags.
  - Use average daily balance over 60–90 days plus a minimum account age, so customers can't load $20K for one day to qualify.
  - Reg DD bonus treatment and tax reporting.
  - Brokered deposits if REAL is compensated on balances.
  - Confirm program max balance and load limits support $20K+, and BSA risk review for a high-balance segment.
  - "Super Bowl" (NFL trademark) and Rao's branding need Legal and Marketing review.

## Decisions
- Recommended architecture: a customer-initiated, bank-computed yes/no eligibility check (Karl did not push back).

## Open questions
- For REAL: Is the program open to all or only existing REAL customers? How is the customer identified? Who funds the rewards, and is REAL compensated on balances? One-off offer or ongoing tiers? Is a tier needed, or only yes/no?
- Reg DD bonus, brokered deposit, and good-standing logic: route to Compliance and Legal (BSA/Compliance for eligibility logic; Tax for 1099).

## Next steps
- Send the REAL discovery questions.
- Brief Compliance, Legal and Privacy early on the brokered deposit and Reg DD questions, since they could change the product design.
- Confirm program balance limits support $20K+.

## Key sources
- None cited externally (general regulatory references: 12 CFR 1016 Reg P, Reg DD, 2023 Interagency TPRM Guidance).

## Resume prompt
> I'm Karl (Director of Product Sales Engineering, Green Dot Bank). REAL, a BaaS debit partner, wants to offer exclusive experience rewards (e.g., a Super Bowl party catered by Rao's) to cardholders holding at least $20K. The recommended design is a customer-initiated, Green Dot-computed yes/no eligibility check keyed on a program token. Key risks: a yes/no is still GLBA NPI; contract limits on REAL's use; a generic "not eligible" with no reason codes; average daily balance over 60–90 days to prevent gaming; Reg DD bonus and 1099; brokered deposits if REAL is paid on balances; $20K program limits; trademark review. Open: REAL's answers to the discovery questions, plus Compliance/Legal views. Please help me with: drafting the REAL discovery questions and a short brief for Compliance and Legal.
