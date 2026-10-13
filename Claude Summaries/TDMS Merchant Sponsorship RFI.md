---
type: claude-summary
session_id: local_075b014d-2a40-4458-9425-b23239164c75
session_title: TDMS merchant sponsorship RFI
last_synced: 2026-10-12
status: active
tags: [claude-summary, rfi-qualification, acquiring, pin-debit]
---
# TDMS Merchant Sponsorship RFI

## Context
Ray forwarded an RFI invitation from TD Merchant Solutions (TDMS) seeking providers for merchant sponsorship models enabling PIN debit network participation (where TD Bank is not a direct member). Karl asked whether this is an acquiring rather than issuing need and likely not a fit.

## Artifacts
None

## Key findings
- Confirmed acquiring-side RFI: TDMS is a merchant acquirer needing a bank with direct PIN debit network membership to sponsor it for merchant acceptance.
- Scope signals: merchant sponsorship, network registration, connectivity, routing, transaction lifecycle, reconciliation for merchants, all acquiring infrastructure.
- Green Dot's BaaS/Arc platform is an issuer play; GD lacks acquiring-side network sponsorship and merchant routing infrastructure.

## Decisions
- Recommend passing on the RFI while keeping the relationship warm for possible issuing/embedded banking needs.

## Open questions
- Whether Ray knows of any GD acquiring-side sponsorship capability (routed to Ray)

## Next steps
- Reply to Ray / TDMS declining participation, leaving door open for issuing use cases

## Key sources
None

## Resume prompt
> I'm Karl (PSE, Green Dot). TD Merchant Solutions sent an RFI (via Ray) for PIN debit merchant/acquirer sponsorship. We concluded it's acquiring-side and not a fit for GD's issuer-focused BaaS/Arc platform; recommended declining but keeping the relationship warm for issuing needs. Please help me with: [next task].
