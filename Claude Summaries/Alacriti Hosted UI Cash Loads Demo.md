---
type: claude-summary
session_id: local_243c2f8b-5a57-43c6-8816-42541077652a
session_title: Hosted UI cash loads demo
last_synced: 2026-10-12
status: active
tags: [claude-summary, alacriti, hosted-ui, gdn]
---
# Alacriti Hosted UI Cash Loads Demo
## Context
Alacriti wants to use Green Dot's hosted UI for cash loads. Karl had only seen static screenshots and wanted to find the source code so he could run a live demo of the experience. The research found the repos, but recommended demoing the QA environment hosted on Azure rather than building locally.

## Artifacts
- Repos in the Green-Dot-Corporation GitHub org:
  - `MMGDN-AFSWEB-AddCashRegisterWeb`: the hosted UI itself (addcash.attheregister.com)
  - `MMGDN-COM-AddCashRegGhostLogin`: ghost login test page that simulates the partner hand-off in non-prod
  - `MMGDN-WEB-Secure.AtTheRegister.Com`: related; unclear whether it hosts the bill pay flow
  - `GDN-k8s-state` and `GDN-DeployConfig`: deployment config
- Legacy Perforce path: `//DotNet/current/Web_Solutions/GDFN/AddCashRegisterWeb/`
- QA environment URLs:
  - Ghost login: https://addcashregghostlogin.qa.eus.azkubegdnnp.com/
  - Hosted UI: https://qa-addcash.attheregister.com/
  - DEV versions of both are also running.

## Key findings
- The hosted UI is the eCash "Redirect" portal, also called AddCash@TheRegister. The customer picks a retailer, gets a barcode, and chooses on-screen, SMS, email or print delivery.
- Building locally is hard: legacy .NET MVC on Windows IIS, extra content folders and a staging certificate, GDN back-end dependencies, and an out-of-date container setup with failing builds.
- The platform team migrated it to Azure. The status page (updated Sep 22) shows QA and DEV running.
- The QA walkthrough (2018) explains the flow: ghost login → pick a partner → retailer → barcode → SMS/email/print. Its URLs are old on-prem addresses (necla, qa3/qa4 nextestate); use the Azure URLs instead.
- Today partners can only white-label their name and logo. The White-label 2.0 design (configurable text, fonts and colors, data-collection page, cross-retailer barcode) is documented, but there's no evidence it shipped.
- The Alacriti Solution Overview Word file in Karl's folder still says "Narmi" in the body text, copied from the Narmi version. Fix before sending.

## Decisions
- Demo the Azure QA site instead of building locally.
- Use only the documented test accounts or synthetic data.

## Open questions
- Is the QA environment stable enough for a partner demo, and is VPN or network access needed? Ask Gerardo Osuna (Azure migration owner, GBOS-213409).
- Does Alacriti's bill pay use the same add-cash redirect or a separate bill pay configuration? Ask Gerardo or the GDN product owner.
- Has any White-label 2.0 feature shipped?

## Next steps
- Contact Gerardo Osuna about QA access and stability.
- Walk the flow using the ECash Test Accounts page.
- Remove the "Narmi" references from the Alacriti Solution Overview.

## Key sources
- [GDN Websites Azure Status](https://greendot.atlassian.net/wiki/spaces/CBS/pages/2891285036/GDN+Websites+Azure+Status)
- [Generate barcode/link web flow for Addcash partners](https://greendot.atlassian.net/wiki/spaces/MOTXQA/pages/99882419/Generate+barcode+link+web+flow+for+Addcash+partners)
- [ECash Test Accounts for Partners](https://greendot.atlassian.net/wiki/spaces/MOTXQA/pages/99890052)
- [eCash Redirect Page White label](https://greendot.atlassian.net/wiki/spaces/GDN/pages/95724257/eCash+Redirect+Page+White+label)
- [Setup of AddCashRegisterWeb](https://greendot.atlassian.net/wiki/spaces/QABEMM/pages/74877232/Setup+of+AddCashRegisterWeb)

## Resume prompt
> Alacriti wants to use our hosted cash-load UI (the eCash Redirect / AddCash@TheRegister portal). The code is in `MMGDN-AFSWEB-AddCashRegisterWeb` plus the ghost login repo, but a local build is impractical. Plan: demo QA on Azure:
> - Ghost login: https://addcashregghostlogin.qa.eus.azkubegdnnp.com/
> - Hosted UI: https://qa-addcash.attheregister.com/
>
> Use the ECash Test Accounts page. Pending: Gerardo Osuna on QA stability and access, whether bill pay uses the same redirect, and removing "Narmi" from the Alacriti doc. Please help me with: [next task].
