---
description: Technical details of cashback calculation
---

# Cashback Logic

Detailed breakdown of how RewardsPro calculates cashback.

## Basic Formula

```
Cashback = Eligible Amount × Tier Rate
```

## Eligible Amount Calculation

### Starting Point

Begin with **order subtotal** (line items total).

### Adjustments

| Step | Calculation |
|------|-------------|
| 1. Line items | Sum of (price × quantity) |
| 2. Discounts | Subtract discount amounts |
| 3. Excluded items | Remove non-qualifying products |
| = Eligible Amount | Final amount for cashback |

### What's NOT Included

- Shipping charges
- Tax amounts
- Tips
- Gift cards
- Excluded products/collections

## Tier Rate Application

### Finding the Rate

1. Look up customer's current tier
2. Get the cashback percentage
3. Apply to eligible amount

### Example Calculation

```
Order Details:
- Products: $150.00
- Discount: -$20.00
- Shipping: $10.00
- Tax: $12.00
- Total: $152.00

Eligible Amount: $150 - $20 = $130.00
Customer Tier: Gold (5%)
Cashback: $130 × 0.05 = $6.50
```

## Edge Cases

### Zero Cashback Scenarios

No cashback awarded when:
- Order total is $0
- All items excluded
- Below minimum threshold
- Customer has no account

### Rounding

Cashback is rounded to 2 decimal places:
- $6.504 → $6.50
- $6.505 → $6.51

### Multi-Currency Orders

For stores with multiple currencies:
1. Order is in customer's currency
2. Converted to store currency
3. Cashback calculated in store currency
4. Credited in store currency

## Discount Handling

### Order-Level Discounts

Applied proportionally across all items.

### Item-Level Discounts

Applied to specific items only.

### Discount Code Types

| Type | Handling |
|------|----------|
| Percentage off | Reduces eligible amount |
| Fixed amount off | Reduces eligible amount |
| Free shipping | No effect on cashback |
| Buy X Get Y | Reduced on free items |

## Refund Impact

### Full Refund

```
Original cashback: $6.50
Refund: Full order
Reversed: $6.50
Net cashback: $0.00
```

### Partial Refund

```
Original order: $130.00
Original cashback: $6.50
Refund: $50.00 (38.5% of order)
Reversed: $6.50 × 0.385 = $2.50
Net cashback: $4.00
```

## Processing Timeline

| Event | Timing |
|-------|--------|
| Order placed | Immediate |
| Payment confirmed | Seconds to minutes |
| Webhook received | < 30 seconds |
| Cashback calculated | < 1 second |
| Credit applied | Immediate |
| Customer sees balance | Real-time |
