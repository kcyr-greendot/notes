**June 30, 2026**
7-Eleven: Jithesh, Siva, Veena
Green Dot: Shane, Veronica, Everett, Sean, Tammina

- no Srikala today - so we don't the right people for void / timeout conversation 
- we got what we needed out of networking conversation last week 
- Veena: 
	- void is a customer-initiated transaction that we support today - including for one of the Green Dot products
	- we must have a timeout reversal 
	- we need all of your products to support void - and if any don't, let us know which don't
	- timeout reversal - we send a request, we don't hear back from Green Dot, we initiate a reversal 
		- this is a requirement so we don't have unreconciled transactions
- Sean: 
	- we do have a story in for this
	- 

**June 25, 2026**
7-Eleven: Steve, Jithesh, Willie
Green Dot: Shane, Taylor, Danon, Wayne

- Steve has been at 7-Eleven for only 4 months
- 7-E architecture meeting yesterday
	- concerns raised about "inefficient routing" (store -> data center -> Green Dot -> data center -> store)
	- the team prefers a "site-to-site" connection
- Wayne - APIM gateway is internet-facing only - no alternative that is "internal facing"
- ![[Screenshot 2026-06-25 at 12.12.26 PM.png|297]]![[Screenshot 2026-06-25 at 12.11.45 PM.png|415]]

- 

**June 23, 2026** - 
7-Eleven: Jithesh, Shiva, Chad
Green Dot: Shane, Danon, Everett, Christina, Tammina

- Void / Return scenario
	- Danon: we're going to gather more data to determine if we actually support the Return scenario today
	- Jithesh: do we have this currently with InComm today? 
		- Danon: i think this might be supported in teh InComm API today because they also sell gift cards but wouldn't be supported for prepaid cards
		- Christina: confirmed, we don't support that Return scenario for Prepaid
		- Everett: we tell Retail Partners to direct the customers to Green Dot in this scenario
	- Shiva - Void within the funding timeout window 
		- Reversal - got a timeout in hitting the Green Dot API - 7-E wants to reverse & retry the transaction
- Shiva - there ARE load voids happening at 7-Eleven ... but we need to verify if they are specifically InComm products. 
	- some of them look like immediate "change of mind" txns at the point of sale

Voids - internal follow-up
[Taylor, Danon, Shane]

- Taylor: feels like this is a practical occurence, not a conceptual anticipation 
- Danon: we have Returns through Incomm but not sure it works the way they're thinking
- Taylor confirmed that the current Incomm spec has a "return" call - but we think that's actually more like a "void"
	- key thing is - you can't Return a card that has been loaded and activated 
- i think it's a matter of different terminology: 
	- Reversal - cancel the current or just completed transaction
	- Void - cancel the order, reverse the txn and get rid of the card - it should not be re-usable
	- Return - bring a card back to the store, get your funds back and card is voided
- we don't / won't support a Return
	- Taylor's suggestion is to get information from Everett about if we actually see this scenario in real life


**June 16, 2026**
[Shane, Kevin, Jason H, Wayne, Everett, Mani, Daniel Suarez]

- 

**June 12, 2026** - Voids
Green Dot: Shane, Srikala, Tammina, Danon
7-Eleven: Jithesh, Veena, Shiva 

- Veena - need to understand the funding delay
- Srikala - for Retail API - we only have void
	- void window varies based on product type (swipe reload, barcode reload, retail product card sale)
	- during void window - the transaction is completed
	- after void window - no return option 
- 96 host response code from Incomm - we decline, but for in some cases the card gets loaded 
	- we see this crop up in the invoicing
	- timeout from Incomm to Green Dot

**June 11, 2026**
Green Dot: Shane, Danon, Michelle, Wayne, Taylor
7-Eleven: Jason, Jithesh, Srikanth, 

- Wayne presenting architecture diagram and network configurations 
- 

**June 09, 2026**
Green Dot: Danon, Shane, Taylor, Srikala
7-Eleven: Chad, Veena, Shiva, Jithesh

**June 8, 2026**
[Danon, Taylor]

- Need to break out the plan by phases - be more explicit about what we're going live with or just building to test for each Phase
- we're not going to be selling our own products yet - still going through Incomm

