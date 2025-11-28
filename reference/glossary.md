---
description: Definitions of key terms used in RewardsPro
---

# Glossary

Complete reference of terms and definitions used throughout RewardsPro.

---

## A

### Annual Evaluation
A tier calculation method where only spending from the past 12 months (rolling) counts toward tier qualification. Old spending "falls off" after 12 months, potentially causing tier downgrades if spending isn't maintained.

### Annual Spent
The customer's total order value within the last 365 days. Used for annual tier evaluation calculations.

### Audit Trail
A complete, immutable record of all changes to customer accounts, tiers, and store credit. Includes timestamps, change types, and the trigger that caused each change.

### Auto Cashback Processing
A feature toggle that, when enabled, automatically issues cashback when orders are paid without requiring manual review.

---

## B

### Balance
The current store credit available to a customer, stored as a decimal with 2 decimal places precision.

### Billing Interval
The frequency of subscription billing. Options: WEEKLY, MONTHLY, or ANNUAL.

### Billing Status
The state of a subscription billing attempt. Values: PENDING, PROCESSING, SUCCESS, FAILED, CANCELLED, or REQUIRES_ACTION.

---

## C

### Cashback
Store credit earned as a percentage of an order's eligible amount, determined by the customer's current tier rate.

### Cashback Rate
The percentage of an order's eligible amount awarded as store credit. Set per-tier (e.g., Bronze 2%, Silver 4%, Gold 6%).

### Cashback Eligible
A boolean flag on orders indicating whether the order qualifies for cashback. Some orders (like those with only excluded products) may be marked ineligible.

### COGS (Cost of Goods Sold)
The direct costs attributable to products sold. Used in business metrics to calculate profit margins and true ROI.

### Credit Sync Status
Tracks whether store credit has been synchronized with Shopify. Values: PENDING, SYNCING, SYNCED, FAILED, or NOT_APPLICABLE.

---

## D

### Default Tier
The base tier automatically assigned to new customers. Typically has a $0 minimum spend requirement and the lowest cashback rate.

### Discount Type
How discounts are calculated. Values: PERCENTAGE (e.g., 10% off) or FIXED_AMOUNT (e.g., $10 off).

### Double-Entry Ledger
The accounting system RewardsPro uses where every store credit transaction has both a debit and credit entry, maintaining balance integrity and providing a complete audit trail.

---

## E

### Eligible Amount
The portion of an order that qualifies for cashback calculation. Typically: subtotal minus discounts, excluding shipping, tax, and excluded products.

### Evaluation Period
The timeframe used to calculate customer spending for tier qualification. Values: ANNUAL (rolling 12 months) or LIFETIME (all-time).

### Exchange Rate
The conversion rate between currencies, updated daily from exchange rate providers. Used when orders are placed in currencies different from the store's base currency.

---

## F

### Financial Status
The payment state of an order. Values: PENDING, AUTHORIZED, PARTIALLY_PAID, PAID, PARTIALLY_REFUNDED, REFUNDED, or VOIDED.

### Fulfillment Status
The shipping state of an order: fulfilled, partial, unfulfilled, or null.

---

## H

### HMAC Verification
Hash-based Message Authentication Code verification used to ensure webhooks and API requests authentically come from Shopify.

---

## I

### Idempotency
A property ensuring that processing the same event multiple times produces the same result. Prevents double-crediting when webhooks are retried.

---

## L

### Ledger Entry
A single transaction record in the store credit ledger. Contains amount, type, balance, references, and timestamps.

### Ledger Entry Type
The category of a store credit transaction:
- **CASHBACK_EARNED**: Credit from order purchases
- **ORDER_PAYMENT**: Debit when using credit at checkout
- **REFUND_CREDIT**: Credit issued for refunds
- **REFUND_CLAWBACK**: Debit reversing cashback on refunded orders
- **MANUAL_ADJUSTMENT**: Admin-initiated credit changes
- **SHOPIFY_SYNC**: Credits synchronized from Shopify

### Lifetime Evaluation
A tier calculation method where all-time spending counts toward tier qualification. Customers never downgrade based on spending alone.

