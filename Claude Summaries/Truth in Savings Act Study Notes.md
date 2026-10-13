---
type: claude-summary
session_id: local_c3cf0f63-1ec1-47ea-8552-126f7f1f5dfa
session_title: Truth in Savings Act compliance
last_synced: 2026-10-12
status: active
tags: [claude-summary, reg-dd, compliance-training]
---
# Truth in Savings Act Study Notes

## Context
Karl shared screenshots from a mandatory compliance training module on the Truth in Savings Act (TISA/Reg DD). He asked for help understanding the material so it would stick and he could pass the quiz. Follow-up questions covered disclosure timing and calendar vs. business days.

## Artifacts
- None. The input was 9 module screenshots.

## Key findings
- **What TISA is:** A disclosure law for consumer deposit accounts (checking, savings, MMDA, NOW, CDs). It doesn't set rates or cap fees: "disclose, don't dictate." Business accounts aren't covered.
- **Memory hook "2-10-30":**
  - 2 years: record retention.
  - 10 calendar days: notice before a non-renewable CD over 1 year matures.
  - 30 calendar days: notice before an adverse change in terms.
- **Initial disclosures:** due before the account is opened or before any fee is paid, whichever comes first. Four buckets:
  - Rate: APY, rate, how long a fixed rate lasts, variable-rate terms.
  - Mechanics: compounding and crediting, balance method, when accrual starts on non-cash deposits, minimum balance.
  - Costs and limits: fees, withdrawal and deposit limits.
  - Extras: bonuses.
- **Initial disclosure exceptions under Reg DD:**
  - Consumer not present: 10 business days after opening or service.
  - Consumer requests disclosures: 10 business days if not present.
  - E-Sign electronic delivery allowed.
- **Auto-renewing CDs ("nothing, summary, everything"):**
  - 1 month or less: disclose only if terms change.
  - More than 1 month up to 1 year: renewal notice or a short notice.
  - More than 1 year: full disclosures again. Reg DD notice is typically 30 calendar days before maturity, or 20 days before the grace period ends if the grace period is 5 days or more.
- **Periodic statements** (quarterly or more often): APY earned and dollar interest; fees charged; NSF and returned-item fees for the period and year-to-date; days in the period or its dates.
- **Interest:** daily balance or average daily balance methods, on the full principal. Accrual starts no later than the business day the bank receives credit.
- **Advertising:** trigger terms (APY, bonus, overdraft protection) require extra disclosures. "Free" is prohibited if there's a maintenance or activity fee. This matters for BaaS partner marketing of "free" or high-yield accounts.
- **Quiz traps:**
  - Only adverse changes need notice.
  - NSF fees are totaled for the period and YTD.
  - "Periodic" means quarterly or more often, not monthly.
  - Notices before an event count calendar days; delivering disclosures after opening or a request counts business days.

## Decisions
- None.

## Open questions
- Program-specific TISA application: route to Compliance/Legal.

## Next steps
- Take the module quiz. Claude offered flashcards or a scored practice quiz if needed.

## Key sources
- Internal compliance training module (screenshots only).

## Resume prompt
> I'm Karl at Green Dot Bank, studying a TISA/Reg DD compliance module. Key hooks: "disclose, don't dictate"; 2-10-30 (2-year records, 10 calendar days before a non-renewable CD over 1 year matures, 30 calendar days before adverse changes); initial disclosures before opening or any fee; 10 business days for not-present or requested disclosures; auto-renew CDs follow nothing/summary/everything; periodic statements show NSF fees for the period and YTD; "free" is banned if there's a maintenance fee. Please help me with: a short scored practice quiz on this material.
