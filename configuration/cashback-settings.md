---
description: How cashback is calculated, and the one setting that controls when it's issued
---

# Cashback Settings

Cashback has one setting today: **Automatic Cashback**, which decides whether cashback is issued to customers on its own. The way cashback is calculated is fixed.

## How Cashback Works

When a paid order arrives, RewardsPro works out its cashback from:

1. **What the customer paid**, by card or another payment method, including shipping and tax. The part paid with store credit or gift cards doesn't count
2. **The products in the order**: gift card products and tier products are taken off
3. **The customer's tier**, which sets the cashback percentage

```
Cashback = Eligible Amount × Tier Cashback Rate

Example:
  Paid by card: $100 (including shipping and tax)
  Customer Tier: Gold (5% cashback)
  Cashback Earned: $100 × 0.05 = $5.00
```

See [Cashback Calculation Rules](../core-features/orders-and-cashback/cashback-calculation-rules.md) for every detail.

---

## Automatic Cashback

Find it on the RewardsPro dashboard (**Home**), in the **Features** card.

| Setting | Default | What it does |
|---------|---------|--------------|
| **Automatic Cashback** | Off | When on, each paid order's cashback is sent to the customer as Shopify store credit straight away. When off, cashback waits on the **Orders** page until you issue it |

If Shopify doesn't accept a cashback send, the cashback stays pending. A scheduled job tries again, and you can also issue it yourself from the **Orders** page.

---

## What You Can't Change Yet

RewardsPro has no settings for:

- including or leaving out shipping and tax
- a minimum order value or a maximum cashback per order
- leaving out other products or collections
- review flags for large or first-time orders
- negative balances, or a delay before refunds take cashback back

---

## Refund Handling

When an order is refunded in Shopify, RewardsPro takes back the refunded share of its cashback:

| Refund Type | Cashback Taken Back |
|-------------|---------------------|
| **Full refund** | All of the order's cashback |
| **Partial refund** | The refunded amount's share of the order total |

**Partial refund example:**
```
Order total: $100
Original Cashback: $5.00 (5%)

Partial Refund: $40
Cashback Taken Back: $2.00 (40% of $5.00)
```

If the cashback hasn't been issued yet, RewardsPro lowers the amount still to issue. If it has, RewardsPro takes the share from the customer's store credit, but only up to what they still hold. Credit already spent isn't taken back, so a balance never goes below zero.

---

## Troubleshooting

### Customer Didn't Receive Cashback

1. Verify the order is marked "Paid" in Shopify
2. Check whether **Automatic Cashback** is on. If it's off, issue the cashback from the **Orders** page
3. Check that the customer has a tier
4. Check how the order was paid: store credit and gift card payments earn nothing

### Wrong Cashback Amount

1. Check for store credit or gift card payments on the order
2. Check for gift card or tier products in the order
3. Verify the customer's tier
4. Remember that shipping and tax count

### Refund Not Taking Back Cashback

1. Check whether the customer already spent the credit. Spent credit isn't taken back
2. Check that the refund was made in Shopify
