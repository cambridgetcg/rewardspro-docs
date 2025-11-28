---
description: Technical reference for RewardsPro data structures
---

# Data Models

Technical reference for the data structures used in RewardsPro. This guide is for developers and advanced users who want to understand how data is stored and related.

---

## Core Models

### Customer

Represents a customer in the loyalty program.

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique identifier |
| `shop` | String | Shop domain |
| `shopifyCustomerId` | String | Shopify's customer ID |
| `email` | String | Customer email |
| `firstName` | String | First name |
| `lastName` | String | Last name |
| `tags` | String | Customer tags (comma-separated) |
| `storeCredit` | Decimal | Current balance (2 decimal places) |
| `pointsBalance` | Decimal | Available points |
| `lifetimePoints` | Decimal | Total points ever earned |
| `totalSpent` | Decimal | All-time spending |
| `annualSpent` | Decimal | Last 12 months spending |
| `totalCashbackEarned` | Decimal | Cumulative cashback |
| `totalRefunded` | Decimal | Total refunds received |
| `netSpent` | Decimal | totalSpent - totalRefunded |
| `orderCount` | Integer | Number of orders |
| `lastOrderDate` | DateTime | Most recent order |
| `currentTierId` | UUID | Current tier reference |
| `hasActiveSubscription` | Boolean | Active tier subscription |
| `subscriptionTier` | String | Subscription tier name |
| `createdAt` | DateTime | Record creation |
| `updatedAt` | DateTime | Last update |

**Key Relationships:**
- Has one current Tier
- Has many StoreCreditLedger entries
- Has many TierChangeLog entries
- Has many Orders
- Has many TierSubscriptions

---

### Tier

