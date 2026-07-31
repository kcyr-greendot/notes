**July 30, 2026**
Bakkt: Aayur, Marc, Ankit
Green Dot: Waylon, Ray, Akhil 

- Aayur: 
	- KYC - Bakkt collects the information, GD uses Socure to perform KYC
		- Bakkt's only touch with Socure is with customers who need todo IDV stepup - Socure SDK
	- ankit - "KYC reliance has always been a requirement for us - this is a miss"
		- Ray - we didn't set it up that way. we like your process but we didn't agree to do reliance
		- Ankit - that's a big miss
		- Ray & Akhil - this is in the SOW and agreement 
		- Ankit is very concerned about the onboarding experience 
- eSim with monthly subscription fee ($15/mo)
	- waive the fee if the user is doing direct deposit
	- two tiers: 
		- free plan ($0 MMF)
		- paid tier w/eSim ($15 MMF)
			- MMF is waived if direct deposit enabled 
	- Akhil: this is supported but there's some challenge in how customers change fee plans 

**July 13, 2026**
[Veronica, Paul, Akhil, Ray, Waylon]

- Paul concerned about non-standard Bakkt requirements
- Five use cases...
	- Fee Settlements (eSIM & Value Add Services)
		- can we run this as Private Network Transactions? 
	- Subscription and Tiers (v2)
		- are they charging their own version of a MMF? 
		- Akhil says: 
			- either, set it up as a MMF and waive for some people; or it's MMF
		- this is for us to manage, not them. 
	- Cross-border remittance
		- this one we're ok with - has been a use case from the start
		- Akhil - use Adjustments API for ledger adjustments 
	- Interest Payouts & APY Bonus Rewards
		- we do standard interest calculations and 1099s
		- Akhil & Ray think they might just be confused about how this is being calculated - what do they actually mean? 
		- our system works to calculate the interest - use our engine
	- Instant ACH Pull Frontloading (Risk-Based Availability)
		- "Akhil - operationally, i'm confident we have the plumbing in place to do this"
		- Paul: are you confident we can do this operationally? 
		- Akhil - it's challenging to figure out how to prefund the first one only vs. prefunding all of them - but if we can default to prefunding all of them, that's a much easier problem
		- Paul - I don't want to push this forward for MVP if we haven't figured out how to operationalize this yet
- Akhil working on a SOW for end of this week to lock down MVP scope 

**July 09, 2026**
Bakkt: Aayur, Marc, Ankit
Green Dot: Paul, Waylon, Wyn, Taylor, Satheesh

- outstanding technical questions in Slack waiting for answer
- Aayur looking for ACH-based "instant funding" - i.e. early access to ACH transfer
	- credit with an Adjustment
	- wanted for MVP
	- [ ] put together a solution guide for this 