### Lifetime Points
The total points a customer has ever earned, regardless of redemptions. Used for tracking program engagement.

---

## M

### Manual Credit
Store credit added by the merchant through the admin interface, not earned through purchases.

### Membership Product
See "Tier Product."

### Minimum Spend (minSpend)
The spending threshold required to qualify for a tier. Stored as an integer in the store's base currency.

---

## N

### Net Amount
For orders: total price minus total refunded. For customers: total spent minus total refunded.

### Net Spent
A customer's spending after accounting for refunds. Used for accurate tier calculations.

---

## O

### Order Count
The total number of orders a customer has placed, tracked for analytics and engagement metrics.

### Order Subtotal
The sum of line item prices before shipping, tax, tips, and after line-item discounts.

---

## P

### Points Balance
Current available points a customer can redeem, distinct from store credit balance.

### Product Duration
How long tier access lasts when purchased via a tier product. Values: MONTHLY (30 days), ANNUAL (365 days), or LIFETIME (permanent).

### Progress
A customer's advancement toward the next tier, calculated as current spending divided by the next tier's threshold.

### Purchase Status
The state of a one-time tier purchase. Values: ACTIVE, EXPIRED, CANCELLED, or REFUNDED.

### Purchase Type
How a tier product can be acquired. Values: ONE_TIME, SUBSCRIPTION, or BOTH.

---

## R

### Recalculation Frequency
How often the system automatically evaluates and updates customer tiers. Values: DAILY, WEEKLY, MONTHLY, or QUARTERLY.

### Redemption
Using store credit to pay for a purchase, creating a debit ledger entry.

### Redemption Rate
The percentage of issued store credit that customers have used. A key metric for program health.

### Refund Clawback
The reversal of cashback when an order is refunded. Calculated proportionally for partial refunds.

---

## S

### Shopify Customer ID
The unique identifier assigned by Shopify to each customer account. Used to link RewardsPro data with Shopify data.

### Spending Threshold
See "Minimum Spend."

### Store Credit
A monetary balance customers can use toward future purchases. Earned through cashback or added manually by merchants.

### Subscription Status
The state of a tier subscription. Values: PENDING, ACTIVE, PAUSED, CANCELLED, EXPIRED, or FAILED.

---

## T

### Tier
A level in the loyalty program defining benefits like cashback rate. Examples: Bronze, Silver, Gold, Platinum.

### Tier Change Log
A record of when and why a customer's tier changed. Includes previous tier, new tier, trigger type, and spending data at time of change.

### Tier Change Type
The direction of a tier transition:
- **INITIAL_ASSIGNMENT**: First tier when joining
- **UPGRADE**: Moving to a higher tier
- **DOWNGRADE**: Moving to a lower tier

### Tier Product
A purchasable product that grants instant access to a specific tier for a set duration. Created as actual Shopify products.

### Tier Subscription
A recurring billing arrangement where customers pay monthly/annually to maintain a specific tier status.

### Tier Trigger Type
What caused a tier change:
- **ACCOUNT_CREATED**: New customer
- **PERIODIC_REVIEW**: Scheduled recalculation
- **SPENDING_MILESTONE**: Crossed spending threshold
- **MANUAL_ADMIN**: Admin changed tier
- **PRODUCT_PURCHASE**: Bought a tier product
- **SUBSCRIPTION_STARTED/RENEWED/UPGRADED/DOWNGRADED/CANCELLED**: Subscription events

### Total Cashback Earned
The cumulative amount of cashback a customer has earned across all orders.

### Total Spent
A customer's all-time order total, used for lifetime tier evaluation.

---

## W

### Webhook
An automated HTTP POST request sent from Shopify to RewardsPro when events occur (like order paid). Secured with HMAC verification.

### Widget
The customer-facing interface displaying tier status, store credit balance, and progress on the storefront. Delivered via Theme App Extension.

---

## Related Guides

- [Evaluation Periods](evaluation-periods.md) - Detailed evaluation period explanation
- [Cashback Logic](cashback-logic.md) - How cashback is calculated
- [Data Models](data-models.md) - Technical data structure reference
