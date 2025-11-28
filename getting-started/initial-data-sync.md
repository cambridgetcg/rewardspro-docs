---
description: Import your existing customers and historical orders
---

# Initial Data Sync

Import your existing customer base and historical orders so customers start with accurate tier placements and cashback history.

## Why Sync Data?

Without syncing historical data:
- All customers start at your base tier (regardless of past spending)
- No historical cashback is credited
- Analytics show incomplete data

With syncing:
- Customers are placed in correct tiers based on actual spending
- Loyal customers are recognized immediately
- Analytics reflect true program performance

---

## What Gets Synced

| Data Type | What's Imported | Used For |
|-----------|-----------------|----------|
| **Customers** | Name, email, account info | Customer profiles |
| **Orders** | Order totals, dates, line items | Tier calculations, cashback |
| **Spending Totals** | Calculated from orders | Tier placement |

---

## Step-by-Step Sync Process

### Step 1: Navigate to Data Sync

1. Go to **Settings** in the sidebar
2. Click the **Data Sync** tab

### Step 2: Choose Your Date Range

Select how much historical data to import:

| Option | Best For | Sync Time |
|--------|----------|-----------|
| **Last 30 days** | Quick setup, testing | 1-2 minutes |
| **Last 90 days** | Balanced approach | 5-10 minutes |
| **Last year** | Annual evaluation period | 15-30 minutes |
| **All time** | Lifetime evaluation, complete history | 30-60 minutes |

{% hint style="info" %}
**Recommendation**: Match your sync range to your tier evaluation period. If using annual evaluation, sync at least "Last year" of orders.
{% endhint %}

### Step 3: Configure Sync Options

| Option | When to Enable |
|--------|----------------|
| **Update Customer Metrics** | Always enable for initial sync |
| **Reconcile Ledger Entries** | Enable if re-syncing or fixing data |

### Step 4: Start the Sync

1. Click **Sync Orders**
2. Wait for the progress bar to complete
3. Review the sync summary

{% hint style="warning" %}
**Large stores**: Syncing 50,000+ orders may take 30-60 minutes. You can navigate away - the sync continues in the background.
{% endhint %}

---

## After Syncing

### Review Sync Results

Check the sync summary:
- **Orders Synced**: Total orders imported
- **Customers Updated**: Unique customers with orders
- **Discrepancies**: Any orders that couldn't be processed

### Verify Customer Tiers

Spot-check a few customers:

1. Go to **Customers**
2. Find a known high-value customer
3. Verify their tier matches their spending

### Check for Issues

If tiers seem wrong:
1. Confirm the sync date range covers their orders
2. Check the evaluation period setting
3. Verify tier thresholds are set correctly

---

## Syncing Strategies

### For New Stores (< 1,000 orders)

```
Recommended: Sync "All time"
Time: 2-5 minutes
Result: Complete historical data
```

### For Established Stores (1,000 - 50,000 orders)

```
Recommended: Sync "Last year" initially
Then: Sync "All time" later if needed
Time: 15-30 minutes
Result: Recent customers get proper tiers
```

### For Large Stores (50,000+ orders)

```
Phase 1: Sync "Last 30 days" (immediate data)
Phase 2: Sync "Last 90 days" (next day)
Phase 3: Sync "Last year" (weekend)
Phase 4: Sync "All time" (if needed)
```

---

## Troubleshooting

### Sync Takes Too Long

- This is normal for large order volumes
- Sync runs in the background
- Check back in 15-30 minutes

### Customers Still at Base Tier

1. Verify sync completed successfully
2. Check sync date range includes their orders
3. Confirm **Update Customer Metrics** was enabled
4. Trigger a manual tier recalculation in Settings

### Missing Orders

1. Check order status (must be "Paid")
2. Verify orders are within sync date range
3. Look for entries in the Discrepancies list

---

## Next Steps

- [Assigning Existing VIPs](assigning-vips.md) - Manually promote your top customers
- [Testing Your Setup](testing-your-setup.md) - Verify everything works

