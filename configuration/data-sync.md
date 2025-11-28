---
description: Sync orders and customer data from Shopify for accurate tier calculations
---

# Data Sync

Import historical orders and keep customer data synchronized with Shopify for accurate tier calculations and analytics.

## Why Data Sync Matters

RewardsPro needs order data to:
- Calculate customer spending totals
- Determine correct tier assignments
- Generate accurate analytics
- Track cashback history

Without synced data, customers start at your base tier regardless of their purchase history.

---

## Accessing Data Sync

1. Go to **Settings** in the main navigation
2. Select the **Data Sync** tab

---

## Order History Sync

### Sync Options

Import historical orders from Shopify to calculate customer spending.

| Date Range | Orders Imported | Best For |
|------------|-----------------|----------|
| **Last 30 days** | ~1 month of orders | Quick setup, recent customers |
| **Last 90 days** | ~3 months of orders | Balanced approach |
| **Last year** | ~12 months of orders | Annual evaluation period |
| **All time** | All historical orders | Lifetime evaluation, complete data |

{% hint style="info" %}
**Recommendation**: Match your sync range to your tier evaluation period. If using annual evaluation, sync at least "Last year" of orders.
{% endhint %}

### Sync Process

1. **Select date range** from dropdown
2. **Configure options** (see below)
3. **Click "Sync Orders"**
4. **Wait for completion** - Progress shown on screen

### Sync Duration

| Order Count | Estimated Time |
|-------------|----------------|
| < 1,000 | 1-2 minutes |
| 1,000 - 10,000 | 5-10 minutes |
| 10,000 - 50,000 | 15-30 minutes |
| 50,000+ | 30-60 minutes |

{% hint style="warning" %}
Large syncs run in the background. You can navigate away and check back later.
{% endhint %}

---

## Sync Options

### Reconcile Existing Ledger Entries

| Setting | Behavior |
|---------|----------|
| **Enabled** | Compares synced orders to existing cashback records, avoids duplicates |
| **Disabled** | Creates new records without checking history |

**When to enable:**
- Re-syncing orders after fixing issues
- Importing orders that may already have cashback
- Updating after manual corrections

**When to disable:**
- Initial setup with no existing data
- Syncing a completely new date range

### Update Customer Metrics

| Setting | Behavior |
|---------|----------|
| **Enabled** | Recalculates customer totals, updates tier assignments |
| **Disabled** | Imports orders without changing tiers |

**When to enable:**
- Initial setup (recommended)
- After importing historical data
- When tiers seem incorrect

**When to disable:**
- Just importing for analytics (not tier calculation)
- Testing sync without affecting production

---

## Sync Statistics

After syncing, you'll see:

### Orders Synced

Total number of orders imported from Shopify.

### Customers Synced

Number of unique customers with orders in the sync period.

### Total Cashback Issued

Sum of all cashback from synced orders (if calculated).

### Date Range

Earliest and latest order dates in the synced data.

### Last Sync Timestamp

When the sync completed.

### Discrepancies Count

Orders that couldn't be processed or had issues.

{% hint style="info" %}
Click on **Discrepancies** to see details about orders that need attention.
{% endhint %}

---

## Customer Sync

### Automatic Sync

Customer data syncs automatically when:
- A customer places an order
- Customer info updates in Shopify
- You visit a customer's detail page

### Manual Customer Sync

To force-refresh a specific customer:
1. Go to **Customers** page
2. Find the customer
3. Click **Sync** button on their row

### Bulk Customer Sync

To sync all customers:
1. Go to **Settings** → **Data Sync**
2. Click **Sync All Customers**
3. Wait for completion

---

## When to Sync

### Initial Setup

1. Install RewardsPro
2. Configure tiers and settings
3. Sync orders matching your evaluation period
4. Enable tier automation

### After Configuration Changes

Sync after:
- Changing tier thresholds
- Switching evaluation period
- Adjusting cashback rates
- Fixing data issues

### Regular Maintenance

| Scenario | Action |
|----------|--------|
| New customer complaints | Check individual customer sync |
| Analytics seem off | Re-sync recent orders |
| Quarterly review | Full sync for data integrity |

---

## Handling Large Stores

For stores with 50,000+ orders:

### Phased Sync Approach

1. **Week 1**: Sync last 30 days (get immediate data)
2. **Week 2**: Sync last 90 days
3. **Week 3**: Sync last year
4. **Later**: Sync all time (if needed)

### Performance Tips

- Sync during low-traffic hours
- Monitor progress in background
- Don't run multiple syncs simultaneously
- Allow current sync to complete before starting another

---

## Troubleshooting

### Sync Stuck or Taking Too Long

1. Large order volumes take time - be patient
2. Check Shopify status for API issues
3. Don't close the browser during sync
4. Contact support if stuck for 2+ hours

### Missing Orders

1. Verify date range covers the orders
2. Check order status (must be paid)
3. Confirm orders aren't test orders
4. Re-sync with "Reconcile" enabled

### Duplicate Cashback Entries

1. Enable "Reconcile Existing Ledger Entries"
2. Re-sync the affected date range
3. System will deduplicate automatically

### Customer Spending Wrong

1. Check evaluation period setting
2. Verify orders are within evaluation window
3. Trigger manual tier recalculation
4. Check for refunded orders

### Sync Errors

Common causes:
- Shopify API rate limits (wait and retry)
- Network timeout (retry)
- Invalid order data (check discrepancies)

---

## Best Practices

### Before Syncing

- [ ] Configure tier settings first
- [ ] Set correct evaluation period
- [ ] Choose appropriate date range
- [ ] Plan for sync duration

### After Syncing

- [ ] Review sync statistics
- [ ] Check for discrepancies
- [ ] Verify sample customer data
- [ ] Run tier recalculation if needed

### Ongoing Maintenance

- [ ] Monitor for sync errors
- [ ] Re-sync if data seems stale
- [ ] Keep evaluation period and sync range aligned
