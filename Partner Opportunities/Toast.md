**June 24, 2026** - 
[Nikhil, Megan]

**June 17, 2026**
Green Dot: Ray, Adriana, Shannon, Taylor
Toast: Fergal, Mini

- update from us to Toast on where we're at
	- if you want to make it open loop ... you'll need to do KYC
	- Mastercard wants email / phone number - Fergal says no problem, we already have it for a Toast local user anyway.
	- Mini: can we upgrade a user from closed loop to full open loop?
		- yes, probably - we can work that out with Mastercard
	- **AFT pull from debit**  -> still open question of can we do this without KYC
		- Taylor thinks that Toast being a merchant aggregator unlocks the ability to do AFT
	- Fergal would like to push the limit as high as possible (within FinCEN)
	- Fergal: Ideally we can get past the aggregated gift card construct

> [!Fergal]
> "it could be dead on arrival if we're stuck to the gift card model"

- Shannon: next step is to run this past Mastercard and try to finalize

**June 15, 2026**
[Ray, Adriana, Shannon, Taylor]

- Ray's daughter is getting married this weekend 
- we need to provide a summary for what we're trying to do with Toast and send to MC
- tightening up the slides to share with Mastercard

**June 09, 2026** Internal post-call sync
[Shannon]

- why did we have to settle on the gift card purchase option? 
	- when we sold it to them we told them we could use AFT or ACH for in 
	- ECOM is live today; AFT is not 
	- we told them we'd do 110 bps and work with the network to negotiate better rates
	- ECOM 2% debit - 3% credit
	- for self-funding - we could launch with ECOM but the pricing was way too high - they built their model based on AFT 
	- Pathward / Fiserv - merchant acquirer for this 
	- Teresa flagged that Visa didn't give us approval to do AFT in for non-reloadable gift cards
	- you can't do AFT in on non-reloadable gift cards - "Toast lost their shit"
	- to make it up for them - we gave them rock bottom pricing and reduced platform fee

**June 09, 2026** - Mastercard Private Label Overview
Mastercard: Antonio
Green Dot: Shannon, Adam, Adriana, Taylor

- there's also an opportunity for Meijer here ... 
- Antonio - we can start a program out as PVL and upgrade it to prepaid or debit 
- no special requirements on the acquiring side - cards "just work"
- tokenization is a differentiator here 
- Issuer processor is responsible for limiting acceptance 
- standard interchange is based on product code / MCC combination
	- MC would use an existing prepaid product code that would drive IX calculation
	- Bilateral Interchange Agreement 
- regarding KYC - "we're always willing to evaluate variances"
- Antonio - we would have to go back to our compliance team and take this case to skip KYC - but we want to do it and work through it with you
- I gave him the Toast & Starbucks example... what we're trying to do. Antonio gets it (I think)


**5/29/26** - Internal
[Internal Follow up - Shannon, Pawel, Taylor]

- ![To Do](data:image/png;base64,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) I will follow up with nikhil and meghan about whitelisting MIDs for Toast - what will this take?
- Seems similar to Dayforce solution? Thye send us lists of MIDs from which accounts can be loaded

**5/29/26** - Call w/Mastercard
Mastercard: Cosku, Scott, Geri
Green Dot: Taylor, Ray, Shannon, Pawel

- Cosku: We cannot commit to a waiver but we will try
	- There are multiple things "working in our favor"
	- We'll take it back to our internal team to evaluate further

- Scott is an expert on Private Label solutions
	- Can be used for debit, credit or prepaid
	- Leverage all the goodness that Mastercard brings to the ecosystem for a closed loop environment
	- Easier onboarding for merchant
	- Auth - approval - settlement flows
	- Better fraud protection than gift cards - "cutting edge, future proof" protections

- Incremental work on our end to block out of scope transactions?
	- We'd have to keep the MID list updated within ACI
- Private label pricing works differently than other prepaid cards
	- We get charged for authroization attempts outside of private label network

- Follow ups:
	- Schedule something with Scott to learn more about Private Label

**5/28/26** - Call w/Toast
Toast: Fergal, Mini
Green Dot: Shannon, Ray, Taylor

- Still looking for this sweet spot where we have tap-to-pay but not
- Consumer strategy - drive guest traffic to our restaurants
- Toast Cash (current) great retention but not great adoption
- Over the last 8-9 months - been building out the
- Personalized loyalty, exclusive offers, no fee ordering, reservations
- Partnership with Amex / Resy for reservations (20k restaurants - one of the largest reservation marketplaces)
- Now is the time to revisit the payment flows to enable optimized user flows
- Do you have any forecasts for user adoption?
- Original forecasts would still hold true

**5/27/26**
Mastercard: Geri, Cosku
Green Dot: Shannon, Pawel

