---
type: claude-summary
session_id: local_6db5b35d-a12c-4c0b-92c1-05c402e73a1a
session_title: Agentic control plane concept
last_synced: 2026-10-12
status: active
tags: [claude-summary, product-concept, agentic-commerce]
---

# Agentic Control Plane for Embedded Accounts

## Context
A product concept exploration. It was written up as an executive-summary page in Confluence under **PSE Opportunity Insights**, using the EBT/Forage page as the structural template.

The concept: an accountholder sets aside a fixed amount (example: $1,500 of $7,500) for an AI agent to spend, through a dedicated virtual card or token. The agent never gets the primary debit card. The buyer is **businesses running branded embedded finance programs**, not consumers.

## Artifacts
- Confluence page (published and updated): [Agentic Control Plane for Embedded Accounts](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2938699850/Agentic+Control+Plane+for+Embedded+Accounts)
- Related page linked from it: [Dynamic Spend Controls](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2895216758/Dynamic+Spend+Controls)
- Structural template: [EBT Balance Visibility via Forage](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2662891604/EBT+Balance+Visibility+in+BaaS+Partner+Apps+via+Forage+API+Integration)

## Key findings
- **The networks use a tokenization layer, not a new card type.** Visa Intelligent Commerce (on VTS) and Mastercard Agent Pay (on MDES) issue agent-specific network tokens on top of an existing card. Each token can be revoked independently. Commercial-side programs (Mastercard MVCT, Visa Commercial Solutions) are B2B only.
- **Mastercard enforces spend rules per token.** The July 2026 MDES release lets issuers enrolled in Agent Pay or MVCT set daily, weekly or monthly caps, a per-transaction limit, a lifetime cap, single-use tokens with expiry, and MCC or merchant allow/block lists. Mastercard declines transactions that break them.
- **Visa is less clear.** Its controls appear to come from the consumer's consent to the agent (caps, categories, time limits, bound to a passkey). Issuer-side enforcement isn't confirmed in public docs, and secondary sources conflict.
- **This could get around the MCC gap.** Our processor (ACI) can't use MCC at authorization today (see Dynamic Spend Controls). Network-enforced rules could make category scoping possible for Mastercard without that work.
- **Ring-fencing vs. capping.** A token on the primary card is only capped by rules. A dedicated virtual card with its own sub-balance, then tokenized, gives two layers: GD controls the funds and the network enforces the rules.

## Decisions
- **The page structure** follows the PSE Opportunity Insights pattern, written as a short executive summary.
- **The roadmap:**
  - Phase 1: a virtual card with a hard limit, expiry, alerts and a kill switch.
  - Phase 2: a **partner API wrapper** around network token controls (create, set rules, pause/revoke, list activity). This is the main way to deliver scoped spend.
- **Naming:** "Control plane" stays as the B2B/partner-facing term, because it accurately describes the architecture and fits the buyers. Consumer branding (e.g., "agent guardrails") is deferred.
- **A "Network-Native Controls" section was added** to the page.

## Open questions
- Can GD **push-provision** tokens to agents, or is GD's role only to approve requests from the agent platform and attach rules?
- Are our BINs eligible for Mastercard Agent Pay token controls? What are the fees? Does ACI support it?
- Does Visa offer issuer-side rule enforcement?
- Fund holding model: a separate sub-balance vs. a limit on the shared balance (needs ledger work).
- Liability for agent-made transactions, BSA/AML monitoring, and manual card-number hand-off to agents. These are routed to Compliance, Legal and InfoSec; no position taken.
- Current virtual card, per-card limit and sub-balance capabilities are marked "to be validated with Product/Engineering."

## Next steps
- Talk to the Mastercard relationship team about BIN eligibility, push provisioning and fees.
- Optional: add a one-line "control plane" definition under the page's info panel (offered, not yet done).
- Before this goes to leadership, replace the secondary/trade sources with Visa's and Mastercard's own announcements.

## Key sources
- [Mastercard MDES Release Notes, July 2026](https://developer.mastercard.com/mdes-customer-service/documentation/release-history/release-notes-july2026/)
- [Visa Intelligent Commerce – Visa Developer](https://developer.visa.com/capabilities/visa-intelligent-commerce)
- [Visa Commercial Solutions – Agentic AI](https://corporate.visa.com/en/solutions/intelligent-commerce/vcs-agentic-ai.html)

## Resume prompt
> I'm continuing work on the "Agentic Control Plane for Embedded Accounts" concept (Confluence: https://greendot.atlassian.net/wiki/spaces/PSE/pages/2938699850). Context: B2B offering for embedded finance partners. Phase 1 is a GD virtual card with a hard limit, expiry, alerts and a kill switch. Phase 2 is a partner API wrapper over Mastercard MDES Agent Pay per-token spend rules, with Visa still unconfirmed. Open items: push-provisioning rights, BIN eligibility and fees, Visa issuer controls, and the sub-balance vs. shared-limit funding model. Please read the current Confluence page first, then help me with: [next task].
