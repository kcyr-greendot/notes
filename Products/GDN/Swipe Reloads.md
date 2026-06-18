### What are Swipe Reloads?

Swipe Reloads are transactions in which a cardholder swipes a card and remits cash to load funds into their account at a participating GDN retail location.

### Key Actors in Swipe Reload Transactions

**Customer** - a person who wants to load cash to their prepaid or debit card account

**Retailer** - a company who has a technical integration between their POS systems and the Green Dot Network that allows customers to deposit cash to their accounts

**Card Partner** - the issuer and/or program brand of the card that is being loaded

**Green Dot** - the provider of the platform that connects the actors to the Green Dot Network

**Reload Processor** - the actor authorizing the reload request. This could be the card partner, the card network (Visa or Mastercard) or an issuing partner like Marqeta or Stripe.

How it works

1. When the card is swiped, an authorization is first routed to Green Dot via the retailer's GDN integration.

Green Dot verifies that the transaction is within limits set for the retailer program and communicates any fees associated with the transaction.

Green Dot forwards the authorization to the reload processor, who will then make a decision whether to accept or decline the request to reload.

The retailer completes the transaction, accepting the cash and any associated fees from the customer. The retailer provides the customer with a receipt to confirm the reload.

Green Dot sends the reload processor a confirmation of the reload amount.

The reload processor credits the customer's account with the reload.

The Retailer remits loaded funds, less retailer fees, to Green Dot in a daily batch settlement process.

Green Dot remits funds less platform fees to the reload processor in a daily batch settlement process.

[Direct Partner Integration](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/Shared%20Documents/GDN%20GTM%20Planning/5.%20Product%20Marketing%20\(BD%20Sell%20Sheets,%20Case%20Studies,%20Simplified%20Flows\)/GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx?d=w81f5f4beb4d44c7999f1f83e330949c3&csf=1&web=1&e=CHZ2fu&nav=eyJzSWQiOjIxNDUsImNJZCI6MzcwMzczMzc1OX0) (Card Partner as Reload Processor)

In this model, the card partner is directly integrated into GDN via the [Retail Consumption API](https://developer.greendot.com/embedded-finance/docs/overview-3). The purpose of this API is to give the card partner the ability to authorize swipe reload transactions made on its BINs at GDN retail locations.

By integrating directly to Green Dot, the card partner benefits by bypassing the Visa/Mastercard rails and the associated costs. The card partner can either pass those cost savings to the end user or earn revenue from fees charged to the customer for the transaction.

[Issuer Integration](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/Shared%20Documents/GDN%20GTM%20Planning/5.%20Product%20Marketing%20\(BD%20Sell%20Sheets,%20Case%20Studies,%20Simplified%20Flows\)/GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx?d=w81f5f4beb4d44c7999f1f83e330949c3&csf=1&web=1&e=EaVmuL&nav=eyJzSWQiOjIxNzQsImNJZCI6MzQ2MjMwNzc0Nn0) (Card Issuers as Reload Processor)

In another model, a card issuer (aka issuing processor) integrates to GDN's [Retail Consumption AP](https://developer.greendot.com/embedded-finance/docs/overview-3)I.

With this type of integration, card issuers are able to scale the cash loads offering to all of the card partners on their platform. Card partners can offer the cash loads feature to their customers. Fee revenue is captured by the card issuer.

[Card Network Integration](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/Shared%20Documents/GDN%20GTM%20Planning/5.%20Product%20Marketing%20\(BD%20Sell%20Sheets,%20Case%20Studies,%20Simplified%20Flows\)/GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx?d=w81f5f4beb4d44c7999f1f83e330949c3&csf=1&web=1&e=RsS1nM&nav=eyJzSWQiOjIxODQsImNJZCI6MjM2NjU3MDB9) (Card Network as Reload Processor)

The card networks also support Swipe Reloads via GDN's integration with Mastercard Send and Visa Direct. In this model, GDN integrates with the card networks to facilitate an Account Funding Transaction (AFT) to the customer's debit account upon cash deposit.

The card network charges a AFT fee to Green Dot for these transactions.

[PayPal/Venmo Integration](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/_layouts/15/Doc.aspx?sourcedoc=%7B81F5F4BE-B4D4-4C79-99F1-F83E330949C3%7D&file=GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx&action=edit&mobileredirect=true) (PayPal as Reload Processor)

Green Dot maintains a dedicated processor connection with PayPal's Deposit API for PayPal and Venmo Debit cards. This conceptually similar to the Issuer Integration model except instead of expecting the partner to integrate to Green Dot, Green Dot integrates directly to PayPal instead.