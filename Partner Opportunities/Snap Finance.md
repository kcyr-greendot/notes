**September 14, 2026**
Snap: Michael, Megan, Amandeep Singh, Isaiah Jones
Green Dot: Willis, Taylor

- Amandeep - lead enterprise services - all technology related to virtual cards
- Isaiah - product manager - working on virtual card programs 
	- Isaiah is the guru on virtual cards
- ability to pass virtual card back to the end user? 
	- today - they have an iframe directly from issuer
	- yes - we have a PCI widget and other UI components we can leverage to minimize your exposure to PCI scope 
- Megan's questions - test cards and attribution
	- "we aren't live in production with anyone today with that type of use case"
	- what kind of data can we get from Visa and Mastercard to help for this? 
- Megan- we are only licensed to have a lease or a loan in certain states
- Isaiah - two separate goals
	- Attribution - can we recognize the entity that's using our virtual card? 
		- a decade ago that was easier - now with payment processors obfuscating the MIDs (Square shares MIDs)
		- LTO - use anywhere within Discover's network - we allow people to shop outside of Snap's partner network
		- attribution is for sales commissions
		- using merchant name, ID, location - combine all three datapoints to create a unique ID for that merchant
		- lots of turnover / switching in 
	- Authorization
		- built their own internal engine
		- is the merchant attributed? are they vetted as a Snap partner? 
		- have the ability to deny on MCC codes
		- combination of merchant name and MID 
- cards are commercial prepaid (GPR) - but Snap doesn't reload the cards - so they're effectively single use
	- high IX rates - lots of blocking by merchants
- Discover provides Snap merchant data
	- huge opportunity going to Visa / Mastercard 
	- but do we potentially lose our data from Discover? 
	- Snap signed a data exchange agreement with Discover - 3.5M merchants and their data shared with Snap 
- Amandeep - can you take Snap's KYC or does Green Dot need to do its own? 
- 

**August 27, 2026**
Snap: Rob Barnhart, Megan Pecilunas, Michael Minor
Green Dot: Willis, Taylor

- [Taylor's slide](https://greendot365-my.sharepoint.com/:p:/r/personal/tdriggs_greendotcorp_com/_layouts/15/Doc.aspx?sourcedoc=%7B4B6347D0-1AD5-4BB3-9B74-9AEEFE3D7F3D%7D&file=Snapfinance%20slide%20082726.pptx&fromShare=true&action=edit&mobileredirect=true)
- Rob is in Salt Lake City; Megan is in Ohio; Michael is in Texas
- Michael: "we have a virtual card today, but we have a lot of limitations with it"
- Snap has been very merchant focused to date
- trying to shift to a Consumer focus ("direct to Alice") 
- POS experience has been a bit painful - handing the merchant the phone to type in a card number
- tap-to-pay would be a big win
- limitations with Discover and Galileo...
	- we have been inserted into the authorization stream 
	- we've built our own restricted access network
	- tight attribution between where the user is approved and where they spend
- "we explicitly block guns, sex and puppies" lol
- ecommerce transactions are harder to attribute 
- cards are a prepaid debit card
- two processors - Galileo and i2c
	- i2c - LTO (lease to own)
	- Galileo for the other programs (loan)
- target state is for lease and loan to be largely the same 
- snap has been doing pass-through authorization for ~10 years
- Megan - do you support Discover? 
	- kind of ... it's been a while 
	- Megan's concern is that we have a lot of attribution data from years of wokring with Discover
- we would be happy to let go of the passthrough authorization if we had a partner who could help us with that
	- what we have works but it's a big PITA for us
- loan volume in a year? 
	- Rob: over 1 million new loans each year
- next steps? 
	- talking through solutions 
	- what does cutover look like? 
	- 

**August 25, 2026**
[Willis, Taylor]

- Snap Finance currently using Galileo
- LTV for these customers is pretty good - a $1500 purchase is $20 of revenue for a single txn
- opportunities to upsell on DDA / prepaid accounts later
- the users are KYC'd for lending purposes
- MIchael Minor (CPO), Isaiah (virtual cards), Megan (originations)
- our current gap - how do we enable spend controls
- Snap is currently on Discover
