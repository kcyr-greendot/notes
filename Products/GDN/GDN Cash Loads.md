# What are Cash Loads? 

Green Dot supports a variety of capabilities that allow customers to load cash into a prepaid or debit account or send cash to a 3rd party recipient (e.g. bill payments, peer transfers). The two main categories of Cash Loads are designated by how the customer *initiates* the reload: with a physical card **swipe** or with a digital **barcode** scan. 

This document gives an overview of the Green Dot Network (GDN) Cash Loads capabilities, the use cases they support, and key considerations when evaluating partner opportunities. 

## Swipe Reloads
### What are Swipe Reloads?

Swipe Reloads are transactions in which a cardholder swipes a card and remits cash to load funds into their account at a participating GDN retail location. 

### Key Actors in Swipe Reload Transactions

**Customer** - a person who wants to load cash to their prepaid or debit card account.

**Retailer** - a company who has a technical integration between their POS systems and the Green Dot Network that allows customers to load cash to their accounts.

**Card Partner** - the issuer and/or program brand of the card that is being loaded.

**Green Dot** - the provider of the platform that connects the actors to the Green Dot Network.

**Processor** - the actor authorizing the reload request. This could be the card partner, the card network (Visa or Mastercard) or an issuing partner like Marqeta or Stripe.

### How it works

1. When the card is swiped, an authorization is first routed to Green Dot via the retailer's GDN integration.

2. Green Dot verifies that the transaction is within limits set for the retailer program and communicates any fees associated with the transaction.

3. Green Dot forwards the authorization to the reload processor, who will then make a decision whether to accept or decline the request to reload.

4. The retailer completes the transaction, accepting the cash and any associated fees from the customer. The retailer provides the customer with a receipt to confirm the reload.

5. Green Dot sends the reload processor a confirmation of the reload amount.

6. The reload processor credits the customer's account with the reload.

7. The Retailer remits loaded funds, less retailer fees, to Green Dot in a daily batch settlement process.

8. Green Dot remits funds less platform fees to the reload processor in a daily batch settlement process.

### Types of Swipe Reload Integrations
#### [Direct Partner Integration](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/_layouts/15/Doc.aspx?sourcedoc=%7B81F5F4BE-B4D4-4C79-99F1-F83E330949C3%7D&file=GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx&nav=eyJzSWQiOjIxNDUsImNJZCI6MzcwMzczMzc1OX0&action=edit&mobileredirect=true) (Card Partner as Reload Processor)

