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

Begin with the order's successful payments (sales and captures), as Shopify records them in your store currency.

### Adjustments

| Step | Calculation |
|------|-------------|
| 1. Payments | Add up the order's payments by card or other payment methods |
| 2. Store credit and gift cards | Leave out payments made with store credit or gift cards |
| 3. Excluded products | Take off gift card products and tier products in the order |
| = Eligible Amount | Final amount for cashback |

### What's Included

- Product prices, after discounts
- Shipping charges
- Tax amounts

### What's NOT Included

- The part paid with store credit
- The part paid with gift cards
- Gift card products
- Tier products

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
- Total: $152.00, paid by card

Eligible Amount: $152.00
Customer Tier: Gold (5%)
Cashback: $152 × 0.05 = $7.60
```

If $50.00 of the same order had been paid with store credit, the eligible amount would be $102.00 and the cashback $5.10.

## Edge Cases

### Zero Cashback Scenarios

No cashback awarded when:
- The order is paid entirely with store credit or gift cards
- The order has only gift card or tier products
- The customer doesn't qualify for any tier
- The order has no customer

### Rounding

Cashback is rounded to the cent.

### Multi-Currency Orders

For stores with multiple currencies:
1. The customer pays in their currency
2. Shopify also records the payment in your store currency
3. Cashback is calculated on the store-currency amount
4. Cashback is credited in store currency

## Discount Handling

Discounts lower what the customer pays, so they lower the cashback.

### Discount Code Types

| Type | Handling |
|------|----------|
| Percentage off | Reduces eligible amount |
| Fixed amount off | Reduces eligible amount |
| Free shipping | No shipping is paid, so none counts |
| Buy X Get Y | Free items earn nothing |

## Refund Impact

A refund takes back its share of the cashback: the refunded amount divided by the order total. A refund that completes the order takes back whatever is left. RewardsPro takes it from the customer's store credit only up to what they still hold. Credit already spent isn't taken back.

### Full Refund

```
Original cashback: $7.60
Refund: Full order
Reversed: $7.60
Net cashback: $0.00
```

### Partial Refund

```
Order total: $152.00
Original cashback: $7.60
Refund: $50.00
Reversed: $7.60 × 50 / 152 = $2.50
Net cashback: $5.10
```

## Processing Timeline

| Event | Timing |
|-------|--------|
| Order placed | Immediate |
| Payment confirmed | Seconds to minutes |
| Webhook received | < 30 seconds |
| Cashback calculated | < 1 second |
| Credit applied | Straight away with Automatic Cashback on; otherwise when you issue it |
| Customer sees balance | Once the credit is in Shopify |
