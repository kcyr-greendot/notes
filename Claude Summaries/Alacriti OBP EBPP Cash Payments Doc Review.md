---
type: claude-summary
session_id: local_fec30522-2fda-4a25-884e-448264a9a7e6
session_title: OBP EBPP Cash Payments document review
last_synced: 2026-10-12
status: active
tags: [claude-summary, alacriti, cash-bill-pay, gdn]
---
# Alacriti OBP EBPP Cash Payments Doc Review
## Context
Karl asked for a review of Alacriti's "OBP EBPP Cash Payments Retail Functional" document, written by Stuart at Alacriti. The review compared it against Green Dot's developer docs, the September Hosted UX solution guide, and the GDN Cash Loads Confluence page, to flag discrepancies before Karl replies to Stuart. The review then found a settlement error in Green Dot's own solution guide, which Karl fixed.

## Artifacts
- Files in Karl's Alacriti folder:
  - OBP EBPP Cash Payments Retail Functional 0926-1 (1).docx
  - Alacriti Cash Bill Pay – Solution Overview – September 2026 (Hosted UX Version).docx (edited by Karl)
  - Alacriti – Cash Loads Solution Overview – March 2026.docx
- [GDN Cash Loads (Confluence)](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2531164461/GDN+Cash+Loads)

## Key findings
Discrepancies in Stuart's doc, most important first:
1. **CSRs can cancel "Approved" payments.** This shouldn't be allowed: an AuthCommit can't be declined and is retried every 3 minutes for up to 10 hours. Only "Accepted/Staged" should be cancellable.
2. **AuthVoid is misunderstood.** Stuart describes it as the consumer changing their mind. It is actually sent on a timeout or a register void within about 30 seconds. Alacriti must also return "00" when it can't find the Auth or has already voided it.
3. **Settlement** (see Decisions).
4. **Barcode expiry mismatch.** Stuart says never, or up to 72 hours. The guide says 1 hour on screen and 48 hours for print/SMS/email. EBPP also has no creation timestamp to base expiry on.
5. **Overlay/iframe launch is unconfirmed.** Green Dot's docs describe a full POST redirect with client certificate checks and IP whitelisting.
6. **Required payer fields are missing.** Bill pay requires senderfirstname, senderlastname, senderaddress, senderzipcode and senderaccountno. Without the biller-side name and address, transactions are blocked in IL, NJ and WV.
7. **Fee ownership is unclear.** The store collects the fee and settlement nets it out. Avoid charging or showing the fee twice.
8. **Technical requirements are omitted:**
   - 4-second Auth deadline
   - Ping health-check service
   - AuthCommit must be safe to receive more than once (retries share the same OriginalConfirmationID)
9. **Other gaps:**
   - No handling for payments stuck in "Approved" (AuthLifeSpan)
   - Whether a barcode can be reused after a decline
   - accountno (payee) vs. senderaccountno (payer) mapping
10. **Claims to verify:**
    - Store count: 90k vs. 65k+
    - Refunds on the 2027 roadmap (unconfirmed)
    - "Real time": the biller is paid in a daily batch
- **Internal inconsistency:** the March overview says Green Dot does KYC. The GDN Cash Loads page says OFAC screening only, no KYC of end customers. Don't send the March doc to Alacriti.

## Decisions
- **Settlement model:** Green Dot settles to Alacriti, and Alacriti settles with its billers. The guide wrongly said Green Dot settles directly with billers.
- Karl fixed and verified four spots:
  - Solution Overview paragraph
  - Settlement section (daily batch to Alacriti; subpartnerid optional and for reporting only)
  - Alacriti's Responsibilities bullet
  - subpartnerid changed to Optional in the payload table

## Open questions
- Optional wording tweak: the subpartnerid description still says "biller receiving the payment."
- Does Alacriti need money transmitter licensing for its new role of settling to billers? Route to Legal/Compliance.
- Items 6 and 7 (required fields, state blocking, fees) go to Compliance before replying to Stuart.
- Engineering to confirm whether the hosted page can load in an iframe.
- Product to confirm the refund roadmap wording and the current store count.

## Next steps
- Send Stuart the list of discrepancies (items 1, 2, 4–11).
- Get the Compliance review of required fields and fees.
- Fix or retire the March solution overview (KYC claim).

## Key sources
- [Barcode Generation](https://developer.greendot.com/embedded-finance/docs/barcode-generation-2)
- [Retail Consumption Overview](https://developer.greendot.com/embedded-finance/docs/overview-3)
- [AuthCommit](https://developer.greendot.com/embedded-finance/docs/authcommit-1)
- [AuthVoid](https://developer.greendot.com/embedded-finance/docs/authvoid)
- [GDN Cash Loads](https://greendot.atlassian.net/wiki/spaces/PSE/pages/2531164461/GDN+Cash+Loads)

## Resume prompt
> I'm reviewing Alacriti's (Stuart's) OBP EBPP Cash Payments functional doc against our cash loads docs. Key issues found:
> - CSR cancel of Approved payments
> - AuthVoid semantics
> - Barcode expiry (1 hour / 48 hours)
> - iframe launch
> - Required sender fields (IL/NJ/WV blocking)
> - Fees
> - 4-second Auth deadline, Ping service, AuthCommit retries
> - Store count and refund claims
>
> I've fixed our September solution guide so Green Dot settles to Alacriti and Alacriti settles billers; subpartnerid is now optional. Pending: Compliance review of fields and fees, the money transmitter question, and the iframe check. Please help me with: [next task].
