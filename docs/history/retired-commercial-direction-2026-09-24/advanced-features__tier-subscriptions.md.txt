---
description: Set up recurring tier membership billing with Shopify Subscriptions
---

# Tier Subscriptions

Tier Subscriptions enable recurring billing for tier memberships using Shopify's native subscription infrastructure. Customers subscribe to a tier and are automatically billed on a regular schedule.

---

## How It Works

```
Customer subscribes to Gold tier ($9.99/month)
        ↓
Subscription contract created in Shopify
        ↓
Customer assigned to Gold tier immediately
        ↓
Monthly billing occurs automatically
        ↓
Tier access continues while subscription active
        ↓
If cancelled, tier reverts based on spending
```

---

## Subscription Components

### Selling Plans

Shopify Selling Plans define subscription options:

| Component | Description |
|-----------|-------------|
| **Selling Plan Group** | Container for related plans |
| **Selling Plan** | Individual subscription option |
| **Billing Policy** | When to charge (weekly/monthly/annual) |
| **Delivery Policy** | For physical products (not used for tiers) |

### Subscription Contracts

When a customer subscribes:

| Field | Description |
|-------|-------------|
| **shopifyContractId** | Unique contract identifier |
| **status** | ACTIVE, PAUSED, CANCELLED, EXPIRED |
| **billingInterval** | WEEKLY, MONTHLY, ANNUAL |
| **nextBillingDate** | When next charge occurs |
| **priceCents** | Amount charged per cycle |
| **discountPercentage** | Any applied discount |

---

## Setting Up Subscriptions

### Prerequisites

1. Shopify Subscriptions app installed
2. Tier product created in RewardsPro
3. "Both" or "Subscription" purchase type selected

### Step 1: Configure Subscription Pricing

In the Tier Product settings:

| Setting | Description | Example |
|---------|-------------|---------|
| **Subscription Price** | Amount per billing cycle | $9.99 |
| **Billing Interval** | How often to charge | Monthly |
| **Discount %** | Optional discount off base | 10% |

### Step 2: Create Selling Plan

RewardsPro automatically creates:

1. **Selling Plan Group** linked to your tier product
2. **Selling Plan** with your pricing configuration
3. **Billing Policy** matching your interval

### Step 3: Product Variant Update

The tier product variant is updated to:
- Include subscription selling plan
- Display subscription option at checkout
- Show correct pricing

---

## Billing Intervals

| Interval | Charge Frequency | Best For |
|----------|------------------|----------|
| **Weekly** | Every 7 days | High-engagement, low-price |
| **Monthly** | Every 30 days | Most common, predictable |
| **Annual** | Every 365 days | Committed customers, discounts |

### Pricing Recommendations

| Tier Level | Monthly | Annual (15% off) |
|------------|---------|------------------|
| Silver | $4.99 | $50.99 |
| Gold | $9.99 | $101.99 |
| Platinum | $19.99 | $203.99 |

---

## Subscription Lifecycle

### Status Flow

```
PENDING → ACTIVE → (PAUSED) → CANCELLED/EXPIRED
```

| Status | Description | Tier Access |
|--------|-------------|-------------|
| `PENDING` | Awaiting first payment | No |
| `ACTIVE` | Subscription running | Yes |
| `PAUSED` | Temporarily stopped | Configurable |
| `CANCELLED` | Customer cancelled | No |
| `EXPIRED` | Payment failed/ended | No |

### Lifecycle Events

| Event | Webhook | Action |
|-------|---------|--------|
| **Created** | `subscription_contracts/create` | Assign tier |
| **Activated** | `subscription_billing_attempts/success` | Confirm tier |
| **Renewed** | `subscription_billing_attempts/success` | Extend access |
| **Paused** | `subscription_contracts/update` | Optional: Keep tier |
| **Resumed** | `subscription_contracts/update` | Restore tier |
| **Cancelled** | `subscription_contracts/update` | Recalculate tier |
| **Failed** | `subscription_billing_attempts/failure` | Grace period |

---

## Managing Subscriptions

### View Customer Subscriptions

In Customer Details > Subscriptions tab:

| Column | Description |
|--------|-------------|
| **Tier** | Subscribed tier name |
| **Status** | Active, Paused, Cancelled |
| **Price** | Recurring amount |
| **Next Billing** | Next charge date |
| **Started** | Subscription start date |

### Pause a Subscription

Customers can pause from their account, or admins can:

1. Open Customer Details
2. Go to Subscriptions tab
3. Click **Pause** on the subscription
4. Select pause duration (optional)

**During Pause:**
- No billing occurs
- Tier access is configurable (keep or remove)
- Can resume anytime

### Resume a Subscription

