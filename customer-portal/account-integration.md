---
description: What customers see in their Shopify customer account
---

# Account Integration

RewardsPro doesn't add a block or extension to customer account pages. Cashback
is issued as Shopify store credit, and Shopify shows store credit natively in
customer accounts.

## What Customers See Where

| Where | What customers see |
|-------|--------------------|
| **Shopify customer account** | Their store credit balance, shown by Shopify |
| **Checkout** | Their store credit, which they can apply when signed in through customer accounts or paying with Shop Pay |
| **RewardsPro widget on your storefront** | Their tier, cashback rate, store credit balance and progress to the next tier, once they're signed in |

## Customer Accounts, Not Legacy Accounts

Store credit isn't available with legacy customer accounts. Customers can spend
their store credit only when signed in through Shopify customer accounts, or
when paying with Shop Pay.

To check which your store uses:

1. Go to **Shopify Admin** → **Settings** → **Customer accounts**
2. Make sure customers sign in with customer accounts, not legacy customer accounts
3. Make sure the **Store credit** setting is turned on there, so customers see their balance in their account
4. Save changes

See Shopify's [store credit help page](https://help.shopify.com/en/manual/customers/store-credit) for the full rules.

## Spending Store Credit

- Shopify applies the customer's full store credit balance. Customers can't choose a partial amount.
- Store credit can't pay for draft orders, edited orders or recurring subscription payments.
- At checkout, customers see only the balance in that checkout's currency.
- If your store was created on or after 12 May 2025, Shopify charges you its third-party transaction fee on the part of an order paid with store credit, even with Shopify Payments.

[Installation](../getting-started/installation.md) explains these rules.

## Showing Tier and Progress

Tier status and progress appear in the RewardsPro widget, not in the customer
account. Turn on the **RewardsPro Widget** app embed in your theme editor. See
[Widget Installation](widget-installation.md).

## Testing

| Scenario | Expected Result |
|----------|-----------------|
| Signed-in customer with store credit | Balance shows in their Shopify customer account and in the widget |
| Same customer at checkout | Store credit is offered, and Shopify applies the full balance |
| Guest visitor | The widget asks them to sign in |
