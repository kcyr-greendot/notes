---
type: claude-summary
session_id: local_d608fd23-39d7-4581-a10a-39969a318ee9
session_title: Merchant restriction requirements
last_synced: 2026-10-12
status: active
tags: [claude-summary, spend-controls, iso-8583, closed-loop]
---
# Merchant Spend Restriction Requirements

## Context
Karl and Taylor brainstormed high-level requirements for restricting network-branded card spend to specific merchants or merchant subsets. Four use cases drove the discussion: Walgreens (Walgreens-only closed-loop wallet), Toast (Toast-powered merchants only), SSA (restricted-use SSI dedicated accounts, per POMS SI 02006.140) and Snap Finance (single-merchant, time-limited BNPL disbursements). All delivery paths were in scope: networks, a new processor such as Marqeta, or a Green Dot build.

## Artifacts
None. A Datadog search for ISO 8583 / DE42 / MTI logs found nothing, so the auth layer is not instrumented there.

## Key findings
- Restriction types:
  - A: single MID (Snap)
  - B: chain/brand (Walgreens, about 9K MIDs, plus Duane Reade)
  - C: acquirer/payfac (Toast)
  - D: MCC whitelist (SSA)
  - Modifiers: time-bound and amount-bound (Snap)
- SSA nuance: an impairment-nexus test plus an emergency override for basic needs. This requires a manual override and an annual payee accounting export, with fail-closed behavior.
- Three paths:
  - Processor-native controls (Marqeta, i2c): fastest, but means a bifurcated processor setup
  - Network controls (e.g., Visa Spend Clarity): good for MCC rules, weak for chain/payfac rules
  - A Green Dot-built issuer auth decisioning engine: most flexible, but needs sub-100ms latency and high availability
  - A hybrid was recommended.
- Cross-cutting requirements: a rules configuration API, program templates with card-level overrides, versioning and audit trail, decline reason visibility, fail-open vs. fail-closed design, refund/reversal handling (amount- and time-bound cards), and a policy for card-not-present transactions.
- ISO 8583 fields:
  - DE18 = MCC
  - DE32 = acquiring institution ID (the acquirer bank's ICA/BIN, not Toast itself)
  - DE42 = 15-character Card Acceptor ID
  - DE43 = free-text name/location (unreliable for rules)
  - Chain IDs and payfac data likely sit in network-proprietary private DEs (DE48, DE61) and need Visa/MC specs.
- Toast (as payfac) controls the DE42 format, so it can change without notice. DE32 is network-assigned and stable, but may cover all merchants of a shared acquirer (Toast has used Worldpay, Heartland and others). The likely rule is DE32 plus a DE42 pattern, unless Toast has a dedicated ICA.
- ACI concerns: does ACI expose DE32/DE42 to the rules layer, is rule configuration self-service, and is Green Dot on the modern ACI platform or legacy?

## Decisions
- Recommended phasing:
  - Near term: a processor partner (Marqeta/i2c) plus network MCC controls for SSA-type programs
  - Medium term: a lightweight Green Dot auth decisioning layer
  - Long term: a self-serve rules engine as a BaaS differentiator
- Auth-layer ISO samples are not in Datadog. Use ACI tooling instead.

## Open questions
- Does Toast have a dedicated acquiring ICA, and what is its DE42 format? (Toast)
- Which DEs are available as rule inputs in ACI, and is configuration self-service? (ACI technical team)
- Snap: what does "single use" mean, and how should partial spend and reversals be handled? (Snap Finance)
- Walgreens: is Walgreens.com (card-not-present) in or out? (Walgreens / BD)

## Next steps
- Pull sample auth records for known Toast-merchant transactions from ACI and inspect DE32, DE42 and DE43.
- Confirm ACI rule-input capabilities.
- Get Visa/MC specs for merchant enrichment in private DEs (chain ID).

## Key sources
- https://secure.ssa.gov/poms.nsf/lnx/0200602140
- https://increase.com/articles/iso-8583-the-language-of-credit-cards
- https://medium.com/@cliffsilla/iso-8583-technical-deep-dive-inside-the-message-5d06da238341

## Resume prompt
> I'm Karl (PSE, Green Dot). With Taylor, I'm defining requirements for merchant spend restrictions across four use cases: Walgreens (chain lock), Toast (payfac/acquirer lock), SSA SSI dedicated accounts (MCC whitelist plus emergency override) and Snap Finance (single-MID, time- and amount-bound virtual card). Options are processor-native (Marqeta/i2c), network controls (Visa Spend Clarity), or a Green Dot auth decisioning engine. The recommendation is a hybrid. For Toast, DE42 is Toast-controlled and unstable, while DE32 is stable but may be shared, so the rule is likely DE32 plus a DE42 pattern. ISO 8583 auth logs are not in Datadog. Open items: Toast ICA/DE42 format, ACI rule inputs, Snap lifecycle definitions. Please help me with: [next task].
