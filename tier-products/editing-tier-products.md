---
description: Modify, manage, and optimize your tier membership products
---

# Editing Tier Products

Once created, tier products can be fully customized in Shopify while maintaining their connection to RewardsPro.

## Accessing Tier Products

<figure><img src="../.gitbook/assets/TP Products page.png" alt="Tier Products in Shopify admin products page"><figcaption>Tier Products appear in your Shopify Products admin</figcaption></figure>

Tier Products are automatically created as Shopify products and appear in **Products** in your Shopify admin.

### Finding Your Tier Products

1. Go to **Products** in Shopify admin
2. Search for "Membership" or the tier name
3. Or filter by Product Type: "Membership"
4. Or filter by Vendor: "RewardsPro"

## Editable Fields

You can customize most product fields to match your brand:

### ✅ Can Edit

| Field | Recommendations |
|-------|-----------------|
| **Product Title** | Make it compelling: "Gold VIP Membership" |
| **Description** | List all benefits, include FAQ |
| **Images** | Use branded membership graphics |
| **Price** | Adjust based on promotions |
| **Compare-at Price** | Show original value for sales |
| **Sales Channels** | Control where it's sold |
| **Collections** | Add to "Memberships" collection |
| **Tags** | Add for organization |
| **SEO Settings** | Optimize title and description |

### ❌ Cannot Edit

| Field | Reason |
|-------|--------|
| **SKU** | Used by RewardsPro to identify the tier and duration |

> ⚠️ **Important:** Do not modify the SKU. RewardsPro uses this to correctly assign tiers when the product is purchased.

## Customizing Product Details

### Product Title

**Default:** "Gold Membership - 12 Months"

**Better options:**
- "Gold VIP Membership (1 Year)"
- "Exclusive Gold Status - Annual"
- "Gold Tier Access - Save 5% on Every Order"

### Product Description

Include these elements:

```markdown
## What You Get

🌟 **Instant Gold Status** - Activated immediately after purchase

### Gold Member Benefits:
- ✅ 5% cashback on every order
- ✅ Early access to sales
- ✅ Free shipping on orders $50+
- ✅ Exclusive member-only products
- ✅ Birthday bonus credit

### How It Works:
1. Purchase this membership
2. Your account is upgraded instantly
3. Enjoy Gold benefits for 12 months
4. Earn cashback on all your orders

### FAQ:
**When does my membership start?**
Immediately after purchase.

**What happens when it expires?**
You'll return to your earned tier based on spending.

**Can I upgrade later?**
Yes! Upgrade to Platinum anytime.
```

### Product Images

Create compelling membership graphics:

| Image Type | Suggestions |
|------------|-------------|
| **Main Image** | Membership card design with tier name |
| **Gallery 1** | Benefits infographic |
| **Gallery 2** | Value comparison chart |
| **Gallery 3** | Happy customer testimonial |

**Image Specifications:**
- Recommended: 2048 x 2048 px
- Format: PNG or JPG
- Style: Match your brand

## Pricing Strategies

### Regular Pricing

Set a price that represents good value:

```
Gold Tier Benefits Value:
- 5% cashback on $2,000/year spending = $100
- Free shipping value (est.) = $50
- Early access (est. savings) = $30
Total Value: $180/year

Suggested Price: $79-99/year (55-45% discount)
```

### Sale Pricing

Use compare-at price for promotions:

| Scenario | Price | Compare-at |
|----------|-------|------------|
| Regular | $99 | - |
| Sale (20% off) | $79 | $99 |
| Black Friday | $59 | $99 |
| Flash Sale | $49 | $99 |

### Subscription Pricing

For recurring memberships:

| Billing | Price | Savings |
|---------|-------|---------|
| Monthly | $9.99/mo | - |
| Quarterly | $24.99/qtr | 17% |
| Annual | $79.99/yr | 33% |

## Sales Channels

Control where tier products are sold:

| Channel | Recommended |
|---------|-------------|
| Online Store | ✅ Yes |
| Point of Sale | ✅ Yes (for retail) |
| Shop App | ✅ Yes |
| Facebook/Instagram | ⚠️ Optional |
| Google Shopping | ⚠️ Optional |
| Wholesale | ❌ Usually no |

## Collections & Organization

### Create a Memberships Collection

1. Go to **Products → Collections**
2. Create "Membership Plans" collection
3. Add all tier products
4. Feature on homepage or navigation

### Suggested Collection Structure

```
Memberships/
├── All Memberships (main collection)
├── Monthly Plans
├── Annual Plans (best value)
└── Gift Memberships
```

## Managing Inventory

### Inventory Settings

For tier products, recommended settings:

| Setting | Value | Reason |
|---------|-------|--------|
| Track inventory | ❌ Off | Unlimited digital product |
| Continue selling when out of stock | ✅ On | Always available |
| SKU | Don't change | Required for RewardsPro |

## Deleting Tier Products

### From RewardsPro

1. Go to **Membership Tiers**
2. Find the tier product
3. Click **Delete**
4. Product is archived in Shopify

### Important Notes

- Existing memberships remain active until expiration
- Consider archiving instead of deleting
- Customers with active memberships keep their benefits

## Troubleshooting

### Product Not Granting Tier

1. **Check SKU** - Must match exactly
2. **Verify Order** - Must be paid/fulfilled
3. **Check Customer** - Must have account
4. **Review Logs** - Check RewardsPro activity

### Duplicate Products

If you accidentally have duplicates:
1. Identify the correct one (check SKU format)
2. Archive or delete the duplicate
3. Ensure only one product per tier/duration

### Price Not Updating

After changing price:
1. Clear any caching apps
2. Check sales channel sync
3. Verify no discount codes conflicting
