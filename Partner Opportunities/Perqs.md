 **July 07, 2026**
[Irena, Jeff, Akhil, Kate, Sam, Chuck, Tony, John, Peter]

- 

**June 26, 2026**
[Tony, Megan, John G, Irena, Paul, Kate, Nikhil]

- Tony: Perqs is changing to a Green Dot-branded product, following the Amscot model
	- will be a new product but will follow limits, fees, pricing of Amscot program as closely as possible
	- part of FSC bin range
- Megan: we can clone the existing Amscot product in ACI
	- we also can clone the GBOS setup 

**4/3/26 - Weekly Status Report**

[Erika, Chrissie H, Kim Reede, Akhil, Charles, Kate, Irena, Sankeerth, Megan]

- Erika leading a status update on behalf of Jeff (OOO this week)

**2/12/26 - Unified Transfer APIs**

[Waqas, Michael, Kate, Tony, Michelle, Sohan, Ashutosh]

- Transfer API is doing more validation than the Adjustments API
- Eventually we will retire / phase out the Adjustments API
- Waqas looked for the minimum effort approach to consolidate the two
- Michael: "an adjustment is always a gain or loss for Green Dot"

	- "Partners cannot do Adjustments"
	- Sohan: agreed - an adjustment is already a ledger a

- Michael: the source of the transfer indicates the "type"

- We could make the identifier of the source map to the type - e.g. "programTransfer"

- Tony - thought to make this async

- We would need another endpoint to check on the transfer endpoint

- Requirements for this project:

**2/3/26**
Perqs: Nick, Julia, Kurt
Green Dot: Jeff, Kate, Ramia, John, Kate, Tony, Ray, Wayne, Rachel, Paul, Irena

- John overview of Teller Incentives program today:

	- Green Dot is paying incentives today for certain qualifying card sales / activities
	- Can we send them a daily file with information of the Card Sales mapped to teller?
	- Tony says yes… we will send all data (not filtered out by business logic)
	- We can also send a file of loads / unloads for the new accounts?

**2/2/26 - Teller Incentives API**
[Tony W, Akhil]

- 3 options…
	- FSC Reload API
	- BaaS Adjustments API
	- GFT Transfers API

- Long term - Transfers API is the right way
- Short term … Adjustments API probably makes the most sense because it provides the accounting mechanisms
- Akhil - for my first two years I couldn't remember the subtle difference between Adjustments or Transfers
	- Adjustments and Transfers are roughly the same thing
	- The difference between FSC and BaaS is more significant

- AG: reload is not as flexible as Adjustment
- For Reload - the Partner owes us money - they collect cash, we process it and send it to the accounts
- Adjustments/Transfers - allow different transaction codes for accounting
- Adjustments is already part of the Transfers API (POST transfers/adjustments)
	- Tony wants to explore if it is possible to do this consolidation now
	- Vision is to consolidate "Adjustments" into the Transfer API - treat it as a special type of Transfer ("Program Transfer")

- Two implications for Perqs:
	- Modify Perqs' system access so they have access to the BaaS APIs with their existing credentials
	- Set up the

**1/27/26 - Partner Call**
Perqs: Julia, Kurt, Michael
Green Dot: Sam, Tony, Jeff, John, Kate, Rachel, Ray, Taylor, Dinesh

- John following up on the Domain name
- Many Perqs locations do not have barcode scanners so won't support cardless cash txns
- Taylor: can we get time with the CCF team to do a review of the technical process?

- Goal is to get teams on site in Ohio in February

**1/23/26 - Aligning on Teller Incentive solution**
[Kate, Taylor, Irena, Chuck, Sanjeev, John G, Michael, Akhil, Tony]

- Akhil - let's talk about what the problem is before we jump into solutions
- John G: here's the problem statement

