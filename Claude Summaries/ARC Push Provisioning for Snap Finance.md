---
type: claude-summary
session_id: local_580f37b4-4e53-4058-8157-8371381b2989
session_title: ARC push provisioning
last_synced: 2026-10-12
status: active
tags: [claude-summary, push-provisioning, snap-finance, digital-wallets]
---
# ARC Push Provisioning for Snap Finance
## Context
Karl asked how in-app push provisioning to Apple Pay and Google Pay works on the ARC BaaS platform. He then applied it to Snap Finance, which wants a single-use card, funded by a BNPL/installment loan disbursement, pushed straight into the user's mobile wallet. The PAN would be viewable as a fallback.

## Artifacts
- [Snap Finance - BaaS - Program Discovery](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2810609886/Snap+Finance+-+BaaS+-+Program+Discovery)
- [Dynamic Spend Controls](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2895216758/Dynamic+Spend+Controls)
- Offered to add open items to the Snap discovery page. Not done yet.

## Key findings
- **How push works:**
  - API: `POST /programs/{programCode}/accounts/{accountId}/paymentInstruments/{paymentInstrumentId}/pushProvisionData`
  - Apple: the app sends a nonce, its signature and the device certificate. ARC returns activationData and encryptedPaymentData.
  - Google: the app sends a device ID and wallet ID. ARC returns an encrypted payload (opc) plus address and phone in the clear.
  - The app never handles the raw PAN.
  - Token events come back through the auth feed to the same token webhooks used for manual provisioning.
- **Prerequisites:**
  - Manual provisioning first.
  - Push permission added to the partner's API credentials (engineering ticket; Product approves production access).
  - Apple: Team ID, Bundle ID and app ID, plus in-app provisioning entitlement. No sandbox, so testing happens in production via App Store promo codes; TestFlight can't be used.
  - Google: per-package API access. Before launch: 25+ cards added with 90%+ success, 3 taps per network, UX review, and launch approval.
  - Fraud controls: 2FA on new devices, verified phone numbers, account takeover training for support staff, and hiding push for risky accounts.
- **Proof points:**
  - Dayforce launched Apple push on 7/8/26. Provisioning attempts nearly doubled and success rose 2%.
  - Not receiving the verification code is the top wallet complaint across BaaS partners. Push skips that step.
- **Unconfirmed:**
  - Mastercard push parity on ARC (docs date from 2019–22 and are Visa-centric)
  - Google's newer "UAPP" integration (new 2026 keys)
  - Samsung Wallet on ARC
  - Open issues: a Mastercard velocity limit on wallet adds, and BINs that can't be added to wallets
- **Snap fit:**
  - The PAN fallback can use the hosted PCI widget's `CARD_DETAILS` activity (`POST /programs/{programCode}/hosted/ux`, 5-minute token). Confirm with Product: BaaS enablement, mobile web view rendering, and whether the 5-minute window is acceptable.
  - Wallet tokens also cover online and in-app Apple/Google Pay checkout, so the fallback population is smaller than Snap assumes.
- **Single-use issues:**
  1. The card must be active before the push call (error 400502).
  2. Unclear whether closing the card deletes the wallet token. Otherwise dead cards pile up across 1M+ loans a year.
  3. Refunds to closed cards.
  4. No confirmed automatic close after the first authorization. Incremental authorizations (tires, installation) complicate exact-amount loads.
  5. Account takeover risk.
  6. Moving from Discover to Visa helps, since ARC's Visa push integration is the most mature.
- **Biggest gap:**
  - Wallet taps go through ACI Base24, which can't decline by MCC or merchant ID. ARC also can't hand authorization decisions to the partner.
  - So push weakens Snap's merchant restriction (attribution, blocking firearms and adult merchants).

## Decisions
- Karl's model is valid: push from Snap's app with no PAN exposure, plus a PAN fallback.
- Pitch push and merchant restriction together, so push isn't read as solving the loan-card track.
- Raise a design alternative with Snap: one long-lived card added to the wallet once, loaded per loan, later becoming the DDA card. This avoids issues 2–4.

## Open questions
- For Product: token deletion when a card closes, automatic close after first use, refund routing, PCI widget for BaaS, Mastercard parity, UAPP.
- For Product/Architecture: the spend controls gap.
- Involve Compliance if the way loan proceeds are delivered changes.

## Next steps
- Add these open items to the Snap discovery page's Product/Architecture pre-check.
- Check the eWallet best-practices doc (Shelby Leonard, Nicol Przybylski) when it's published.

## Key sources
- [Push Provisioning (PROD)](https://greendot.atlassian.net/wiki/spaces/PROD/pages/94441657/Push+Provisioning)
- [BaaSAGW PushProvisionData](https://greendot.atlassian.net/wiki/spaces/WEB/pages/99239478/BaaSAGW+-+PayInst+-+PushProvisionData)
- [PCI Widget Integration](https://greendot.atlassian.net/wiki/spaces/EF/pages/916979808/PCI+Widget+Integration+Documentation)
- [eWallet Improvement](https://greendot.atlassian.net/wiki/spaces/BAAS/pages/2519400453/eWallet+Digital+Wallet+Improvement)
- [Google Push Provisioning UAPP](https://greendot.atlassian.net/wiki/spaces/TSE/pages/2462711809/Google+Push+Provisioning+UAPP)

## Resume prompt
> I'm scoping push provisioning on ARC for Snap Finance's single-use, loan-funded card. Push gives a no-PAN wallet add, and the PCI widget CARD_DETAILS can be the fallback. Open problems:
> - Wallet token removal when the card closes
> - Single-use enforcement and incremental authorizations
> - Refunds to closed cards
> - Base24 can't restrict merchants on wallet taps
>
> Alternative to raise: a long-lived card loaded per loan. Please help me with: [next task].
