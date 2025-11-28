---
description: Understand exactly how cashback amounts are calculated
---

# Cashback Calculation Rules

RewardsPro uses a consistent formula to calculate cashback on every order. Understanding these rules helps you configure tiers effectively and explain rewards to customers.

---

## The Cashback Formula

```
Cashback Amount = (subtotalPrice - totalDiscounts) × (cashbackPercent / 100)
```

### Variables Explained

| Variable | Description | From Order Data |
|----------|-------------|-----------------|
| **subtotalPrice** | Sum of line item prices before any adjustments | Order.subtotalPrice |
| **totalDiscounts** | All discounts applied to the order | Order.totalDiscounts |
| **cashbackPercent** | Customer's tier percentage at time of order | Tier.cashbackPercent |
| **cashbackAmount** | Final credit earned (stored on order) | Order.cashbackAmount |

### Important Notes

- **Shipping and tax are NOT included** in cashback calculation
- **Discounts are subtracted** before calculating cashback
- **Tier rate is locked** at the time of order (stored as `cashbackPercentAtOrder`)
- **Cashback is rounded** to 2 decimal places

### Calculation Example

**Order Details:**

| Field | Amount |
|-------|--------|
| subtotalPrice | $150.00 |
| totalDiscounts | $20.00 |
| totalShipping | $10.00 |
| totalTax | $12.00 |
| **totalPrice** | **$152.00** |

**Cashback Calculation:**
```
Eligible Amount = $150.00 - $20.00 = $130.00
Cashback Rate = 5% (Gold tier)
Cashback = $130.00 × 0.05 = $6.50
```

The customer earns **$6.50** in store credit, even though the order total was $152.00.

---

## What's Included

### ✅ Included in Calculation

| Item | Explanation |
|------|-------------|
| **Product prices** | Base price of items |
| **Variant prices** | Size, color variations |
| **After discounts** | Calculate on discounted price |
| **Bundle products** | Full bundle price |
| **Pre-order items** | When payment collected |

### ❌ Excluded from Calculation

| Item | Reason |
|------|--------|
| **Shipping costs** | Not product value |
| **Taxes** | Government fees |
| **Tips** | Not merchandise |
| **Gift cards** | Already a stored value |
| **Excluded products** | If configured |

---

## Discount Handling

### Order-Level Discounts

Discounts that apply to the entire order:
- Percentage off (e.g., 20% off)
- Fixed amount off (e.g., $25 off)
- Free shipping (no effect on cashback)

**Calculation:**
```
Subtotal: $200.00
20% discount: -$40.00
Eligible: $160.00
```

### Item-Level Discounts

Discounts that apply to specific items:
- Sale prices
- Buy X Get Y promotions
- Automatic discounts

**Calculation:**
```
Item 1: $100.00 (full price)
Item 2: $50.00 (was $80, on sale)
Eligible: $150.00 (uses sale price)
```

### Stacked Discounts

When multiple discounts apply:
- All discounts are subtracted
- Cashback calculated on final amount

---

## Tier Rate Application

### Finding the Rate

1. Identify the customer
2. Look up their current tier
3. Get the tier's cashback percentage
4. Apply to eligible amount

### Tier at Time of Order

**Important:** Cashback uses the tier at **order time**, not current tier.

**Example:**
- Customer was Silver (3%) when ordering
- Upgraded to Gold (5%) the next day
- Cashback on that order = 3% (Silver rate)

This ensures:
- Accurate historical records
- Fair tier progression
- No retroactive changes

---

## Edge Cases

### Zero Cashback Scenarios

No cashback is awarded when:

| Scenario | Result |
|----------|--------|
| Guest checkout | $0 (no customer account) |
| No tier assigned | $0 (assign default tier) |
| All items excluded | $0 (nothing eligible) |
| Below minimum order | $0 (if threshold set) |
| Zero subtotal | $0 (free order) |

### Rounding

Cashback is rounded to **2 decimal places**:
- $6.504 → $6.50
- $6.505 → $6.51
- $6.506 → $6.51

Standard banker's rounding is used.

### Multi-Currency

For stores with multiple currencies:

1. Order placed in customer's currency
2. Converted to store currency (if different)
3. Cashback calculated in store currency
4. Credited in store currency

**Example:**
```
Order: €100.00 EUR
Exchange rate: 1 EUR = $1.10 USD
Converted: $110.00 USD
Tier rate: 5%
Cashback: $5.50 USD
```

---

## Product Exclusions

### Excluding Specific Products

Some products may not earn cashback:
- Gift cards
- Donations
- Service fees
- Sale/clearance items (optional)

**Configuration:**
1. Go to **Settings** → **Cashback Rules**
2. Add products or collections to exclude
3. These items won't count toward cashback

### Excluding Collections

Entire collections can be excluded:
- Create "No Cashback" collection
- Add products to it
- Configure exclusion in settings

---

## Order Scenarios

### Standard Order

```
Products: $100.00
Tier: Silver (3%)
Cashback: $3.00
```

### Discounted Order

```
Products: $100.00
Discount: -$20.00
Tier: Silver (3%)
Eligible: $80.00
Cashback: $2.40
```

### Partial Exclusion

```
Product A: $75.00 (eligible)
Product B: $25.00 (gift card - excluded)
Tier: Gold (5%)
Eligible: $75.00
Cashback: $3.75
```

### Mixed Currency

```
Order: £80.00 GBP
Store currency: USD
Exchange rate: 1.25
Converted: $100.00 USD
Tier: Gold (5%)
Cashback: $5.00 USD
```

---

## Verifying Calculations

### In Order Details

Each processed order shows:
- Order subtotal
- Discounts applied
- Tier at time of order
- Calculated cashback
- Any exclusions

### In Transaction History

Customer ledger shows:
- Cashback amount
- Reference to order
- Tier information
- Timestamp

### Audit Trail

For disputes:
1. Check order total and discounts
2. Verify tier at time of order
3. Check for excluded products
4. Recalculate manually if needed

---

## Best Practices

### Setting Rates

| Tier Level | Suggested Rate | Why |
|------------|----------------|-----|
| Entry | 1-2% | Accessible reward |
| Mid | 3-4% | Meaningful upgrade |
| Upper | 5-6% | Strong incentive |
| Top | 7-10% | VIP treatment |

### Margin Consideration

Ensure cashback is sustainable:
```
Profit margin: 40%
Max sustainable cashback: ~15-20% of margin
Example: 40% × 15% = 6% max cashback
```

### Communication

Help customers understand:
- How cashback is calculated
- What's included/excluded
- When credit is issued
- How to check their balance
