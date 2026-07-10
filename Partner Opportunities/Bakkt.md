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