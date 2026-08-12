**August 11, 2026** - Technical Integration Kickoff Call
Green Dot: Mano, Sohan, Taylor, Karl 
Paypal: Alison, Ryan, Benjamin, Jas, Carlton

- Jas: what is the business problem you're trying to solve? 
	- Taylor replies - Rapid!, disbursements, me-to-me transfers on BaaS
- extended conversation about funds flows
- Jas - we don't support payroll payouts today due to liability 
	- contractor and commission payouts are fine, W2 are not 
	- Mano - this is potentially a problem for Rapid!
		- we look at it as - the user has already earned these funds, we're unlocking PayPal as an option to get access to those funds
		- the wages are already there in the employees' accounts, this is a mechanism for transferring them externally
		- Jas- doesn't sound like it will be a problem, will check with compliance team
	- 

**July 30, 2026**
[Erik]

- let's not try to jam this into the existing draft amendment - it's at the 1 yard line
- we can get the boilerplate agreement from Shilpa 
- PayPal as a vendor in LogicGate (not as a Partner)
	- we're paying PayPal $0.25/txn for this
	- eixsting vendor relationship was set up previously for marketing program funding 

**July 07, 2026**
[Mano, Bob, Irena, Taylor]

- Preliminary PRD review 
- [x] Review PRD and provide feedback by 7/13
	- need to have different fee structures stored in DB? Taylor thinks perhaps yes but we'll see
	- 

**June 26, 2026**
[Mano, Bob, Michael, Taylor, Irena, Michelle, Sohan]

- Mano: product & technology met yesterday 
	- Crystal led the meeting
	- Sankeerth, Bob and Sohan were there
- Rapid will lead delivery & handle their front end work
- Money Movement team (Tony) has some additional resources that will be assigned to this
	- they will start working on this in August
- Mano will start working on PRD and share with this group for feedback
	- Taylor - we have some expectations we should share related to this
	- this feature will be build in Azure - new APIs
	- Rapid is already calling Azure for RTP
- additional scope considerations - not for this phase but could be later...
	- hosting UX elements for getting account information
	- Azure APIM endpoints for disbursements - documentation references legacy
	- transfer funds inbound from PayPal (pull)
- Michael - there's a risk here that Rapid is an internal team using this API but we're not testing it like a "real" external Partner
	- don't expose internal assumptions that a partner wouldn't be able derive on their own

**June 11, 2026**
[Bob, Michael, Michael, Michelle, David, Mano, Irena, Tony]

- Bob discussed this with Melissa 
	- who should own this?
	- ideally - money movement team owns (short term and long term)
	- recommendation was to do the practical thing ... Rapid should get it done and connect with Money Movement team for coordination
	- need to align with Tony & Ravi
- Michael - "I don't have a horse in the race on who does the work"
- Tony joined late - he agrees with the go forward plan... 