In this model, the card partner is directly integrated into GDN via the [Retail Consumption API](https://developer.greendot.com/embedded-finance/docs/overview-3). The purpose of this API is to give the card partner the ability to authorize swipe reload transactions made on its BINs at GDN retail locations.

By integrating directly to Green Dot, the card partner benefits by bypassing the Visa/Mastercard rails and the associated costs. The card partner can either pass those cost savings to the end user or earn revenue from fees charged to the customer for the transaction.

#### [Issuer Integration]([GDN Use Case Flows - Simple Version.pptx](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/Shared%20Documents/GDN%20GTM%20Planning/5.%20Product%20Marketing%20BD%20Sell%20Sheets,%20Case%20Studies,%20Simplified%20Flows/GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx?d=w81f5f4beb4d44c7999f1f83e330949c3&csf=1&web=1&e=RhrrC8&nav=eyJzSWQiOjIxNzQsImNJZCI6MzQ2MjMwNzc0Nn0)) (Card Issuers as Reload Processor)

In another model, a card issuer (aka issuer processor) integrates to GDN's [Retail Consumption API](https://developer.greendot.com/embedded-finance/docs/overview-3).

With this type of integration, card issuers are able to scale the cash loads offering to all of the card partners on their platform. Card partners can offer the cash loads feature to their customers. Fee revenue is captured by the card issuer.

#### [Card Network Integration](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/Shared%20Documents/GDN%20GTM%20Planning/5.%20Product%20Marketing%20\(BD%20Sell%20Sheets,%20Case%20Studies,%20Simplified%20Flows\)/GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx?d=w81f5f4beb4d44c7999f1f83e330949c3&csf=1&web=1&e=RsS1nM&nav=eyJzSWQiOjIxODQsImNJZCI6MjM2NjU3MDB9) (Card Network as Reload Processor)

The card networks also support Swipe Reloads via GDN's integration with Mastercard Send and Visa Direct. In this model, GDN integrates with the card networks to facilitate an Account Funding Transaction (AFT) to the customer's debit account upon completion of the in-store cash load.

The card network charges a AFT fee to Green Dot for these transactions.

#### [PayPal/Venmo Integration](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/_layouts/15/Doc.aspx?sourcedoc=%7B81F5F4BE-B4D4-4C79-99F1-F83E330949C3%7D&file=GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx&action=edit&mobileredirect=true) (PayPal as Reload Processor)

Green Dot maintains a dedicated processor connection with PayPal's Deposit API for PayPal and Venmo Debit cards. This conceptually similar to the Issuer Integration model except instead of expecting the partner to integrate to Green Dot, Green Dot integrates directly to PayPal instead.

## Barcode Cash Loads
### What are Barcode Cash Loads? 

Barcode Loads (also known as "eCash") are transactions in which a cardholder presents a barcode and remits cash to load funds into their account or make a payment at a participating GDN retail location. 

### Key Actors in Barcode Load Transactions

**Customer** - a person who wants to load cash to their account or make a payment to a specific payee. 

**Retailer** - a company who has a technical integration between their POS systems and the Green Dot Network that allows customers to load cash to their accounts.

**Load Partner** - the issuer and/or program brand of the customer account that is being loaded. In payment scenarios, the load partner may be a payments facilitator coordinating the transfer of funds from the cash-loading customer to a payee. The partner owns the responsibility of displaying the barcode to the Customer.

**Green Dot** - the provider of the platform that connects the actors to the Green Dot Network.

**Processor** - the actor authorizing the load request. This is either the load partner or the partner's processor (e.g. Galileo, Stripe, Treasury Prime). 

### How it works

1. The customer initiates barcode generation through the load partner's user interface. 

2. The customer presents a barcode at the point of sale and an authorization request is routed to Green Dot via the retailer's GDN integration.

3. Green Dot validates the barcode, verifies that the transaction is within limits set for the retailer program and communicates any fees associated with the transaction.

4. Green Dot forwards the authorization to the processor, who will then make a decision whether to accept or decline the request to load request.

5. The retailer completes the transaction, accepting the cash and any associated fees from the customer. The retailer provides the customer with a receipt to confirm the load.

6. Green Dot sends the processor a confirmation of the load amount.

7. The load processor credits the customer's account with the load.

8. The Retailer remits loaded funds, less retailer fees, to Green Dot in a daily batch settlement process.

9. Green Dot remits funds less platform fees to the processor in a daily batch settlement process.

### Types of Barcode Load Integrations
#### [Direct Partner Integration](https://greendot365.sharepoint.com/:p:/r/sites/GDNPartners/_layouts/15/Doc.aspx?sourcedoc=%7B81F5F4BE-B4D4-4C79-99F1-F83E330949C3%7D&file=GDN%20Use%20Case%20Flows%20-%20Simple%20Version.pptx&nav=eyJzSWQiOjIxNDUsImNJZCI6MzcwMzczMzc1OX0&action=edit&mobileredirect=true) (Load Partner as Processor)

In this model, the load partner is directly integrated into GDN via the [Retail Consumption API](https://developer.greendot.com/embedded-finance/docs/overview-3). The purpose of this API is to give the card partner the ability to authorize cash load transactions made on its BINs at GDN retail locations.

By integrating directly to Green Dot, the load partner plays a direct role in both sides of the transaction, i.e. barcode presentation in their user experience and real-time transaction authorization at the time of the cash load. 

#### Processor Integration (Load Partner with Existing Processor integration)

In this model, a processor integrates with the [Retail Consumption API](https://developer.greendot.com/embedded-finance/docs/overview-3) to make the GDN cash load service available for any of its partners.  

With this type of integration, processors are able to scale the cash loads offering to any of the partners on their platform. Load Partners can offer the benefit of cash loads without the need to build their own processing integration to Green Dot. Fee revenue is captured by the processor. 

#### Cash Payments (Load Partner as Processor and Payment Facilitator)

In payments use cases, the load partner receives cash loads and credits the funds received to another party such as a bill payee. The load partner and processor roles are the same as the standard cash loads use case, but the load partner has an additional role to play in ensuring that the funds are properly credited and settled to the payment recipient. 

One significant implication of the payments facilitator role is that the partner  needs to handle the settlement of funds to the recipient (which may require money transmitter licenses, MTLs). Green Dot may be able to facilitate settlement to individual payees but this should be determined on a case-by-case basis due to the potential complexity. 