1. Open Customer Details
2. Go to Subscriptions tab
3. Click **Resume** on the paused subscription
4. Next billing date is set

### Cancel a Subscription

1. Open Customer Details
2. Go to Subscriptions tab
3. Click **Cancel** on the subscription
4. Confirm cancellation

**After Cancellation:**
- No future billing
- Tier access continues until period end
- Customer reverts to spending-based tier

---

## Payment Handling

### Successful Payments

When billing succeeds:

1. Payment captured in Shopify
2. Subscription period extended
3. Tier access continues
4. Event logged in subscription history

### Failed Payments

When billing fails:

1. **Grace Period** starts (default: 3 days)
2. Customer notified via email
3. Retry attempts scheduled
4. After grace: Subscription cancelled

### Dunning Management

RewardsPro handles payment retries:

| Retry | Timing | Action |
|-------|--------|--------|
| 1st | Immediate | Automatic retry |
| 2nd | 24 hours | Retry + email |
| 3rd | 48 hours | Retry + email |
| Final | 72 hours | Cancel if fails |

---

## Subscription Data Model

### TierSubscription Fields

| Field | Type | Description |
|-------|------|-------------|
| `id` | UUID | Unique subscription ID |
| `shopifyContractId` | String | Shopify contract reference |
| `customerId` | UUID | Customer relationship |
| `tierId` | UUID | Subscribed tier |
| `status` | Enum | ACTIVE, PAUSED, CANCELLED, EXPIRED |
| `billingInterval` | Enum | WEEKLY, MONTHLY, ANNUAL |
| `priceCents` | Int | Price per cycle in cents |
| `discountPercentage` | Decimal | Applied discount |
| `currentPeriodStart` | DateTime | Current period start |
| `currentPeriodEnd` | DateTime | Current period end |
| `nextBillingDate` | DateTime | Next charge date |
| `cancelledAt` | DateTime? | When cancelled |
| `cancellationReason` | String? | Why cancelled |

### Subscription Events

All subscription changes are logged:

| Event Type | Description |
|------------|-------------|
| `CREATED` | Subscription started |
| `ACTIVATED` | First payment successful |
| `RENEWED` | Recurring payment successful |
| `PAUSED` | Subscription paused |
| `RESUMED` | Subscription resumed |
| `CANCELLED` | Subscription cancelled |
| `EXPIRED` | Subscription ended |
| `PAYMENT_FAILED` | Billing attempt failed |
| `PAYMENT_RETRY` | Payment retry attempted |

---

## Webhooks for Subscriptions

RewardsPro listens to these Shopify webhooks:

| Webhook | Purpose |
|---------|---------|
| `subscription_contracts/create` | New subscription created |
| `subscription_contracts/update` | Status changes (pause/cancel) |
| `subscription_billing_attempts/success` | Payment succeeded |
| `subscription_billing_attempts/failure` | Payment failed |

---

## Customer Self-Service

Customers can manage subscriptions from:

### Shopify Account Page

- View active subscriptions
- See next billing date
- Pause subscription
- Cancel subscription
- Update payment method

### Customer Account Extension

If enabled, customers see:
- Subscription status badge
- Current tier benefits
- Billing history
- Management actions

---

## Best Practices

### Pricing Strategy

1. **Price below threshold value**: If Gold requires $1000 spend at 5% = $50 value, price subscription lower
2. **Offer annual discounts**: 15-20% off encourages commitment
3. **Consider upgrade paths**: Make higher tiers attractive upgrades

### Reducing Churn

1. **Clear value communication**: Show cashback earned vs subscription cost
2. **Engagement reminders**: Email about benefits being used
3. **Win-back campaigns**: Offer discounts to churned subscribers
4. **Pause option**: Better than cancellation

### Launch Checklist

- [ ] Subscription pricing configured
- [ ] Selling plans created in Shopify
- [ ] Products published to sales channels
- [ ] Webhook endpoints verified
- [ ] Customer emails configured
- [ ] Test subscription completed

---

## Troubleshooting

### Subscription Not Created

**Check:**
1. Shopify Subscriptions app is installed
2. Selling plan is attached to product
3. Customer completed checkout

### Tier Not Assigned

**Check:**
1. Subscription status is ACTIVE
2. Webhook was received
3. Customer exists in RewardsPro

### Payment Failing

**Check:**
1. Customer payment method is valid
2. Card not expired
3. Sufficient funds

**Solution:**
Customer needs to update payment method in Shopify account.

---

## Related Guides

- [Tier Products](tier-products.md) - Create purchasable tiers
- [Pricing Strategies](pricing-strategies.md) - Optimize pricing
- [Webhooks](webhooks.md) - Subscription webhook details