- On the legacy FSC side of the house, Green Dot supports logic to payout on Teller Incentives
- For the Perqs program (new on GBOS), Perqs wants to support a similar program
- We don't support that and it's not on our roadmap
- GD wants to stay arms length on these types of programs going forward
- We're fine with the partner managing it, we just don't want to manage it
- Perqs wants to know… how do we do that?
- We [presented a solution to Perqs](https://greendot365-my.sharepoint.com/personal/kcyr_greendotcorp_com/_layouts/15/Doc.aspx?sourcedoc=%7BA0254A7E-A6B1-4CC3-8146-5B0F2002EDAE%7D&file=Perqs%20Teller%20Rewards%20Solution%20Brief.docx&action=default&mobileredirect=true&DefaultItemOpen=1) using the Reload API

- John G: "is the whole file thing off the table?"
- Akhil: there is some amount of effort that Perqs has to do … they seem to be willing to do the hard part but not the easy part
- Akhil: Major major concerns from a risk perspective - we don't want to own this for compliance and regulatory reasons

- John: we were strong from the beginning that we don't want to do this… but they came back to us requesting if we could support a file-based solution

- Next steps - John to go back to Perqs and validate why our preferred solution wouldn't work for them, test assumptions

1/20/26 - Internal Product / Eng Solutioning Session

[Irena, Sam, Chuck Rickard, Taylor, Kate, Wayne Lin, Dinesh, John G, Ramia, Jeff]

- CCF is an existing FSC partner supporting Green Dot cards
- How to support existing Green Dot customers at CCF Locations?

- They'll be supporting two different programs (Green Dot & Perqs) at the same location
- Merchantid maps to a product - so there will be different merchantids that need to be routed appropriately from the POS (this is CCF's integration)

- Green Dot customers are on "legacy" platform (not BaaS - this is happening in Q2)

- You can reload a legacy card via GDN
- But, Unload and Replace functions aren't supported

- Approach - until we migrate Green Dot to GBOS, we will instruct CCF to keep Replace card and Unload functions;

- After migration,

- For Incentives…

- CFF/Perqs wants a file-based payout for teller incentives

- Paid by IQ Ventures

- Lendly approves/underwrites/services loans

- Paid by IQ ventures via Lendly

- John: they aren't PCI compliant and don't want to worry about the external accounts
- Taylor: it's kind of like a user interface in front of the Adjustments API
- Need to use AssociateRetailChainUserWithCard
- Tony - this makes sense - probably uses the Transfer API (future proofing to be used across multiple platforms)

1/20/26 - Weekly Project Status

GD: John G, Kate, Jen S, Sam, Amit, Jeff G, Akhil, Rachel Landwehr, Taylor, Ramia

Perqs: Kurt, Julia, Nick

- Physical cards - Rachel L
- At Go Live - we will issue only Perqs cards going forward - we will support legacy customers but issue only new cards as Perqs

- Need to make sure technology solution at POS is seamless to reduce training needs for tellers

- Perqs Team:

- Kurt - VP of Perqs - has worked on this from the start
- Julia - very new to IQV - Director of CRM
- Nick - CRO of Perqs/IQV

- Next priorities…

- Working out the Teller Incentives solution
- Technical integration with CCFI - Kurt & Nick need to be involved - we haven't talked with them in a few months

1/15/26

[Tony]

Tony's questions…

- i assume perqs teller will need to get a perqs card for incentive reload correct?

I think we need to check with Taylor on this but I think it is

- has it been decided to use reload or adj api, assuming tellers all need to get perqs card?

It is probably the Reload API because it is the FSC APIs. Adjustments API probably doesn't work with this type of account and there are concerns with

On BaaS - we have Transfers and Adjustments; on MM we have Disbursements & ____. We have run into ocmpliance issues with Adjustments. Long term we need to tighten up the APIs

1. reload api can do push to debit on non-GD issued card today or that requires enhancement?
2. the incentive tracking will only happen daily right?

12/3/25

[Ericka, Jen, Jamison, John, Taylor, Karl, Ray]

- Perqs wants to deploy in February, Jamison told them April
- Want to move as fast as possible on CCFI, then do Lendly next … and Liberty Tax has to be live by May
- The FSC partner needs to pass us the Teller ID when they call us (userId)

- Do we support this on GBOS today? … it's in the card sale API call
