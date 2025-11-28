---
description: Understanding how tier memberships activate, renew, and expire
---

# Membership Lifecycle

Learn how tier product memberships work from purchase to expiration.

## Lifecycle Stages

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│  Purchase   │ → │  Activate   │ → │   Active    │ → │   Expire    │
│             │    │             │    │             │    │             │
│ Customer    │    │ Tier        │    │ Customer    │    │ Reverts to  │
│ buys product│    │ assigned    │    │ enjoys      │    │ earned tier │
│             │    │ instantly   │    │ benefits    │    │             │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
```

## Stage 1: Purchase

### What Happens

1. Customer adds tier product to cart
2. Completes checkout
3. Payment is processed
4. Order is created in Shopify

### Order Requirements

For activation to occur:

| Requirement | Status |
|-------------|--------|
| Payment | Must be completed |
| Order Status | Paid or fulfilled |
| Customer Account | Must exist |
| Product SKU | Must match RewardsPro format |

### Guest Checkout

If customer checks out as guest:
- Order is created
- Activation waits for account
- Customer prompted to create account
- Tier activates when account linked

## Stage 2: Activation

### Instant Activation

Once payment confirms:

1. **Webhook Received** - RewardsPro notified of order
2. **Product Identified** - SKU matched to tier/duration
3. **Customer Found** - Order linked to customer record
4. **Tier Assigned** - Customer upgraded immediately
5. **Expiry Set** - End date calculated

### Activation Timeline

| Event | Timing |
|-------|--------|
| Payment confirmed | T+0 |
| Webhook sent | T+0 to T+30s |
| Tier activated | T+1 to T+60s |
| Customer notified | Real-time (widget) |

### What Customer Sees

- Widget immediately shows new tier
- Cashback rate updates
- Progress bar reflects new status
- Benefits list updates

## Stage 3: Active Membership

### During Active Period

Customer enjoys:
- Higher cashback rate
- All tier benefits
- Tier badge in widget
- Status in account

### Tracking Active Memberships

RewardsPro tracks:

| Data | Description |
|------|-------------|
| Start Date | When membership began |
| End Date | When membership expires |
| Original Order | Purchase that created membership |
| Tier Level | Which tier was purchased |

### Multiple Memberships

If customer purchases while already having membership:

| Scenario | Behavior |
|----------|----------|
| Same tier | Duration extended |
| Higher tier | Upgraded, time added |
| Lower tier | Queued after current expires |

## Stage 4: Approaching Expiration

### Pre-Expiration Notifications

| Days Before | Action |
|-------------|--------|
| 30 days | First reminder email |
| 14 days | Second reminder |
| 7 days | Urgent reminder |
| 1 day | Final reminder |

### Widget Indicators

As expiration approaches:
- Shows "Expires in X days"
- Highlights renewal option
- May show "Renew Now" button

## Stage 5: Expiration

### What Happens at Expiry

1. **Membership Ends** - Purchased tier access stops
2. **Tier Recalculated** - Customer's earned tier determined
3. **Status Updated** - Widget reflects new tier
4. **Benefits Adjusted** - Cashback rate changes

### Tier After Expiration

Customer reverts to their **earned tier** based on spending:

| Spending | Earned Tier |
|----------|-------------|
| $0 - $499 | Bronze (2%) |
| $500 - $999 | Silver (3%) |
| $1,000 - $2,499 | Gold (5%) |
| $2,500+ | Platinum (7%) |

### Example

```
Customer: Jane
Purchased: Gold Membership (12 months)
Lifetime Spend: $750

During Membership: Gold tier (5% cashback)
After Expiration: Silver tier (3% cashback)
                  (based on $750 lifetime spend)
```

## Renewal Flow

### Manual Renewal

Customer purchases again:
1. Buys tier product
2. New order created
3. Membership extended
4. New expiry date set

### Automatic Renewal (Subscriptions)

If set up as subscription:
1. Billing date arrives
2. Payment auto-charged
3. Renewal order created
4. Membership seamlessly continues

## Edge Cases

### Refund Requested

| Timing | Recommended Action |
|--------|-------------------|
| Within 24 hours | Full refund, revoke tier |
| Within 7 days | Prorated refund option |
| After 7 days | Store credit or deny |

### Upgrade Mid-Membership

If customer wants to upgrade:

**Option 1: Immediate Upgrade**
- Charge difference
- Upgrade tier immediately
- Keep original end date

**Option 2: New Membership**
- Full price for new tier
- Old membership value credited
- New duration starts

### Downgrade Request

Generally not offered, but options:
- Wait for expiration
- Partial refund to store credit
- Pause instead of downgrade

## Reporting

### Membership Reports

Track membership health:

| Metric | Description |
|--------|-------------|
| Active Memberships | Currently active count |
| Expiring Soon | Within 30 days |
| Expired This Month | Recently ended |
| Renewal Rate | % who renew |
| Average Duration | How long customers stay |

### Export Data

Export membership data for analysis:
- Customer email
- Tier level
- Start/end dates
- Purchase order
- Renewal history
