---
description: How orders are processed and cashback is calculated
---

# Orders & Cashback

RewardsPro automatically processes orders and awards cashback to customers.

## Order Processing Flow

```
Order Placed → Payment Confirmed → Cashback Calculated → Credit Added
```

### Step-by-Step

1. **Customer places order** on your store
2. **Payment confirmed** by Shopify
3. **Webhook received** by RewardsPro
4. **Customer identified** in database
5. **Tier rate applied** to order total
6. **Store credit added** to balance
7. **Transaction logged** for audit

## Viewing Orders

Navigate to **Orders** to see:
- Order number and date
- Customer name and tier
- Order total
- Cashback amount
- Processing status

### Order Status

| Status | Meaning |
|--------|---------|
| ✅ Processed | Cashback awarded |
| ⏳ Pending | Awaiting payment |
| ❌ Failed | Processing error |
| 🔄 Refunded | Cashback reversed |

## Cashback Calculation

### Formula

```
Cashback = Order Subtotal × Tier Rate
```

### What's Included

| ✅ Included | ❌ Excluded |
|-------------|-------------|
| Product prices | Shipping costs |
| Discounted items | Taxes |
| Bundle products | Tips |
| | Gift cards |

### Example

**Gold tier customer (5%)** places $200 order:
- Order subtotal: $200
- Tier rate: 5%
- **Cashback: $10.00**

## Manual Processing

### Award Missed Cashback

If an order wasn't processed:
1. Go to Orders
2. Find the order
3. Click **Process Cashback**
4. Confirm amount

### Reverse Cashback

If cashback was awarded incorrectly:
1. Go to customer detail
2. Find the transaction
3. Click **Reverse**
4. Enter reason

## Refund Handling

### Full Refund

Options when order is fully refunded:
- Reverse cashback automatically
- Keep cashback (goodwill)
- Convert to store credit

### Partial Refund

Options for partial refunds:
- Proportional cashback reduction
- No change to cashback
- Custom adjustment

## Troubleshooting

### Order Not Processing

1. Check order status (must be paid)
2. Verify customer has account
3. Check webhook logs
4. Process manually if needed

### Wrong Cashback Amount

1. Verify tier at time of order
2. Check order subtotal
3. Review any exclusions
4. Adjust manually if needed
