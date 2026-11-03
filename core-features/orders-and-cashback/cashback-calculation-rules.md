---
description: Understand exactly how cashback amounts are calculated
---

# Cashback Calculation Rules

RewardsPro uses the same formula on every paid order. Knowing it helps you set tier rates and explain rewards to customers.

---

## The Cashback Formula

```
Cashback = (amount paid, not counting store credit or gift cards
            - gift card products and tier products in the order)
           × (cashbackPercent / 100)
```

### Variables Explained

| Variable | Description |
|----------|-------------|
| **Amount paid** | What the customer paid by card or another payment method, as Shopify records it in your store currency. The part paid with store credit or a gift card doesn't count |
| **Gift card and tier products** | Gift cards and tier products bought in the order are taken off |
| **cashbackPercent** | The cashback rate of the customer's tier |

### Important Notes

- **Shipping and tax are included**, because they're part of what the customer paid
- **Discounts lower the cashback**, because they lower what the customer paid
- **Store credit and gift card payments earn nothing**, so spending cashback doesn't earn more cashback
- **Cashback is rounded** to the cent

### Calculation Example

**Order Details:**

| Field | Amount |
|-------|--------|
| Subtotal | $150.00 |
| Discounts | -$20.00 |
| Shipping | $10.00 |
| Tax | $12.00 |
| **Total paid by card** | **$152.00** |

**Cashback Calculation:**
```
Eligible Amount = $152.00 (everything paid by card)
Cashback Rate = 5% (Gold tier)
Cashback = $152.00 × 0.05 = $7.60
```

The customer earns **$7.60** in store credit.

If the same customer had paid $50.00 of that order with store credit and $102.00 by card, only the card payment would count: $102.00 × 0.05 = $5.10.

---

## What's Included

### ✅ Counts Toward Cashback

| Item | Explanation |
|------|-------------|
| **Product prices** | After any discounts, as the customer paid them |
| **Shipping** | Part of what the customer paid |
| **Tax** | Part of what the customer paid |

### ❌ Doesn't Count

| Item | Reason |
|------|--------|
| **Payments with store credit** | Spending cashback doesn't earn cashback |
| **Payments with gift cards** | Already a stored value |
| **Gift card products** | Taken off, so buying a gift card earns nothing |
| **Tier products** | A membership purchase doesn't earn cashback on itself |

There's no setting to leave out other products or collections.

---

## Tier Rate Application

### Finding the Rate

1. Identify the customer on the order
2. Look up their current tier
3. Get the tier's cashback percentage
4. Apply it to the eligible amount

### Tier at Time of Order

Cashback uses the tier the customer has when RewardsPro processes the paid order. If the spending in that order moves them up a tier, the order still earns at their previous tier. The new rate applies from their next order.

A customer who has no tier yet is placed in one first, using this order's spending, and the order earns at that tier.

The rate is saved with each cashback entry, so later tier changes don't change cashback already earned.

---

## Edge Cases

### Zero Cashback Scenarios

No cashback is awarded when:

| Scenario | Result |
|----------|--------|
| No customer on the order | $0 |
| The customer doesn't qualify for any tier | $0 |
| Paid entirely with store credit or gift cards | $0 |
| Only gift cards or tier products in the order | $0 |
| Refunded in full before the cashback was recorded | $0 |

### Rounding

Cashback is rounded to the cent.

### Multi-Currency

Shopify records each payment in your store currency as well as in the customer's currency. RewardsPro uses the amount in your store currency, and issues the cashback in your store currency.

**Example:**
```
Order paid by card: €100.00 EUR
Shopify's amount in your store currency: $108.00 USD
Tier rate: 5%
Cashback: $5.40 USD
```

---

## Refunds

When an order is refunded, RewardsPro takes back the refunded share of its cashback, up to the store credit the customer still holds. Credit already spent isn't taken back.

---

## Verifying Calculations

### In Transaction History

The customer's store credit history shows each cashback entry with:
- The cashback amount
- The order it came from
- The tier rate used
- The date

### Audit Trail

For disputes:
1. Check how the order was paid in Shopify: by card, store credit or gift card
2. Check for gift cards or tier products in the order
3. Verify the customer's tier at the time of the order
4. Recalculate with the formula above

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

Cashback is paid on shipping and tax too, so work out your rates on the full amount customers pay:
```
Profit margin: 40%
Max sustainable cashback: ~15-20% of margin
Example: 40% × 15% = 6% max cashback
```

### Communication

Help customers understand:
- How cashback is calculated
- That paying with store credit or a gift card earns no cashback
- When credit is issued
- How to check their balance
