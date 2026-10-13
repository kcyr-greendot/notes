---
type: claude-summary
session_id: local_173a6c43-357f-4454-99da-7ff1ee33ca86
session_title: Digital wallet terminology
last_synced: 2026-10-12
status: active
tags: [claude-summary, digital-wallets, payments-taxonomy]
---
# Digital Wallet Taxonomy

## Context
Karl argued that "digital wallet" is overused and ambiguous in fintech and often masks imprecise understanding. The goal was to split the term into distinct solution classes with precise names so he can quickly disambiguate it in sales and discovery conversations.

## Artifacts
None

## Key findings
- Proposed classes:
  - 1. Tokenized credential / passthrough wallet (Apple Pay, Google Pay, Samsung Pay): no stored value, no new account; a tokenized pointer to an existing card.
  - 2. Stored value / digital account (Apple Cash, prepaid; Venmo/Cash App balances): de facto bank or prepaid-access account with lightweight UX; top-up model.
  - 3. Closed-loop commerce wallet (7-Eleven 7Rewards, Starbucks): closed-loop stored value, closer to gift card law.
  - 4. Crypto wallets: split custodial (Coinbase, behaves like #2) vs self-custody (MetaMask, Ledger; key management).
  - 5. Virtual account / subledger (GD "purse"): earmarked partition of a larger account.
  - 6. Multi-rail payment orchestrator (PayPal, Venmo as typically used): pulls funds from an external account at transaction time; value is abstracting which instrument funds a payment.
  - 7. Benefits / government disbursement wallet (EBT/SNAP): restricted by eligible spend categories; distinct compliance posture.
- Three-question framework for any "wallet": where funds live, what credentials are stored, where funds can be spent.
- Key differentiator: at the moment of transaction, where does money come from (no movement / pre-loaded balance / pull-at-transaction).
- Many products span categories (Venmo and PayPal are both #2 and #6; Apple Wallet spans #1, #2, #6).

## Decisions
- Claude initially offered to drop #6, but Karl's point (Venmo usage pulls from BofA on the fly) restored it as a distinct "multi-rail payment orchestrator" class.

## Open questions
- Final naming for each class and whether #7 stays separate from #3.
- Whether to formalize into a shareable one-pager or slide.

## Next steps
- Finalize the class names and definitions.
- Optionally build a reference table or slide for sales and discovery use.

## Key sources
None cited

## Resume prompt
> I'm building a taxonomy to disambiguate "digital wallet." Current classes: (1) tokenized credential/passthrough (Apple Pay); (2) stored value/digital account, top-up model (Apple Cash); (3) closed-loop commerce (Starbucks, 7-Eleven); (4) crypto, custodial vs self-custody; (5) virtual account/subledger (GD purse); (6) multi-rail payment orchestrator, pull-at-transaction (PayPal, Venmo as typically used); (7) benefits/government disbursement (EBT). Diagnostic questions: where funds live, what credentials are stored, where funds can be spent, and where money comes from at transaction time. Please help me with: [next task].
