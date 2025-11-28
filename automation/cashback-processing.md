---
description: How RewardsPro automatically calculates and awards cashback on customer purchases
---

# Cashback Processing

RewardsPro automatically processes cashback rewards when customers complete purchases, requiring no manual intervention.

## How It Works

When a customer completes a purchase, RewardsPro automatically:

1. **Receives Order Webhook** - Shopify notifies RewardsPro when an order is paid
2. **Identifies Customer** - Matches the order to your customer database
3. **Calculates Cashback** - Applies the customer's tier rate to the order total
4. **Credits Account** - Instantly adds store credit to their balance
5. **Logs Transaction** - Records the transaction with full audit trail

## Cashback Calculation

The cashback formula is straightforward:

```
Cashback = Order Subtotal × Tier Cashback Rate
```

### Example

A **Gold tier** customer (5% cashback) places a $200 order:

| Component | Value |
|-----------|-------|
| Order Subtotal | $200.00 |
| Tier Rate | 5% |
| **Cashback Earned** | **$10.00** |

The $10.00 is automatically added to their store credit balance.

## What's Included in Calculations

### ✅ Included
- Product prices
- Product variants
- Discounted amounts (after discount applied)

### ❌ Excluded
- Shipping costs
- Taxes
- Tips
- Gift card purchases

## Order States

Cashback is only processed for specific order states:

| Order State | Cashback Awarded? |
|-------------|-------------------|
| Paid | ✅ Yes |
| Pending | ❌ No |
| Partially Paid | ❌ No |
| Refunded | Reversed (optional) |
| Cancelled | ❌ No |

## Processing Timeline

| Event | Timing |
|-------|--------|
| Order placed | Immediate webhook |
| Cashback calculated | < 1 second |
| Balance updated | Instant |
| Customer notified | Real-time (via widget) |

## Handling Edge Cases

### Partial Refunds
When an order is partially refunded, you can choose to:
- Proportionally reduce the cashback earned
- Convert the refund to store credit
- Keep the original cashback (goodwill gesture)

### Order Modifications
If an order total changes after processing:
- Cashback adjustments can be made manually
- Or configure automatic recalculation

### Duplicate Prevention
RewardsPro uses idempotency keys to prevent:
- Double-processing of webhooks
- Duplicate cashback awards
- Race conditions on rapid orders

## Monitoring

Track cashback processing in the **Analytics** dashboard:
- Total cashback issued today/week/month
- Average cashback per order
- Cashback by tier breakdown
- Failed processing alerts

## Troubleshooting

### Cashback Not Awarded

1. **Check Order Status** - Only "paid" orders trigger cashback
2. **Verify Customer Match** - Customer must have an account
3. **Review Webhook Logs** - Ensure webhook was received
4. **Manual Award** - Use customer detail page to add credit manually

### Delayed Processing

If cashback seems delayed:
1. Check Shopify webhook delivery status
2. Verify app is properly installed
3. Contact support if issues persist