- Marc - question about ACH return codes - I don't fully understand all of the situations where I could receive these codes? 
	- [ ] look into this (Marc's question on Slack)

**July 02, 2026**
Bakkt: Aayur, Marc
Green Dot: Ray, Taylor, Akhil, Waylon, Satheesh

- Aayur - we want to know more about the fraud monitoring capabilities
	- Akhil: Andrew Fong left teh company so we're looking to get something scheduled with his replacement (Veronica to schedule)
	- Forter is the monitoring system for AFT 
	- Plaid or Finicity for ACH
	- PRM - fraud monitoring built into processing engine 
	- Money Guard - user-based real-time transaction validation ("do you recognize this transaction?")
	- Aayur - this is good information, we don't necessarily need a meeting if we can just get this documented
- Bakkt wants to increase limits - getting internal approvals, doesn't seem like it's an issue
- Marc - we are expecting to get PIE access July 7 
	- can we get testing data for these transaction types? 
- Taylor: questions from our side (risk team)
	- do we have the UX samples for review? need to understand where balances are displayed, especially in txns related to crypto
		- there's no crypto products or balances in this app
		- initial launch is fiat debit card, credit card to be added later
	- any plans to use the Adjustments API to credit / debit account directly? 
		- Marc: no because the API is due to be deprecated - but we will use Transfers API
		- funds are being moved between primary spend account and savings purse
		- also - between checking account and FBO - to support instant transfer on ACHs


**4/16/26**
Bakkt: Marc, Przemek, Aayur
Green Dot: Akhil, Satheesh, Ray

- Przemek: can we have the ability to approve/reject an incoming ACH?
- Interested in catching the fraudulent use case - what happens if Bakkt wants to block a transfer / transaction?
- What do webhooks look like?

**3/26/26**
Bakkt: Marc, Aayur
Green Dot: Karl, Veronica, Akhil, Ray, Satheesh

- What happens if ach is returned?
- Accounts can go in the negative and stay that way for 6 months
- Ultimately the contract will dictate what happens with negative accounts - typically partner will cover

**3/19/26**
Bakkt: Aayur, Marc
Green Dot: Karl, Paul, Veronica, Satheesh

- Where's Ramia?

**2/26/26**

Bakkt: Marc, Aayur, Przemek

Green Dot: Akhil, Satheesh, Waylon, Ericka, Ray

- Marc asking for ATM locators

- Sent: [https://developer.greendot.com/embedded-finance/docs/retail-atm-locators](https://developer.greendot.com/embedded-finance/docs/retail-atm-locators)

- Bank lookup API call not working in Sandbox

- It probably just doesn't work on Sandbox

- Webhooks not working on Sandbox since Tuesday - what happened?

- Satheesh - there was an outage on the sandbox

2/5/26

Bakkt: Przemek, Aayur, Joanna, Marc

Green Dot: Akhil, Satheesh, Ramia, Ray,

- Testing in sandbox 1 - access working well
- ACH Out not working - "schema is malformed"

- Satheesh - should be working but needs to check configuration

- Get card Details (PCI compliant UX for gathering sensitive data) returns 400

- This should work too

- Webhook (testeventwebhook) not working

- Satheesh - should be working

- What level of testing with debit cards can we do on sandbox?

- No real world testing of card txns - need to do this in production
- Everything is simulated - we have QA scripts that can simulate this (but nothing that Bakkt can initialize for themselves)

- What is estimated timeline for PIE?

- Contract finalization is obviously key

- Wires is getting deprioritized… probably Q3 delivery now

1/29/26

Bakkt: Przemek, Aayur, Ankit, Marc

Green Dot: Ramia, Satheesh

- What happens when the virtual card is deactivated when physical card is issued?

- Virtual card is permanently disabled

- Fees for issuing cards?

- No fee by default, you can set fees at a program level
- You can charge a fee for card replacement if you want
- Need to put this in the T&Cs for the users and change configuration - not something you can do on the fly but easy enough to set up on an ongoing basis

- Does Green Dot provide only monthly statements or does it also provide a txn statement

- Yes - we have an API for that - you can access transactions and display how you wish

- Any limits to how many times a card can be frozen/unfrozen?

- No
- At an account level… you can lock and unlock, but this is more complicated and rqeuires GD backoffice

- Do we receive sender name information in the webhook for a ACH?

- No - but you can look up more information based on the information contained in the webhook (sender information is in the txn details

- QR code on the mailer

- Our business ops team will work with you - you can point the QR code at anything you want, we'll work with you to figure it out

- Direct Deposit switch -

1/22/26

Bakkt: Przemek, Aayur

Green Dot: Taylor, Akhil

Przemek questions:

- How long can an account stay in "restricted" status as part of normal account closure?

- 60 days - then we send a refund check with any remaining balance.

- What messaging do we get if an ACH transaction is rejected (NOC message)?

- [https://developer.greendot.com/embedded-finance/docs/webhook-samples#ach-noc-alert-webhook](https://developer.greendot.com/embedded-finance/docs/webhook-samples#ach-noc-alert-webhook)
- We won't block transactions if they fail - but if you keep trying and they keep failing, we'll keep trying them with the outside bank.

1/8/26

Bakkt: Przemek, Marc, Aayur

Green Dot: Ramia, Taylor, Karl, Satheesh

- Bakkt provided new IPs for whitelist - Ramia will take care of this
- Webhooks - Bakkt endpoints have been whitelisted
- Ramia will create client credentials, sample payloads and a certificate for encryption on Sandbox 1
- Ramia will provide Webhook samples and lists of webhooks that can and cannot be tested in the Sandbox environment
- Marc - questions about transaction webhooks and how to handle failed transactions
- Tier 1 Support goes to Bakkt / Tier 2 escalated to Green Dot - we will do the account servicing
- Aayur - what happens if a subscription is started on the virtual card and then a physical card is updated?

- PAN stays the same but CVV and expiration changes
- We do have an account updater when the card is reissued after expiration, not sure if that applies for this scenario though

12/18/25 - Weekly Integration Sync

Bakkt: Aayur, Przemeslaw, Marc, Aram, Julia

Green Dot: Ramia, Taylor, Akhil, Karl, Ray, Satheesh

- Bakkt is currently in Sandbox but waiting on access to Sandbox 1
- Przemek

- Can we test debit cards in our current Sandbox?  (e.g. simulating a transaction)

- Ramia - we can in Sandbox 1 but not in their sandbox

- Are webhooks grouped?

- Ramia - they're sent immediately - no batching for one-off events
- Akhil - we send an end of day webhook reconciliation file (encrypted and dropped to FTP folders)

- Can we passed a tokenized account number to Green Dot instead of an actual account number (for account linking for ACH)?

- When we link an account via Plaid, you get back a plaid link token- we don't know what that means
- But if the tokenized values make sense to the end bank account and clearing house, there's no problem
- In other words… if Bakkt passes a tokenized account # to Green Dot, we will pass that to NACHA. If NACHA and the receiving bank can make sense of that information then this should work.

- What is the standard settlement time for ACH Pull?

- Could be same day, typically next business day
- Return period will

- Push-to-Card - how will this work? We're not PCI compliant?

- Step 1 - create customer profile
- Step 2 - link target card via hosted UX
- Step 3 - Run transfer
- PCI compliance and UX

- If Bakkt is using the PCI widget, we can handle this all in the UX
- Widget handles all PCI data and returns the link token

- Pull -from-card

- We need to set up your program for acquiring with Fiserv
- This is a bit more complicated and make take longer than the (super fast) timeline you have

12/4/25 - Risk Assessment

[Pierce, Sajal, David]

- Sajal - we've made good progress
- Sajal: "Risk seems very high… I am uncomfortable" with company stability, strategic shifts, financial performance, etc.
- David … we already went through TPRM in the past 30-60 days
- Real-time interest calculation - we don't want to do this

11/26/25

Debit Cards

What is the fee for adding funds via an external debit card?

|   |
|---|
|3% of the amount transferred to your primary deposit account, subject to a $2.00 minimum and rounded to the nearest cent. A max fee can also be set and is generally set based on the maximum amount the customer can transfer.|

What fields do we need to capture if someone needs to add funds to their account via an externall debit card? Like Do we need name and zipcode along with card details?

Can a user fund their account with a debit card not under their name? For ex: Their sister's?

How is this payment processed? Is there a processor in between like 3DS in EU?

These payments are processed through the card network (Mastercard Send or Visa Direct)

Daily/monthly limits on transaction amount and volumes

Apple Pay/Google Pay

How does funding via these methods work?

Is there a fee associated with this method of funding?

How is this payment processed? Is there a processor in between like 3DS in EU?

Daily/monthly limits on transaction amount and volumes

ACH/WIRE/SWIFT

Do you have separate routing numbers for all 3? ACH, Wire and SWIFT?

Daily/monthly limits on transaction amount and volumes

Accounts

Is the PDF with bank details generated by greendot or do we need to create it ourselves? What are the requirements in US for this document (bank stamp, etc).? Can greendot customise those documents for us? logo, etc. same for "bank details" document proof?

Transactions

Do we get merchant name, logo, category for transactions done via debit card? For ex: If a pay at McDonalds can I show the merchant details in recent transactions on the app? Will you pass on that information? Or is that passed be card network?

**11/21/25**

Green Dot: Ray, Sarah, Lauren Quandt

Bakkt: Aayur, Ankit, Donald, Nora Cantwell, Eric Schneider

- Purpose of this call - Bakkt showing Sarah and Lauren how their KYC works in order to convince us in our confidence in KYC "reliance"

**11/18/25**

[Veronica, Ramia, Ray, Taylor, Heather H, Akhil, Satheesh, Rahul Monga]

- Bakkt going to announce a partnership with "the most famous family in the world" (puke)
- Looking for launch 120 days from signing
- Satheesh and Rahul are the dev team

- Satheesh - new from Wells Fargo
- Rahul - new, .NET dev

**11/7/25**
Mutliple accounts
Bakkt: Przemek, Marc
Green Dot: Akhil, Ray, Karl

- Changing approach - would like just to have a single account
- Can we use the "prefunded account" as an omnibus account?
- Akhil: that makes sense
	- Two options for FBO account
- Host FBO account at Green Dot - money can be moved as a ledger adjustment via API
- Host at another bank

**Compliance Call**
Bakkt: Ankit, Donald
Green Dot: Ray, Jen, Sarah, Nathan (Sr. Manager of TPRM)

- Ankit was previously at Revolut
- Bakkt is trying to build a neobank account with savings, debit,
- Donald is Chief Compliance Officer & Chief Risk Officer
- Donald - my assumption is that Green Dot has the regulatory responsibility and Bakkt has the financial responsibility (e.g. covering losses)
- What do partners experience from Green Dot's regulators?
- Typically the regulator would go to Green Dot but there will be some requirements for Bakkt to be able to quickly turn around information if needed
- Bakkt will also be available to talk directly to a partner if necssary
- Sarah - "in my experience, that does not happen"
- Initial and ongoing due diligence is very important - if we do a good job of that, the regulators should leave Bakkt alone

- CIP/KYC

- Donald: it sounds like Green Dot is open to reliance (assume that means "delegated KYC"?)
- Yes - we'll have to vet but should be OK

Internal compliance sync

[Ray, Jen Crosby, Sarah Corneau]

- Jen - SVP BSA/AML
- Sarah Corneau - head of 3rd party onboarding for BSA/AML
- Ray: this has morphed into something different than crypto.com
- Thoughts on remittance use case?

- Jen: "our regulators are going to hate this so much"
- We need to know who the other bank is

- Does Bakkt's regulatory standing (MSB & MTLs) help?

- Maybe?

- KYC process

- They use Socure, Unit 21, Chainalysis

11/5/25

Green Dot: Akhil, Tony, Karl

Bakkt: Przemek, Marc, Ankit, Aram

- Przemek - "Sheh-mek"
- Transfer verification

- ACH Pull - expectation is that you've used a tool like Plaid or Finicity to do some validation on the name matching

- Bakkt is planning to use Plaid
- We can actually enable our Partners to utilize Green Dot's commercial relationship & integration with Plaid

- ACH Push - we don't do account name matching because the user may want to send the funds to someone else

- Does Green Dot offer a feature to match routing numbers to bank names?

- No, we use a 3rd party provider for this

- Green Dot does not require validation to send money externally via ACH

- Does Green Dot support instant ACH?

- Yes - (technically not "instant" - it's "same day")

- Przemyslaw: what other limits do you have for money movement?

- Akhil: we will work with you to establish those limits at the outset of establishing the program
- These limits are disclosed to the end user at the time of account opening
- There are also fraud rules that are kept secret so as not to be exploited by fraudsters

- Account structure

- Can you open two accounts automatically?

- Savings account and intermediatary transfer account ("remittance account")
- Akhil - when you create an account - you have …

- a primary purse - has the account & routing number, debit card (only one allowed)
- Optionally a Savings vault/secondary purse (can have up to 5)

- Can we have a second account & routing number for the customer?

 11/4/25

Bakkt: Ankit, Aayur

Green Dot: Ray, Karl

- Clarifying confusion between engineering
- Original envisioning -

- Bakkt would hold funds in fiat - "for now, money stays in Green Dot"
- We're only sweeping funds when the customer is sending international remittances
- In 6 months - we might want to offer a high yield offering with another provider

- MMF = Money Market Fund

- We have MTLs in 19 states and use our bank charter in all of the others - we are covered across all states
- We don't accrue interest in savings
- Ankit - can we take all of our funds and store them in an omnibus account that earns interest?
- Followups for Bakkt

- ACH out - verification?
- Architecture - how to structure accounts for "sweep"?

10/22/25 - Bakkt Secured Card

Bakkt: Ankit - CPO, Aayur - Product owner, Rafa - product engineer/product manager, Krish - product owner for cards, Marc - PM for Green Dot integration, marcos - finance

Green Dot: Ray, Sankeerth, Karl

- Currently looking at DDA with debit card - interested in secured card as well
- Ankit: time to market is key for us - 3 months

- Planning to offer two types of cards - secured credit card; unsecured credit card

- Sankeerth - our secured card program is a "traditional" secured card

- User puts down collateral
- User gets a card with an account
- We do statements, loan management, handle payments, card support, bureau reporting, etc.

- Ankit - goals …

- Credit application - big benefit is you don't need to KYC again because the user already has an account
- Credit check isn't needed (no soft pull or anything) … but KYC is needed again
- Bakkt can re-send the information, doesn't need to create friction with the user
- What kind of card is it? Visa
- what is IX rate?

- Sankeerth will get it

- Who holds collateral?

- Green Dot

- Can we earn yield on this?

- Yes - it becomes a configuration on our side but we can do it

- How do you do rewards?

- We are launching merchant-funded cashback rewards soon
- Ankit - I'm confused…

- We do have the ability to calculate rewards based on data
- We are not integrated with partners who have points marketplaces

- We also have Blackhawk for egift rewards

- Yes we know BHN

- Ankit - we need to do KYC a certain way
- What are implementation timelines?

- Bakkt will manage the front end and integrate with the APIs
- We can do this in parallel with onboarding the DDA
- Ankit: Can this be done in 3 months?
- Card design and production wi

- How does customer service work?

- Green Dot handles fulfillment
- Bakkt wants to do all of the customer communication

- We need to figure out how that is going to work…

- Rafa: what types of credit cards do you provide?

- Right now it's Visa - but also working on MC soon

- Basic tiers

- Does Bakkt KYC apply?

- Again… we don't do credit checks
- There is no difference in KYC requirements for DDA or secured card
- We can support programs that bring their own KYC but our AML team needs to approve this process … that hasn't been done yet

- 3 months is an important target for Bakkt for certain partnerships

10/17/25

- Started out as a crypto.com clone - but morphing into more of a traditional DDA & savings account
- Interested in being a neo-bank - but not clear what their ideas and plans are
- Bakkt wants to take the interest they earned and move to the customer

9/4/25

[Shane, Taylor, Ray]

- Taylor's ID: can we charge BPS on the money movement (in & out)

- Idea is can we monetize GDV

8/29/25

[Taylor, Ray]

- Bakkt solution - similar to Crypto.com - GD facilitiates money in (ACH/RTP) to user wallet, moved into
- Next steps: how to price?

- Shane (reports to Jess) - long term pricing guru

7/9/25

Bakkt: Nicholas Baes, Michael Krupa, Blake Knaebel

Green Dot: Ray, Taylor

Nick - COO

Michael Chief of Staff

Blake - technical(?)

- Domestic on/off account for crypto to fiat

- Currently supported by Lead Bank

- Deposits
- "Paypal-like" feature for P2P

- Fiat / stablecoin

- Do we want a card associated with this product?
- Yield on deposits?
- Brokerage solution for crypto trading
- Agentic commerce

- AI chat interfaces for facilitating payment workflows
- "very bullish" on this type of workflow for payments

- Want to be able to fund with a debit card - currently more important than issuing a card, but may be in play in the future
- Named virtual accounts

- Use held assets in brokerage account for payments
- You get a payment instrument automatically with the virtual account
- Green Dot would hold the USD account, Bakkt has the crypto ledger

- Bakkt is doing all the KYC / IDV for their customers (using Socure) and have MTLs in all necessary jurisdictions

> "In the context of Bakkt, the acronym DTR likely stands for Detailed Transaction Report. This report is typically used to provide comprehensive information about transactions, including details such as transaction amounts, dates, and parties involved"

- Bakkt does B2B2C - they do p2p within their own ledger but want to also be able to move funds in/out with card rails
- Would you be ok with terms and limits and structure across all partners?

- Yes… but everyone is going to want to be a neobank in their own way

- Next steps - set up more time to share with Nick & team to go over funds flows

- Nick also interested in understanding cash deposit capabilities