Defines a loyalty tier with its benefits.

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique identifier |
| `shop` | String | Shop domain |
| `name` | String | Tier name (e.g., "Gold") |
| `minSpend` | Integer | Spending threshold |
| `cashbackPercent` | Integer | Cashback rate (0-100) |
| `evaluationPeriod` | Enum | ANNUAL or LIFETIME |
| `icon` | String | Emoji or icon (default: ⭐) |
| `color` | String | Hex color (default: #FFD700) |
| `threshold` | Integer | Progress tracking value |
| `monthlyPrice` | Decimal | Subscription price |
| `billingInterval` | Enum | WEEKLY, MONTHLY, ANNUAL |
| `discountPercentage` | Decimal | Subscription discount |
| `createdAt` | DateTime | Record creation |
| `updatedAt` | DateTime | Last update |

**Key Relationships:**
- Has many Customers
- Has many TierProducts

---

### Order

Represents a customer order with cashback data.

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique identifier |
| `shop` | String | Shop domain |
| `shopifyOrderId` | String | Shopify order ID |
| `shopifyOrderNumber` | String | Customer-visible number |
| `shopifyOrderName` | String | Order name (#1234) |
| `customerId` | UUID | Customer reference |
| `email` | String | Customer email |
| `currency` | String | Order currency code |
| `subtotalPrice` | Decimal | Before discounts/shipping/tax |
| `totalDiscounts` | Decimal | Discounts applied |
| `totalShipping` | Decimal | Shipping cost |
| `totalTax` | Decimal | Tax amount |
| `totalPrice` | Decimal | Final total |
| `totalRefunded` | Decimal | Refunded amount |
| `netAmount` | Decimal | totalPrice - totalRefunded |
| `financialStatus` | Enum | PAID, REFUNDED, etc. |
| `fulfillmentStatus` | String | Shipping status |
| `cashbackEligible` | Boolean | Qualifies for cashback |
| `cashbackPercent` | Integer | Rate applied |
| `cashbackAmount` | Decimal | Cashback earned |
| `cashbackProcessed` | Boolean | Has been credited |
| `tierIdAtOrder` | UUID | Customer's tier when ordered |
| `tierNameAtOrder` | String | Tier name for history |
| `shopifyCreatedAt` | DateTime | Shopify order date |
| `processedAt` | DateTime | When we processed it |

**Key Relationships:**
- Belongs to Customer
- Has many StoreCreditLedger entries

---

### StoreCreditLedger

Double-entry ledger for store credit transactions.

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique identifier |
| `customerId` | UUID | Customer reference |
| `shop` | String | Shop domain |
| `amount` | Decimal | Transaction amount (+/-) |
| `balance` | Decimal | Running balance after transaction |
| `type` | Enum | Entry type (see below) |
| `shopifyOrderId` | String | Related Shopify order |
| `shopifyTransactionId` | String | Shopify credit transaction |
| `syncStatus` | Enum | Shopify sync state |
| `syncedAt` | DateTime | When synced |
| `orderId` | UUID | Related Order |
| `description` | String | Human-readable description |
| `note` | String | Admin notes |
| `createdBy` | String | Who created entry |
| `createdAt` | DateTime | Transaction timestamp |

**Entry Types (LedgerEntryType):**

| Type | Description | Amount |
|------|-------------|--------|
| `CASHBACK_EARNED` | From order purchases | Positive |
| `ORDER_PAYMENT` | Used at checkout | Negative |
| `REFUND_CREDIT` | Credit for refunds | Positive |
| `REFUND_CLAWBACK` | Reversed cashback | Negative |
| `MANUAL_ADJUSTMENT` | Admin changes | Either |
| `SHOPIFY_SYNC` | Sync from Shopify | Either |

---

### TierChangeLog

Audit trail for tier transitions.

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique identifier |
| `customerId` | UUID | Customer reference |
| `shop` | String | Shop domain |
| `fromTierId` | UUID | Previous tier (null for first) |
| `fromTierName` | String | Previous tier name |
| `toTierId` | UUID | New tier |
| `toTierName` | String | New tier name |
| `changeType` | Enum | INITIAL_ASSIGNMENT, UPGRADE, DOWNGRADE |
| `triggerType` | Enum | What caused the change |
| `totalSpending` | Decimal | Spending at time of change |
| `periodSpending` | Decimal | Period spending at change |
| `createdAt` | DateTime | When change occurred |

**Trigger Types (TierTriggerType):**

| Type | Description |
|------|-------------|
| `ACCOUNT_CREATED` | New customer signup |
| `PERIODIC_REVIEW` | Scheduled recalculation |
| `SPENDING_MILESTONE` | Crossed threshold |
| `MANUAL_ADMIN` | Admin changed tier |
| `PRODUCT_PURCHASE` | Bought tier product |
| `SUBSCRIPTION_STARTED` | Started subscription |
| `SUBSCRIPTION_RENEWED` | Subscription renewed |
| `SUBSCRIPTION_UPGRADED` | Upgraded subscription |
| `SUBSCRIPTION_DOWNGRADED` | Downgraded subscription |
| `SUBSCRIPTION_CANCELLED` | Cancelled subscription |

---

## Subscription Models

### TierSubscription

Recurring tier membership subscription.

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique identifier |
| `shop` | String | Shop domain |
| `customerId` | UUID | Customer reference |
| `tierId` | UUID | Tier being subscribed to |
| `shopifyContractId` | String | Shopify contract ID |
| `status` | Enum | Subscription state |
| `billingInterval` | Enum | WEEKLY, MONTHLY, ANNUAL |
| `price` | Decimal | Subscription price |
| `currency` | String | Currency code |
| `nextBillingDate` | DateTime | Next charge date |
| `currentPeriodStart` | DateTime | Period start |
| `currentPeriodEnd` | DateTime | Period end |
| `cancelledAt` | DateTime | Cancellation date |
| `pausedAt` | DateTime | Pause date |
| `failedPaymentCount` | Integer | Consecutive failures |

**Subscription Status:**

| Status | Description |
|--------|-------------|
| `PENDING` | Not yet activated |
| `ACTIVE` | Currently active |
| `PAUSED` | Temporarily suspended |
| `CANCELLED` | Permanently cancelled |
| `EXPIRED` | Past end date |
| `FAILED` | Payment failures exceeded |

---

### TierProduct

Purchasable product granting tier access.

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique identifier |
| `shop` | String | Shop domain |
| `tierId` | UUID | Tier granted |
| `shopifyProductId` | String | Shopify product ID |
| `shopifyVariantId` | String | Shopify variant ID |
| `name` | String | Product name |
| `price` | Decimal | Purchase price |
| `currency` | String | Currency code |
| `duration` | Enum | MONTHLY, ANNUAL, LIFETIME |
| `purchaseType` | Enum | ONE_TIME, SUBSCRIPTION, BOTH |
| `isActive` | Boolean | Available for purchase |

---

### TierPurchase

One-time tier purchase record.

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique identifier |
| `shop` | String | Shop domain |
| `customerId` | UUID | Customer reference |
| `tierProductId` | UUID | Product purchased |
| `tierId` | UUID | Tier granted |
| `shopifyOrderId` | String | Purchase order |
| `status` | Enum | ACTIVE, EXPIRED, CANCELLED, REFUNDED |
| `purchasePrice` | Decimal | Amount paid |
| `currency` | String | Currency code |
| `startDate` | DateTime | Access start |
| `expiresAt` | DateTime | Access end |

---

## Shop Settings

### ShopSettings

Store-level configuration.

| Category | Fields |
|----------|--------|
| **Store Info** | storeName, storeUrl, shop |
| **Currency** | storeCurrency, currencyDisplayType |
| **Localization** | timezone |
| **Email** | emailEnabled, emailProvider, emailFromName, emailFromAddress, emailLogo, emailPrimaryColor |
| **Tier Automation** | tierRecalculationEnabled, tierRecalculationFrequency, tierRecalculationLastRun |
| **Business Metrics** | averageProfitMargin, averageCogsPercent, averageShippingCost, averageOrderValue, targetRoiPercent |
| **Feature Toggles** | advancedAnalyticsEnabled, autoCashbackProcessingEnabled, emailMarketingEnabled, tierProductsEnabled |
| **Widget** | widgetIsActive, widgetSetupDismissed |
| **Sync Status** | customersInitialSynced, customersSyncInProgress |

---

## Enums Reference

### Financial Statuses

```
OrderFinancialStatus:
  PENDING
  AUTHORIZED
  PARTIALLY_PAID
  PAID
  PARTIALLY_REFUNDED
  REFUNDED
  VOIDED
```

### Evaluation Periods

```
EvaluationPeriod:
  ANNUAL    // Rolling 12 months
  LIFETIME  // All-time
```

### Recalculation Frequency

```
RecalculationFrequency:
  DAILY
  WEEKLY
  MONTHLY
  QUARTERLY
```

### Billing Intervals

```
BillingInterval:
  WEEKLY
  MONTHLY
  ANNUAL
```

### Product Duration

```
ProductDuration:
  MONTHLY   // 30 days
  ANNUAL    // 365 days
  LIFETIME  // Permanent
```

---

## Data Relationships Diagram

```
ShopSettings (1:1 per shop)
     │
     └── Tiers (1:many)
           │
           ├── Customers (many:1)
           │     │
           │     ├── Orders (1:many)
           │     │     └── StoreCreditLedger (1:many)
           │     │
           │     ├── StoreCreditLedger (1:many)
           │     ├── TierChangeLog (1:many)
           │     ├── TierSubscriptions (1:many)
           │     └── TierPurchases (1:many)
           │
           ├── TierProducts (1:many)
           │     └── TierPurchases (1:many)
           │
           └── TierSubscriptions (1:many)
```

---

## Related Guides

- [Glossary](glossary.md) - Term definitions
- [Webhooks](webhooks.md) - Event processing
- [Cashback Logic](cashback-logic.md) - Calculation formulas
- [Evaluation Periods](evaluation-periods.md) - Tier evaluation
