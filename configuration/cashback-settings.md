---
description: Configure cashback calculation rules
---

# Cashback Settings

Fine-tune how cashback is calculated on orders.

## Calculation Settings

### Base Calculation

Cashback is calculated on the **order subtotal** by default.

```
Cashback = Subtotal × Tier Rate
```

### Include/Exclude Options

| Option | Default | Description |
|--------|---------|-------------|
| Include Shipping | ❌ No | Add shipping to calculation |
| Include Tax | ❌ No | Add tax to calculation |
| Include Discounts | ✅ Yes | Calculate after discounts |

## Order Thresholds

### Minimum Order Value

Set minimum order to earn cashback:
- Orders below threshold earn $0
- Helps prevent abuse
- Recommended: $0 or $10

### Maximum Cashback per Order

Cap the cashback on single orders:
- Protects against large orders
- Optional setting
- Recommended: Leave unlimited

## Product Rules

### Excluded Products

Products that don't earn cashback:
- Gift cards
- Donations
- Service fees
- Custom exclusions

### Excluded Collections

Entire collections can be excluded:
- Sale items
- Clearance
- Non-qualifying products

## Processing Rules

### Automatic Processing

Orders are processed automatically when:
- Payment is confirmed
- Customer has account
- No exclusions apply

### Manual Review

Flag orders for review if:
- Amount exceeds threshold
- First-time customer
- Multiple orders same day

## Refund Handling

### Automatic Reversal

When order is refunded:
- **Full refund**: Reverse entire cashback
- **Partial refund**: Proportional reversal

### Grace Period

Time before reversal:
- Default: Immediate
- Optional: 1-7 days
- Allows for partial refund adjustments
