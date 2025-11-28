---
description: Configure cashback calculation rules and processing options
---

# Cashback Settings

Configure how cashback is calculated, when it's awarded, and how refunds are handled.

## How Cashback Works

When a customer places an order, RewardsPro automatically calculates cashback based on:

1. **Order amount** (subtotal, with optional inclusions)
2. **Customer's tier** (determines cashback percentage)
3. **Product eligibility** (exclusions if configured)
4. **Order thresholds** (minimum order requirements)

```
Cashback = Eligible Amount × Tier Cashback Rate

Example:
  Order Subtotal: $100
  Customer Tier: Gold (5% cashback)
  Cashback Earned: $100 × 0.05 = $5.00
```

---

## Accessing Cashback Settings

1. Go to **Settings** in the main navigation
2. Select the **Cashback** tab

---

## Calculation Settings

### Base Calculation

Cashback is calculated on the **order subtotal** by default. The subtotal is the sum of product prices after line-item discounts but before shipping and tax.

### Include/Exclude Options

Configure what's included in the cashback calculation:

| Option | Default | When Enabled | Recommendation |
|--------|---------|--------------|----------------|
| **Include Shipping** | Off | Shipping costs count toward cashback | Keep off (shipping varies) |
| **Include Tax** | Off | Tax amount counts toward cashback | Keep off (tax isn't profit) |
| **Calculate After Discounts** | On | Discount codes reduce eligible amount | Keep on (standard practice) |

**Example with options:**

```
Order Subtotal: $100
Discount Code: -$20
Shipping: $10
Tax: $8

Default calculation:
  Eligible Amount: $100 - $20 = $80
  (Shipping and tax excluded)

With all options enabled:
  Eligible Amount: $100 - $20 + $10 + $8 = $98
```

{% hint style="info" %}
Including shipping in cashback calculation can incentivize free shipping thresholds but may complicate margin calculations.
{% endhint %}

---

## Order Thresholds

### Minimum Order Value

Set a minimum order subtotal required to earn cashback.

| Setting | Effect | Use Case |
|---------|--------|----------|
| **$0** | All orders earn cashback | Maximum engagement |
| **$10-25** | Small orders excluded | Reduce tiny transactions |
| **$50+** | Only larger orders qualify | Premium positioning |

**Behavior:**
- Orders below threshold earn **$0 cashback**
- Customer still accumulates spend toward tier progress
- Threshold applies to eligible amount (after discounts)

{% hint style="warning" %}
Setting threshold too high may frustrate customers. Consider your average order value.
{% endhint %}

### Maximum Cashback per Order

Cap the maximum cashback amount on a single order.

| Setting | Use Case |
|---------|----------|
| **No limit** (default) | Standard stores, simple |
| **$50** | Prevent abuse on large orders |
| **$100** | Balance protection and rewards |
| **Custom** | Based on your margins |

**Example:**
```
Order: $2,000
Tier Rate: 10%
Calculated Cashback: $200

With $50 cap:
  Actual Cashback: $50 (capped)
```

---

## Product Exclusions

### Excluded Products

Specific products that don't earn cashback:

| Product Type | Why Exclude |
|--------------|-------------|
| **Gift Cards** | Already a form of store credit |
| **Donations** | No profit margin |
| **Service Fees** | Not product revenue |
| **Subscriptions** | Handled separately |

**How to configure:**
1. Go to **Settings** → **Cashback**
2. Find **Product Exclusions**
3. Search and select products to exclude
4. Save changes

### Excluded Collections

Exclude entire product collections:

| Collection Type | Reasoning |
|-----------------|-----------|
| **Sale/Clearance** | Already discounted, margins thin |
| **Cost Items** | Sold at or below cost |
| **Partner Products** | Different margin structure |
| **Pre-Orders** | Revenue not yet realized |

**Mixed order handling:**
```
Order:
  Regular Product: $80
  Sale Item (excluded): $40

Eligible Amount: $80 (sale item not counted)
Cashback at 5%: $4.00
```

---

## Processing Rules

### Automatic Processing

Orders are processed automatically when:

| Condition | Requirement |
|-----------|-------------|
| **Payment Status** | Order marked as "Paid" in Shopify |
| **Customer Account** | Customer has email on file |
| **No Exclusions** | No excluded products or collections apply |
| **Above Threshold** | Meets minimum order requirement |

**Processing timeline:**
1. Order placed and paid
2. Webhook received (instant)
3. Cashback calculated
4. Balance credited to customer
5. Ledger entry created

### Manual Review Queue

Flag orders for review before processing:

| Flag Condition | Default | Purpose |
|----------------|---------|---------|
| **Cashback exceeds $X** | Off | Protect against large orders |
| **First-time customer** | Off | Fraud prevention |
| **Multiple orders same day** | Off | Detect abuse |
| **Guest checkout** | Off | Encourage account creation |

{% hint style="info" %}
Manual review queue is available on Growth and Max plans.
{% endhint %}

---

## Refund Handling

### Automatic Reversal

When an order is refunded in Shopify, cashback is automatically reversed:

| Refund Type | Cashback Reversal |
|-------------|-------------------|
| **Full refund** | 100% of original cashback deducted |
| **Partial refund** | Proportional amount deducted |
| **Item return** | Item's portion of cashback deducted |

**Partial refund example:**
```
Original Order: $100
Original Cashback: $5.00 (5%)

Partial Refund: $40
Cashback Reversal: $2.00 (40% of $5.00)
New Balance Effect: -$2.00
```

### Negative Balance Handling

If reversal exceeds current balance:

| Setting | Behavior |
|---------|----------|
| **Allow Negative** | Balance can go negative, recovered on next order |
| **Cap at Zero** | Balance stops at $0, remainder forgiven |

{% hint style="warning" %}
"Cap at Zero" prevents negative balances but may result in lost cashback revenue.
{% endhint %}

### Grace Period

Optional delay before processing refund reversals:

| Period | Use Case |
|--------|----------|
| **Immediate** (default) | Real-time accuracy |
| **24 hours** | Allow for refund adjustments |
| **3 days** | Complex refund scenarios |
| **7 days** | High-value orders |

---

## Best Practices

### For New Stores

Start with conservative settings:

```
Minimum Order: $0 (engage all customers)
Maximum Cashback: No limit
Exclusions: Gift cards only
Processing: Automatic
Refund Handling: Immediate
```

### For Established Stores

Optimize based on data:

```
Minimum Order: Based on AOV analysis
Maximum Cashback: 2-3x your average cashback
Exclusions: Sale items, low-margin products
Processing: Automatic with flags for high values
Refund Handling: 24-hour grace period
```

### For High-Volume Stores

Protect margins while rewarding loyalty:

```
Minimum Order: $15-25
Maximum Cashback: $75-100
Exclusions: Sale, clearance, partner products
Processing: Manual review for $100+ cashback
Refund Handling: Immediate with negative balance cap
```

---

## Troubleshooting

### Customer Didn't Receive Cashback

1. Verify order is marked "Paid" in Shopify
2. Check if products were excluded
3. Confirm order met minimum threshold
4. Review manual review queue
5. Check for processing errors in sync status

### Wrong Cashback Amount

1. Review what's included in calculation
2. Check for excluded products in order
3. Verify customer's current tier
4. Confirm discount handling

### Refund Not Reversing Cashback

1. Check if order was originally synced
2. Verify refund webhook was received
3. Review grace period setting
4. Check for sync errors

