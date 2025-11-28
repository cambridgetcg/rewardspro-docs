# Access Store Credits

Shopify **Store Credit** is an internal balance that a merchant issues to a customer, stored directly in Shopify’s **Customer Account**. It functions like a wallet inside Shopify and can be applied at checkout as a payment method.

## VIP status

<div data-with-frame="true"><figure><img src="../.gitbook/assets/VIP status.png" alt=""><figcaption></figcaption></figure></div>

VIP status is displayed as a widget in the customer facing storefront, with display of tier, cashback percentage, store credit balance, and tier progress.

## Merchants's customer portal

<div data-with-frame="true"><figure><img src="../.gitbook/assets/StoreCredit_Customers.png" alt=""><figcaption></figcaption></figure></div>

### Customer-level balance

Store credit is stored on the _Customer_ resource, not at the order level. Each customer has a StoreCreditAccount with a running balance.

Store credit balance can be accessed through shopify's customer portal.

### Ledger based

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Store Credit Ledger.png" alt=""><figcaption></figcaption></figure></div>

All changes are made through **store credit adjustments** (credit or debit entries). These form a ledger:

* **Credit** = add value (refunds, goodwill, loyalty rewards).
* **Debit** = subtract value (customer redeems store credit at checkout).

## Customer Checkout

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Customer_Checkout_1.png" alt=""><figcaption></figcaption></figure></div>

Customer can apply their store credit balance during checkout by selecting the store credit option under Payment module

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Customer_Checkout_2.png" alt=""><figcaption></figcaption></figure></div>

The store credit balance will be deducted from the total purchasing price automatically