- The rule is any reloadable prepaid card needs IDV (doesn't necessarily require SSN - name and address should suffice)
- If it's private label card - and we have "near KYC" - we can do an exception - seems likely we can get approval for this exception

- What is required?

- Needs to be closed loop / only works at Toast
- Identifying / tagging customers (phone, email - velocity controls to prevent money laundering)

- Shannon's question - is Reg E a requirement?

- Ideally we don't want this to be in Reg E scope
- We have it on the acquiring side … but on the issuing side?

- Cosku - limits are still high - we would like to have a monthly maximum as well ($5000?)
- Has to be a prepaid cards, has to comply with Durbin & have "backup card"

- Toast has to commit that all txns are routed through Mastercard signature rails

- Private label is less expensive than prepaid

5/20/26

[Akhil, Shannon, Kara]

- Akhil - structure

- non-reloadable gift card purchased each time with a debit or credit card
- Internal ledger
- FIFO spending method
- User just sees the single aggregated balance
- You can purchase for yourself or buy for someone else

- Self buy can only be a debit card
- Not sure exactly why … might have something to do with

- Kara -

- We're going to have to go to Legal
- The minute a card becomes reloadable you're in CIP world
- Who made this decision

5/19/26 - Rebuilding a model for a prepaid product

[Shannon, Shane, Adriana]

- We spent $2M already on a Toast product that hasn't launched…
- How do we build out a model for a prepaid card?
- Focus is on Toast Pay for Toast purchases - outside spend
- We'd give them back interchange revenue but also pass on dispute costs and losses
- Return on bank capital - maybe not a lot here (are they going to have a lot of funds on the books?)
- Charge on cash in w/AFTs?
- $1M contribution over 170k actives - original projections - we're not going to get there - and that wouldn't move the needle today
- Shane's guess - 3 year contribution needs to be  $4-5M

5/14/26

Mastercard: Cosku

Green Dot: Pawel, Shannon, Taylor, Adriana

- "Cosku" - pronounced "Joshku"
- Private label cards are still Mastercards (prepaid, debit, credit)

- PL cards replace closed-loop private label card
- Partners Encouraged to remove the logo

- Can we have custom interchange for the specific private label merchant?

- Challenge is - who is the MOR? Is it Toast or is it

- Pricing shouldn't be drastically different for private label - it takes the rates associated with the card product classification
- Issuing fees are squeezed
- Do you have to go through CIP?

5/12/26

[Shannon]

- AFT and ECOM funds in - ended up costing the same … and was much more expensive than we originally thought
- We goofed… we cut them a deal for super cheap

Mastercard: Geri, Cosku

Green Dot: Shannon, Taylor, Pawel, Adriana

- Toast solving for the "simplicity of tap to pay"
- Cosku - "I love the idea"

- There are multiple ways of adjusting the economics
- Three options:

1. Custom bilateral rates - custom interchnage by BIN

2. Enrolling all the merchants is tough
3. If it's a PIN txn we don't see the txn - but Toast can ensure that they're submitted as signature txns

4. Tool developed for installments (1740 txn)

5. When there's a signature txns, right after clearing custom "economics" txn sent
6. Again dependent on Toast ensuring this is sent as signature txn
7. Pawel concerned about ACI support for this approach / Cosku thinks it's a non-issue, can be set up on MC backend with no ACI dependencies
8. Interchange flows through normally. Then at the time of clearing, a separate txn is sent to the acquirer (txn code 1740) to

9. Use Mastercard loyalty engine (local loyalty program)

- Pawel - re: interchange adjusted?

- It's a custom interchange looked up at the time of txn (not a retroactive reimbursement
- Looked up by product code, MCC, BIN and finds in exceptions table

- Cosku - "we see the value here and want to invest in this"

5/11/26

Toast: Fergal, Mini

Green Dot: Shannon, Adriana, Taylor

- Fergal - leads Fintech & Embedded Finance partenrships at Toast

- Prior to this - at PayPal - worked on PayPal - Green Dot integration since 2010

- Mini - leads payments product team
- Fergal & Mini - both based in Bay Area
- Toast Cash -> Toast Pay - "in store, NFC capable"
- Fergal open to Prepaid with AFT
- KYC requirements?

- KYC is the big hurdle here

- Mini - we see a lot of drop offs when IDV is involved

- Shannon - we can get some stats about KYC dropoff?

5/7/26

[Pawel, Adriana, Taylor, Shannon]

- Taylor's idea - we'll charge a per txn fee for Toast purchases, but reimburse all IX to Toast

- We'd keep interchange on non-Toast txns
- Pawel - this is a bad idea… fraud, customer support, chargebacks are going to cost us

- Ansa uses Visa rails to put the card in the top of wallet

- Assume we're not paying full interchange

5/5/26

[Shannon]

- Shannon met with Renata yesterday
- We spent over $2M to launch Toast Wallet … and they haven't launched
- Didn't get the economics right on the reboot - AFT on transaction

- ECOM to AFT - you can't reload

4/27/26

[Shannon, Taylor, Akhil]

- [Toast Pay Prepaid Opportunity](https://greendot365-my.sharepoint.com/:w:/g/personal/syonai_greendotcorp_com/IQA5YjKlrDQoQZcPqowEz9oKAQMJMqqdI-glxofnCZu1udI?wdLOR=cBF6A50A5-B8AE-3C4F-AC98-3583C1FB375B)
- We've been trying to launch Toast Cash for last 18 months
- Adoption is not great in Mass, no national rollout plan

- Too much friction with QR code scanning

- Dirt cheap fees to load cards
- Want to launch Toast Pay with digital wallet
- Akhil - what are they trying to focus on for this?

- Fergal says the QR code scan is too much friction
- Akhil says he can use tap to pay on

6/26/25

Toast: Nealy Varney, Gautm Tankha, Ani Boyo, Fergal Finnan, Suket Somani

Green Dot: Taylor, Shannon Yonai

- Nealy's best friend (Ginny Broadwater) lives in North Yarmouth!

- They're going to Acadia for the 4th of July

- Apple Pay integration - putting Toast Cash wallet into ApplePay
- Today - we don't support tokenization on "private network" cards
- Ansa (3rd party) can support integration - we'd have some build on our side to do this
- We should approach both networks to see who might have a good option for this
- Nealy: We already have an on-prem QR code integration
- Fergal: we want to use Apple VAS (Value Added Services) - proprietary NFC protocol developed by Apple for use with Apple Wallet passes