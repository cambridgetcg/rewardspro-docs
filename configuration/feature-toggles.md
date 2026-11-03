---
description: Enable or disable specific features in your loyalty program
---

# Feature Toggles

Control which features are active in your RewardsPro installation. Feature toggles let you customize your loyalty program's functionality and gradually roll out new capabilities.

---

## Accessing Feature Toggles

1. Open the RewardsPro dashboard (**Home**)
2. Find the **Features** card

---

## Available Toggles

### Advanced Analytics

| Setting | Default | Description |
|---------|---------|-------------|
| **Advanced Analytics Enabled** | On | Enable detailed analytics and reporting features |

**When enabled:**
- ROI calculations with business metrics
- Customer behavior analysis
- Tier movement analytics
- Export capabilities
- Trend analysis

**When disabled:**
- Basic order and customer counts only
- No business metric calculations
- Simplified dashboard

{% hint style="info" %}
**Tip**: Keep this enabled to get the most value from your loyalty program data.
{% endhint %}

---

### Automatic Cashback Processing

| Setting | Default | Description |
|---------|---------|-------------|
| **Automatic Cashback** | Off | Automatically process cashback when orders are paid |

**When enabled:**
- Cashback issued instantly on order payment
- No manual review required
- Fastest customer experience

**When disabled:**
- Cashback waits on the **Orders** page
- You issue it yourself, order by order
- More control over fraud prevention

**Recommended for:**
- **Enable**: Established stores with low fraud risk
- **Disable**: New stores, high-value products, or fraud concerns

{% hint style="warning" %}
Even with automatic processing, refunded orders automatically reverse cashback.
{% endhint %}

---

### Email Marketing

Email campaigns and automations aren't sending yet. There's no toggle for them on the **Features** card. Welcome and tier-change emails are separate and send on their own. See [Email Settings](email-settings.md).

---

### Membership Tiers

| Setting | Default | Description |
|---------|---------|-------------|
| **Membership Tiers** | On | Allow selling tier memberships as products (tier products) |

**When enabled:**
- Create products that grant tier access
- Sell tier upgrades in your store
- One-time tier purchases available

**When disabled:**
- Tiers based on spending only
- No tier product creation
- Simplified tier management

**Use cases:**
- **Enable**: Want to sell VIP memberships
- **Disable**: Prefer spending-based tiers only

See [Tier Products](../advanced-features/tier-products.md) for setup guide.

---

## Feature Dependencies

Some features depend on others:

| Feature | Requires |
|---------|----------|
| ROI Analytics | Business Metrics configured |
| Tier Products | At least one tier created |
| Auto Cashback | Order sync enabled |

---

## Plans

RewardsPro is free, with one plan, Free Forever. These toggles aren't tied to a plan.

---

## Toggle Best Practices

### For New Stores

Start conservative:

```
Advanced Analytics: On
Automatic Cashback: Off (review manually first)
Membership Tiers: On (if selling memberships)
```

### For Established Stores

Enable automation:

```
Advanced Analytics: On
Automatic Cashback: On (trust your customers)
Membership Tiers: On
```

### For High-Volume Stores

Maximize efficiency:

```
Advanced Analytics: On
Automatic Cashback: On (essential for scale)
Membership Tiers: On
```

---

## Troubleshooting

### Feature Not Working After Enabling

1. **Refresh the page** - Settings may need reload
2. **Verify dependencies** - Check if related features are configured
3. **Clear browser cache** - Force fresh settings load

### Feature Greyed Out

- Dependent setting not configured
- Contact support if issue persists

### Unexpected Behavior After Toggle

1. Changes apply to new transactions only
2. Historical data unchanged
3. Allow a few minutes for propagation
4. Check for related webhook processing

---

## Related Guides

- [Store Settings](store-settings.md) - Basic store configuration
- [Business Metrics](business-metrics.md) - Required for advanced analytics
- [Email Settings](email-settings.md) - Email marketing configuration
- [Tier Products](../advanced-features/tier-products.md) - Selling tier access
