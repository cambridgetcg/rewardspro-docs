---
description: Create purchasable membership products that grant customers instant tier access
---

# Creating Tier Products

Tier Products allow customers to purchase direct access to loyalty tiers, bypassing the traditional spending thresholds. This is perfect for subscription-based loyalty programs or VIP memberships.

## Overview

### What Are Tier Products?

Tier Products are Shopify products that, when purchased, automatically assign the customer to a specific loyalty tier for a set duration.

| Feature | Description |
|---------|-------------|
| **Instant Upgrade** | Customer gets tier benefits immediately |
| **Time-Limited** | Membership lasts for set duration |
| **Recurring Option** | Can be set up as subscription |
| **Shopify Native** | Managed like any other product |

### Use Cases

- **VIP Memberships** - Sell Gold/Platinum access directly
- **Annual Programs** - Yearly membership purchases
- **Trial Periods** - Let customers try higher tiers
- **B2B Programs** - Business customer tier access

## Tier Product Coverage

<figure><img src="../.gitbook/assets/Screenshot 2025-11-24 at 21.39.50.png" alt="Tier Product Coverage Module showing available tiers and their product status"><figcaption>Tier Product Coverage Module in the Membership Tiers Page</figcaption></figure>

The Tier Products Coverage Module is found on the **Membership Tiers** page. It shows:
- Which tiers have products created
- Product status (active/draft)
- Quick actions to create or edit

## Create Tier Product

<figure><img src="../.gitbook/assets/Create Tier Products.png" alt="Create Tier Product form with tier selection, duration, and pricing fields"><figcaption>Create Tier Product dialog</figcaption></figure>

### Step-by-Step Guide

1. Navigate to **Membership Tiers** in RewardsPro
2. Find the **Tier Product Coverage** section
3. Click **Create** next to the tier you want
4. Configure the product settings (see below)
5. Click **Create Product**

### Configuration Options

#### Tier Selection

Choose which tier this product grants access to:

| Tier | Typical Price Point | Suggested Duration |
|------|--------------------|--------------------|
| Silver | $9.99 - $19.99 | 1-3 months |
| Gold | $29.99 - $49.99 | 3-6 months |
| Platinum | $99.99 - $199.99 | 12 months |

#### Duration

Set how long the tier membership lasts:

| Duration | Best For |
|----------|----------|
| 1 Month | Trial memberships |
| 3 Months | Quarterly programs |
| 6 Months | Semi-annual |
| 12 Months | Annual memberships |
| Lifetime | Permanent VIP status |

#### Pricing

Set the purchase price for the membership:

**Pricing Strategies:**

- **Value-Based** - Price based on cashback savings
- **Competitive** - Match competitor programs
- **Tiered Pricing** - Longer durations = better value

**Example Calculation:**
```
Gold tier = 5% cashback
Average customer spends $200/month
Monthly cashback value = $10
12-month value = $120
Suggested price: $79-99 (discount to actual value)
```

## After Creation

Once created, the tier product:

1. **Appears in Shopify** - Listed in Products admin
2. **Gets Unique SKU** - Used for tier identification
3. **Ready to Sell** - Add to collections, feature on site

### What Gets Created

| Element | Details |
|---------|---------|
| Product Title | "[Tier Name] Membership - [Duration]" |
| SKU | `REWARDSPRO-[TIER]-[DURATION]` |
| Product Type | "Membership" |
| Vendor | "RewardsPro" |
| Status | Draft (publish when ready) |

## Best Practices

### Pricing Strategy

✅ **Do:**
- Price below the calculated cashback value
- Offer discounts for longer commitments
- Create urgency with limited-time pricing

❌ **Don't:**
- Overprice compared to earning potential
- Hide the tier benefits
- Make it confusing which tier they're buying

### Product Presentation

✅ **Do:**
- Use compelling product images
- List all tier benefits clearly
- Show the savings/value proposition
- Include FAQ in description

❌ **Don't:**
- Leave default placeholder content
- Skip the product description
- Forget to set up proper collections

### Launch Checklist

- [ ] Product images uploaded
- [ ] Description highlights benefits
- [ ] Price is competitive
- [ ] Added to relevant collections
- [ ] Sales channels configured
- [ ] Test purchase completed
- [ ] Published and live

## Related

- [Editing Tier Products](editing-tier-products.md) - Modify existing products
- [Membership Tiers](../automation/membership-tiers.md) - Tier configuration
