---
description: Enable or disable specific features in your loyalty program
---

# Feature Toggles

Control which features are active in your RewardsPro installation. Feature toggles let you customize your loyalty program's functionality and gradually roll out new capabilities.

---

## Accessing Feature Toggles

1. Go to **Settings** in the main navigation
2. Select the **Features** tab

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
| **Auto Cashback Processing** | Off | Automatically process cashback when orders are paid |

**When enabled:**
- Cashback issued instantly on order payment
- No manual review required
- Fastest customer experience

**When disabled:**
- Orders queued for manual review
- You approve cashback before it's issued
- More control over fraud prevention

**Recommended for:**
- **Enable**: Established stores with low fraud risk
- **Disable**: New stores, high-value products, or fraud concerns

{% hint style="warning" %}
Even with automatic processing, refunded orders automatically reverse cashback.
{% endhint %}

---

### Email Marketing

| Setting | Default | Description |
|---------|---------|-------------|
| **Email Marketing Enabled** | Off | Enable email campaign features |

**When enabled:**
- Send promotional emails to loyalty members
- Segment customers by tier
- Track email engagement
- Schedule campaigns

**When disabled:**
- Transactional emails only (tier changes, balance updates)
- No promotional capabilities
- Reduced email quota usage

**Plan requirement:** Max or Ultra plan for full email features

---

### Tier Products

| Setting | Default | Description |
|---------|---------|-------------|
| **Tier Products Enabled** | On | Allow selling tier memberships as products |

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
| Email Marketing | Email Enabled |
| ROI Analytics | Business Metrics configured |
| Tier Products | At least one tier created |
| Auto Cashback | Order sync enabled |

---

## Plan-Based Features

Certain features are tied to your subscription plan:

| Feature | Starter | Growth | Max | Ultra |
|---------|---------|--------|-----|-------|
| Basic Analytics | Yes | Yes | Yes | Yes |
| Advanced Analytics | - | Yes | Yes | Yes |
| Manual Cashback | Yes | Yes | Yes | Yes |
| Auto Cashback | - | Yes | Yes | Yes |
| Email Notifications | Basic | Basic | Custom | White-label |
| Tier Products | Yes | Yes | Yes | Yes |
| Customer Widget | Yes | Yes | Yes | Yes |

---

## Toggle Best Practices

### For New Stores

Start conservative:

```
Advanced Analytics: On
Auto Cashback: Off (review manually first)
Email Marketing: Off
Tier Products: On (if selling memberships)
```

### For Established Stores

Enable automation:

```
Advanced Analytics: On
Auto Cashback: On (trust your customers)
Email Marketing: On (engage customers)
Tier Products: On
```

### For High-Volume Stores

Maximize efficiency:

```
Advanced Analytics: On
Auto Cashback: On (essential for scale)
Email Marketing: On (segmented campaigns)
Tier Products: On
```

---

## Troubleshooting

### Feature Not Working After Enabling

1. **Refresh the page** - Settings may need reload
2. **Check plan requirements** - Some features need higher plans
3. **Verify dependencies** - Check if related features are configured
4. **Clear browser cache** - Force fresh settings load

### Feature Greyed Out

- Feature may require plan upgrade
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
