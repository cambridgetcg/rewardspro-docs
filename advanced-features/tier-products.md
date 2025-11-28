---
description: Sell tier memberships as purchasable Shopify products
---

# Tier Products

Tier Products allow you to monetize your loyalty program by selling tier memberships as Shopify products. Customers can purchase instant access to premium tiers with enhanced cashback rates.

---

## How It Works

```
Customer browses tier products
        ↓
Adds "Gold Membership" to cart
        ↓
Completes checkout
        ↓
Order webhook received
        ↓
Customer automatically assigned to Gold tier
        ↓
Enhanced cashback starts immediately
```

---

## Benefits

| Benefit | Description |
|---------|-------------|
| **New Revenue Stream** | Monetize VIP access directly |
| **Immediate Tier Access** | Customers skip spending thresholds |
| **Flexible Pricing** | One-time or subscription options |
| **Shopify Integration** | Products managed in your store |
| **Automatic Assignment** | No manual tier changes needed |

---

## Creating a Tier Product

### Step 1: Navigate to Tier Products

1. Open RewardsPro in your Shopify admin
2. Go to **Tier Products** in the navigation
3. Click **Create Tier Product**

### Step 2: Select the Tier

Choose which tier this product will grant access to:

| Setting | Description |
|---------|-------------|
| **Tier** | The loyalty tier to assign on purchase |
| **Cashback Rate** | Displayed from tier settings (read-only) |
| **Current Threshold** | Spending threshold being bypassed |

### Step 3: Configure Product Details

| Field | Description | Example |
|-------|-------------|---------|
| **Product Name** | Customer-facing name | "Gold VIP Membership" |
| **Description** | Benefits and features | "Get 5% cashback on every order" |
| **SKU** | Unique identifier | "TIER-GOLD-001" |

### Step 4: Set Purchase Type

Choose how customers can buy the tier:

| Type | Description | Best For |
|------|-------------|----------|
| **One-Time** | Single purchase, fixed duration | Trial access, gift cards |
| **Subscription** | Recurring billing | Ongoing membership programs |
| **Both** | Customer chooses | Maximum flexibility |

### Step 5: Configure Pricing

#### One-Time Purchase Pricing

| Setting | Options | Description |
|---------|---------|-------------|
| **Duration** | Monthly, Annual, Lifetime | How long access lasts |
| **Price** | Your currency | One-time payment amount |

**Example Pricing:**
- Monthly: $9.99/month access
- Annual: $99.99/year (save 17%)
- Lifetime: $299.99 forever

#### Subscription Pricing

| Setting | Options | Description |
|---------|---------|-------------|
| **Billing Interval** | Weekly, Monthly, Annual | How often to charge |
| **Price** | Your currency | Recurring payment amount |
| **Discount %** | 0-50% | Discount off base price |

### Step 6: Add Features List (Optional)

List the benefits included with this tier:

```
- 5% cashback on all orders
- Early access to sales
- Free shipping on orders over $50
- Exclusive member discounts
- Priority customer support
```

### Step 7: Save and Publish

1. Review all settings
2. Click **Create Product**
3. Product is created in Shopify
4. Optionally publish to sales channels

---

## Tier Product Data

Each tier product tracks:

| Field | Description |
|-------|-------------|
| **shopifyProductId** | Linked Shopify product ID |
| **shopifyVariantId** | Product variant ID |
| **sku** | Unique SKU for the product |
| **purchaseType** | ONE_TIME, SUBSCRIPTION, or BOTH |
| **oneTimePriceCents** | Price in cents for one-time purchase |
| **oneTimeDuration** | MONTHLY, ANNUAL, or LIFETIME |
| **subscriptionPriceCents** | Price in cents for subscription |
| **billingInterval** | WEEKLY, MONTHLY, or ANNUAL |
| **discountPercentage** | Subscription discount (0-50%) |
| **features** | JSON array of benefit strings |
| **isActive** | Whether product is available |

---

## How Purchase Assignment Works

When a customer purchases a tier product:

1. **Order webhook** fires when payment completes
2. **Line items checked** for tier product SKUs
3. **Customer identified** from order email/account
4. **Tier assigned** via `PRODUCT_PURCHASE` trigger
5. **Tier change logged** in audit trail
6. **Duration tracked** (for non-lifetime purchases)

### Trigger Types

| Trigger | When Used |
|---------|-----------|
| `PRODUCT_PURCHASE` | One-time tier product purchase |
| `SUBSCRIPTION_STARTED` | New subscription activated |
| `SUBSCRIPTION_RENEWED` | Subscription renewal |
| `SUBSCRIPTION_CANCELLED` | Subscription ended |

---

## Managing Tier Products

### View All Products

The Tier Products page shows:
- Product name and tier
- Purchase type (one-time/subscription/both)
- Pricing configuration
- Active/inactive status
- Shopify product link

### Edit a Product

1. Click **Edit** on the product row
2. Modify settings as needed
3. Click **Save Changes**

{% hint style="warning" %}
**Note**: Changing prices only affects new purchases. Existing subscriptions keep their original pricing.
{% endhint %}

### Deactivate a Product

1. Click **Deactivate** on the product row
2. Product remains in Shopify but won't trigger tier assignment
3. Can be reactivated later

### Delete a Product

1. Click **Delete** on the product row
2. Confirm deletion
3. Product is unpublished in Shopify
4. Existing tier assignments are NOT affected

---

## Expiration Handling

### One-Time Purchases

| Duration | Expiration Behavior |
|----------|---------------------|
| **Monthly** | Expires 30 days after purchase |
| **Annual** | Expires 365 days after purchase |
| **Lifetime** | Never expires |

### On Expiration

When a tier product expires:
1. Customer is recalculated for spending-based tier
2. May downgrade if below threshold
3. Tier change logged with `PRODUCT_EXPIRED` reason
4. Customer notified (if email enabled)

### Grace Period

Configure a grace period in Settings:
- Default: 3 days after expiration
- During grace: Customer keeps tier
- After grace: Automatic recalculation

---

## Best Practices

### Pricing Strategy

| Tier | One-Time Annual | Subscription Monthly |
|------|-----------------|---------------------|
| Silver | $49.99 | $4.99 |
| Gold | $99.99 | $9.99 |
| Platinum | $199.99 | $19.99 |

**Tips:**
- Price annual 15-20% below 12x monthly
- Higher tiers should have clear value increase
- Consider your cashback rates in pricing

### Product Descriptions

Include in descriptions:
- Cashback percentage clearly stated
- All tier benefits listed
- Duration/renewal terms
- How to use store credit

### Marketing Tips

- Feature tier products on homepage
- Create "VIP" collection for tier products
- Use email to promote to frequent buyers
- Offer first-month discounts for subscriptions

---

## Troubleshooting

### Customer Not Assigned to Tier

**Check:**
1. Order status is "Paid"
2. Product SKU matches tier product
3. Customer has a Shopify account
4. Webhook is connected

**Solution:**
Manually assign the tier and investigate webhook logs.

### Wrong Tier Assigned

**Check:**
1. Correct tier selected for product
2. No conflicting tier products
3. Customer's existing tier status

**Solution:**
Check order line items and tier product configuration.

### Product Not Showing in Store

**Check:**
1. Product is published in Shopify
2. Product added to sales channels
3. Product is marked active in RewardsPro

---

## Related Guides

- [Tier Subscriptions](tier-subscriptions.md) - Set up recurring billing
- [Pricing Strategies](pricing-strategies.md) - Optimize your pricing
- [Tier Automation](tier-automation.md) - Automatic tier management
