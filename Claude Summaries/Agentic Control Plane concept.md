---
type: claude-summary
session_id: local_6db5b35d-a12c-4c0b-92c1-05c402e73a1a
session_title: Agentic control plane concept
last_synced: 2026-10-16
status: active
tags: [claude-summary, product-concept, agentic-commerce]
---

# Agentic Control Plane for Embedded Accounts

## Context
A product concept exploration. It was written up as an executive-summary page in Confluence under **PSE Opportunity Insights**, using the EBT/Forage page as the structural template.

The concept: an accountholder sets aside a fixed amount (example: $1,500 of $7,500) for an AI agent to spend, through a dedicated virtual card or token. The agent never gets the primary debit card. The buyer is **businesses running branded embedded finance programs**, not consumers.

Latest activity: Karl shared a Visa industry-trends deck (Oct 2026, marked Visa Confidential) and asked whether it changes the thinking. It refines the Visa side but doesn't change the core concept.

## Artifacts
- Confluence page (published and updated): [Agentic Control Plane for Embedded Accounts](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2938699850/Agentic+Control+Plane+for+Embedded+Accounts)
- Related page linked from it: [Dynamic Spend Controls](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2895216758/Dynamic+Spend+Controls)
- Structural template: [EBT Balance Visibility via Forage](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2662891604/EBT+Balance+Visibility+in+BaaS+Partner+Apps+via+Forage+API+Integration)
- Uploaded Visa deck (SBECC Master Deck, Oct 2026). Visa Confidential, need-to-know inside GD; may include MNPI. Not copied here.

## Key findings
- **The networks use a tokenization layer, not a new card type.** Visa Intelligent Commerce (on VTS) and Mastercard Agent Pay (on MDES) issue agent-specific network tokens on top of an existing card. Each token can be revoked independently. Commercial-side programs (Mastercard MVCT, Visa Commercial Solutions) are B2B only.
- **Mastercard enforces spend rules per token.** The July 2026 MDES release lets enrolled issuers set caps, per-transaction and lifetime limits, single-use tokens with expiry, and MCC or merchant allow/block lists. Mastercard declines transactions that break them.
- **Visa sends signals to the issuer instead of enforcing rules (per Visa briefing).** Its model rests on bank ID&V at token creation, agent-bound tokens, biometric cardholder verification and intent data. Visa is phasing in issuer-facing agent signals (agent-requested token flag, agent ID, purchase-context indicator, intent data API) [redacted – partner confidential: specific roadmap dates]. So for Visa, GD would have to enforce rules in its own authorization, which runs into the same MCC gap as Dynamic Spend Controls.
- **This could get around the MCC gap for Mastercard.** Our processor (ACI) can't use MCC at authorization today. Network-enforced rules could make category scoping possible for Mastercard without that work.
- **Ring-fencing vs. capping.** A token on the primary card is only capped by rules. A dedicated virtual card with its own sub-balance, then tokenized, gives two layers: GD controls the funds and the network enforces the rules.
- **Visa may cover step-up approval.** Its per-transaction biometric check could replace a GD-built approval step, though it adds friction to hands-off agent purchases.
- **Positioning and demand are confirmed.** Visa's sponsor-bank readiness framing ("recognize and control agent-led activity") closely matches the control plane pitch. The deck cites live agentic commerce from Meta and Amazon and strong consumer AI shopping adoption. Liability and agent error handling are flagged as open industry problems.

## Decisions
- **The page structure** follows the PSE Opportunity Insights pattern, written as a short executive summary.
- **The roadmap:**
  - Phase 0 (proposed): network readiness. Enable agentic token provisioning in Visa's Cloud Token Framework and use strong ID&V at token creation.
  - Phase 1: a virtual card with a hard limit, expiry, alerts and a kill switch.
  - Phase 2: a **partner API wrapper** around network token controls (create, set rules, pause/revoke, list activity). This is the main way to deliver scoped spend.
- **Naming:** "Control plane" stays as the B2B/partner-facing term. Consumer branding (e.g., "agent guardrails") is deferred.
- **A "Network-Native Controls" section was added** to the page.

## Open questions
- Can GD **push-provision** tokens to agents, or does GD only approve requests from the agent platform and attach rules?
- Are our BINs eligible for Mastercard Agent Pay token controls? What are the fees? Does ACI support it?
- Visa: confirm that issuer-side enforcement is GD's job, and where partners should set the biometric approval threshold.
- Fund holding model: a separate sub-balance vs. a limit on the shared balance (needs ledger work).
- Liability, BSA/AML monitoring and manual card-number hand-off to agents. These are routed to Compliance, Legal and InfoSec; no position taken.
- Can Visa deck details go on the PSE Confluence page? It depends on the space's audience; check with Compliance if unsure.

## Next steps
- Decide whether to update the Confluence page with Visa insights: a sanitized high-level line (default) or full detail if the audience allows. Offered, waiting on Karl.
- Talk to the Mastercard relationship team about BIN eligibility, push provisioning and fees.
- Optional: add a one-line "control plane" definition under the page's info panel.
- Before this goes to leadership, replace the secondary/trade sources with Visa's and Mastercard's own announcements.

## Key sources
- [Mastercard MDES Release Notes, July 2026](https://developer.mastercard.com/mdes-customer-service/documentation/release-history/release-notes-july2026/)
- [Visa Intelligent Commerce – Visa Developer](https://developer.visa.com/capabilities/visa-intelligent-commerce)
- [Visa Commercial Solutions – Agentic AI](https://corporate.visa.com/en/solutions/intelligent-commerce/vcs-agentic-ai.html)
- Visa SBECC deck, Oct 2026 (Visa Confidential; the agentic section and the sponsor-bank readiness slide)

## Resume prompt
> I'm continuing work on the "Agentic Control Plane for Embedded Accounts" concept (Confluence: https://greendot.atlassian.net/wiki/spaces/PSE/pages/2938699850). Context: B2B offering for embedded finance partners. Phase 0 is network readiness (agentic token provisioning, strong ID&V). Phase 1 is a GD virtual card with a hard limit, expiry, alerts and a kill switch. Phase 2 is a partner API wrapper over Mastercard per-token spend rules. Visa sends signals to the issuer rather than enforcing rules, so GD must enforce for Visa. A Visa confidential deck informed this; keep its specifics off the wiki unless the audience is cleared. Open items: push-provisioning rights, BIN eligibility and fees, the sub-balance vs. shared-limit funding model, and whether to add sanitized Visa insights to the page. Please read the current Confluence page first, then help me with: [next task].
