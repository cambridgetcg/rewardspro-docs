---
description: Set up recurring membership subscriptions for ongoing tier access
---

# Subscription Setup

Convert your tier products into recurring subscriptions for predictable revenue and ongoing customer engagement.

## Why Subscriptions?

| Benefit | Description |
|---------|-------------|
| **Recurring Revenue** | Predictable monthly/annual income |
| **Higher LTV** | Customers stay engaged longer |
| **Reduced Churn** | Automatic renewal reduces drop-off |
| **Better Planning** | Forecast membership numbers |

## Setting Up Subscriptions

### Requirements

To enable subscriptions, you need:
- Shopify subscription app (Shopify Subscriptions, Recharge, etc.)
- Tier products created in RewardsPro
- Payment gateway supporting recurring billing

### Step-by-Step Setup

#### 1. Install Subscription App

Popular options:
- **Shopify Subscriptions** (free, native)
- **Recharge** (advanced features)
- **Bold Subscriptions** (flexible)

#### 2. Configure Tier Product

1. Go to the tier product in Shopify
2. Enable subscription selling plan
3. Set billing frequency
4. Configure pricing

#### 3. Set Billing Intervals

| Interval | Best For | Typical Discount |
|----------|----------|------------------|
| Monthly | Trial/testing | 0% |
| Quarterly | Moderate commitment | 10% |
| Annual | Best value | 20-30% |

### Subscription Pricing Example

**Gold Membership:**

| Plan | Price | Annual Cost | Savings |
|------|-------|-------------|---------|
| Monthly | $9.99/mo | $119.88 | - |
| Quarterly | $24.99/qtr | $99.96 | 17% |
| Annual | $79.99/yr | $79.99 | 33% |

## How Renewals Work

### Automatic Processing

When a subscription renews:

1. **Payment Charged** - Customer's card is billed
2. **Order Created** - Shopify creates renewal order
3. **Webhook Received** - RewardsPro is notified
4. **Membership Extended** - Tier access continues

### Timeline

```
Day 1: Initial purchase → Tier activated
Day 30: Subscription renews → Tier extended
Day 60: Subscription renews → Tier extended
...continues automatically
```

## Managing Subscriptions

### Customer Self-Service

Customers can manage their subscription:
- View next billing date
- Update payment method
- Change plan (upgrade/downgrade)
- Cancel subscription

### Merchant Controls

You can:
- Pause subscriptions
- Skip billing cycles
- Apply discounts
- Cancel on behalf of customer

## Handling Cancellations

### When Customer Cancels

Options for handling tier access:

| Option | Behavior |
|--------|----------|
| **Immediate** | Tier reverts right away |
| **End of Period** | Keep tier until paid period ends |
| **Grace Period** | Extra days to resubscribe |

### Recommended: End of Period

Most customer-friendly approach:
1. Customer cancels
2. Keeps tier benefits until billing period ends
3. After expiry, reverts to earned tier

## Failed Payments

### Dunning Process

When payment fails:

| Day | Action |
|-----|--------|
| 0 | First attempt fails, retry scheduled |
| 3 | Second attempt + email notification |
| 7 | Third attempt + urgent email |
| 14 | Subscription paused/cancelled |

### Tier Status During Dunning

**Recommended:** Keep tier active during retry period
- Better customer experience
- Higher recovery rate
- Grace period shows goodwill

## Subscription Analytics

Track subscription health:

| Metric | Target |
|--------|--------|
| **MRR** (Monthly Recurring Revenue) | Growing |
| **Churn Rate** | < 5% monthly |
| **Failed Payment Recovery** | > 70% |
| **Average Subscription Length** | > 6 months |

## Best Practices

### Pricing

✅ **Do:**
- Offer annual discount (20-30% off)
- Show monthly equivalent price
- Highlight savings prominently

❌ **Don't:**
- Make cancellation difficult
- Hide subscription terms
- Charge immediately without trial option

### Communication

✅ **Do:**
- Send renewal reminders
- Notify before price changes
- Thank subscribers regularly

❌ **Don't:**
- Surprise customers with charges
- Skip failed payment notifications
- Ignore inactive subscribers

### Retention

✅ **Do:**
- Offer pause instead of cancel
- Provide downgrade options
- Win-back campaigns for churned

❌ **Don't:**
- Let cancellations happen silently
- Ignore engagement metrics
- Forget to survey churned customers
