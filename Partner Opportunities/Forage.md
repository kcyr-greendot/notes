**July 10, 2026**
Green Dot: Ray, Taylor
Forage: Mike, Jack, Ofek

- Jack went to Bates College 
- Mike - "we have two distinct and complementary paths"
- largest most scaled partnerships are with DoorDash and Uber Eats 
	- DoorDash consumer can connect their EBT balance and see it and use it for spend directly from the app
- partners provide a user id to Forage
- Forage does "anti-fraud card fingerprinting" - matching userid-card combinations 
- Forage app is a "storefront for the retailer"
	- USDA only allows the "retailer" (FNS ID) to do the balance check
	- so - as long as we partner with a retailer (i.e. Walmart, Meijer, 7-Eleven, etc.) to pull the balance we can do it (e.g. "EBT balance provided through partnership with Meijer")
- no txn history available via APIs, only balance 
	- Forage app shows txn history 
- balance check feature drives meaningful results: 
	- higher average order value (+9%)
	- Jack: "Forage observes up to 9% higher AOV among our retailer partners who offer balance check in the path to purchase."
	- higher conversion 
	- higher order frequency 
- people use EBT benefits in first half of the month, use their card in the second half
- user needs to enter their 4 digit PIN every time they want to view the balance 

**July 09, 2026**
Green Dot: Ray, Adam, Taylor
Forage: Mike, Jack, Ofek

- Ofek - co-founder & CEO 
	- lots of overlap for us with Green Dot
	- serve 40M low-income Americans 
	- serve delivery, grocer, retailer customers 
- Jack Stewart - head of product
- Mike - head of BD / partnerships
- Taylor: lots of interest from our partners looking to support closed loop cards - looking to learn more about SNAP / EBT
- Ofek - a lot of capabilities we're interested in, you have and we don't 
	- merchant acquirer for EZ payments - iso 8583 payments 
	- balance inquiry 
	- Green Dot could use forage's API 
	- average family of four - monthly EBT balance over $700
	- recently launcehd a consumer app - hundreds of thousands of users - #1 highest rated EBT app in U.S. 
	- expanding financial access
	- cash digitization 
	- underbanked/underserved people often don't have access to cards 
	- Earned Wage Access
	- today just EBT - but building programs for WIC, HSA, FSA 
- Jack - today we want to dig into the Retailer Wallet App opportunity 
	- Meijer - can we embed EBT into our wallet? 
	- down the road - they're also interested in HSA 
- EBT - Electronic Benefit Transfer
	- SNAP - $100B / TNF / WIC
	- we abstract away a lot of the complexity 
	- a single EBT card might have a lot of purses 
	- single message system / refunds 
- list of "item restrictions" for SNAP eligibility is "in flux"
	- Forage does *not* enforce eligibility
	- Retailer does - they get USDA certified and maintain the catalog
	- Forage calculates amount of transaction that is SNAP eligible and calculates sales tax (SNAP purchases are exempt from sales tax)
- card swipe for most states 
	- card skimming is the biggest fraud vector nationwide - moving to tap / chip dip will cut down on this significantly
- apple / google wallet hasn't really been rolled out yet
- online checkout 
- there's a pilot program in 5 states to pay for SNAP with mobile devices (including IL, MA, OK)
- [https://docs.joinforage.app/reference/create-custom-balance-check-session](https://docs.joinforage.app/reference/create-custom-balance-check-session "https://docs.joinforage.app/reference/create-custom-balance-check-session")
- [https://www.fna.usda.gov/snap/mobile-payment-pilot](https://www.fna.usda.gov/snap/mobile-payment-pilot "https://www.fna.usda.gov/snap/mobile-payment-pilot")
- Ofek: what type of card? 
	- Taylor: government benefits direct deposits land 4-5 days earlier with Green Dot than with large banks
	- Adam: we waive monthly fees for direct deposit 
	- ODP is free if you pay it back in 24 hours
	- Propel is "the other EBT company" - they launched a card product and failed
	- how do we structure so we can make this work economically? 
		- Ray will work on this once he has volume estimates from Forage
		- 10M unique transactions in 2025
		- Consumer app is early days but already hundreds of thousands of users
		- launching a waitlist for card program in the app as early as next week 
	- "it would be hard to imagine a world in which we think we can do a better job of being a program manager than you"
- Adam - what level of loyalty does a consumer have to the Forage brand? 
	- branding from the start - we took our inspiration from Plaid - "powered by Forage" logo on EBT interactions 
	- want to be a brand of trust with grocers and EBT recipients 
- Jack: "this is a space where people are afraid of and often failed by financial institutions"
	- check balance is a small but valuable feature - it's actually not easy to do today (often requires calling a 1-800 # )
