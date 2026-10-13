---
type: claude-summary
session_id: local_e9a81b64-6b0f-4eb2-9ceb-5a8516265884
session_title: Moneypak card tokenization
last_synced: 2026-10-12
status: active
tags: [claude-summary, moneypak, tokenization, mobile-wallets]
---
# MoneyPak Mobile Wallet Tokenization

## Context
Quick Q&A: can MoneyPak be tokenized into Apple Pay, Google Pay, or Samsung Pay? Intended to inform BD conversations.

## Artifacts
None

## Key findings
- No. MoneyPak is a cash reload voucher, not a payment card: customer buys at retail, reveals a scratch-off code, and directs funds to a destination account (prepaid card, bank account, etc.).
- There is no underlying card credential (PAN, expiry, CVV) tied to MoneyPak, so Visa/Mastercard cannot issue a wallet token against it.
- MoneyPak is a funding/load instrument, not a spend instrument.

## Decisions
- For partners wanting mobile wallet acceptance, position a Green Dot-issued card (e.g., BaaS debit card on GBOS/Arc), not MoneyPak.

## Open questions
None

## Next steps
- Use this framing in BD conversations where mobile wallet support comes up

## Key sources
None

## Resume prompt
> I'm Karl (PSE, Green Dot). Confirmed MoneyPak is not tokenizable in Apple/Google/Samsung Pay because it's a cash reload voucher with no PAN; it sits on the load side of money movement. Partners needing mobile wallets should get a GD-issued debit card on GBOS/Arc. Please help me with: [next task].
