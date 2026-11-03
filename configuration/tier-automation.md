---
description: Configure automatic tier recalculation for your loyalty program
---

# Tier Automation

Configure how and when RewardsPro automatically recalculates customer tiers based on their spending.

## What is Tier Automation?

Tier automation automatically evaluates customer spending and updates their tier assignments based on your configured thresholds. Without automation, you would need to manually recalculate tiers.

### Benefits

| Manual Recalculation | Automatic Recalculation |
|---------------------|------------------------|
| Requires staff time | Runs automatically |
| May be forgotten | Consistent schedule |
| Inconsistent timing | Predictable for customers |
| Delayed tier upgrades | Timely tier changes |

---

## Accessing Tier Automation Settings

1. Go to **Settings** in the main navigation
2. Select the **Tier Automation** tab

---

## Configuration Options

### Enable Automatic Tier Recalculation

A toggle to enable or disable the automated system.

| Setting | Behavior |
|---------|----------|
| **Enabled** | Tiers recalculate on schedule automatically |
| **Disabled** | No scheduled recalculation. Tiers still update when an order is paid, and when you recalculate by hand |

{% hint style="info" %}
When first enabled, the first recalculation runs at the next daily check, at 09:00 UTC.
{% endhint %}

---

### Recalculation Frequency

How often the system evaluates all customers and updates tiers.

RewardsPro checks every day at 09:00 UTC and recalculates on the frequency you choose. The interval counts from when the last recalculation finished, so a recalculation can come a day later than the interval.

| Frequency | When It Runs | Best For |
|-----------|--------------|----------|
| **Daily** | When a day has passed since the last recalculation | High-volume stores, frequent tier updates |
| **Weekly** | When 7 days have passed | Most stores (recommended) |
| **Monthly** | When 30 days have passed | Low-volume stores, stable programs |
| **Quarterly** | When 90 days have passed | Minimal tier movement needed |

### Choosing the Right Frequency

**Daily** - Choose if:
- You have high order volume (100+ orders/day)
- Customers expect immediate tier upgrades
- You run time-sensitive promotions based on tiers

**Weekly** (Recommended) - Choose if:
- Moderate order volume (10-100 orders/day)
- Want balance of accuracy and system resources
- Standard loyalty program

**Monthly** - Choose if:
- Low order volume (<10 orders/day)
- Tiers have high spend thresholds
- Customers don't expect frequent changes

**Quarterly** - Choose if:
- Very low volume or new store
- Tiers are primarily for VIP recognition
- Minimal automation needed

---

## How Recalculation Works

### The Process

```
1. System triggers at scheduled time
2. For each customer:
   a. Calculate spending in evaluation period
   b. Compare to tier thresholds
   c. Determine correct tier
   d. Update if changed
3. Log all tier changes
4. Update "Last Recalculation" timestamp
```

### Evaluation Period

Tier automation respects your tier evaluation period setting:

| Evaluation Period | Spending Calculated |
|-------------------|---------------------|
| **Annual** | Orders from last 365 days |
| **Lifetime** | All orders ever |

### What Triggers a Tier Change

A customer's tier changes when:
- Their calculated spending crosses a threshold
- They qualify for a higher tier (upgrade)
- Their spending drops below current tier minimum (downgrade)

---

## Status Information

### Last Recalculation

Shows when the automatic recalculation last completed.

| Status | Meaning |
|--------|---------|
| Timestamp shown | Last successful run |
| "Never" | Automation not yet run or just enabled |
| "In Progress" | Currently running |

### Next Scheduled Run

Calculated based on frequency and last run:

```
Next Run = the first daily check (09:00 UTC) once the frequency interval
           has passed since the last run finished

Example (Weekly):
  Last Run finished: 1 December at 09:02 UTC
  Next Run: 9 December at 09:00 UTC
```

---

## Manual Recalculation

Even with automation enabled, you can trigger a manual recalculation anytime.

### When to Use Manual Recalculation

- After importing historical orders
- After changing tier thresholds
- After fixing data issues
- Before a major promotion

### How to Trigger

1. Go to **Settings** → **Tier Automation**
2. Click **Recalculate Now**
3. Wait for completion (may take several minutes for large customer bases)

{% hint style="warning" %}
Manual recalculation processes all customers. For stores with 10,000+ customers, this may take 5-10 minutes.
{% endhint %}

---

## Tier Change Notifications

When tiers change (automatic or manual), the system:

1. **Logs the change** - Visible in Customer Details → Tier History
2. **Updates customer record** - New tier applies immediately
3. **Triggers notifications** - Sends the customer a tier upgrade or downgrade email only when a paid order changes the tier. Refunds, manual changes and scheduled recalculation send no email

### Tier Change Log

Each change records:
- Previous tier
- New tier
- Change reason (upgrade/downgrade/manual)
- Timestamp
- Triggering order (if applicable)

---

## Best Practices

### Recommended Setup

For most stores, we recommend:

```
Automation: Enabled
Frequency: Weekly
Evaluation: Annual (or Lifetime for new programs)
```

### Communicating to Customers

- **Set expectations** - Tell customers when tiers update
- **Be transparent** - Explain evaluation periods
- **Celebrate upgrades** - Notify customers of tier increases

### Handling Downgrades

Tier downgrades happen when customers don't maintain spending levels. Consider:

| Approach | Implementation |
|----------|----------------|
| **Grace period** | Use monthly frequency to give more time |
| **Notification** | Email customers before downgrade |
| **Win-back** | Offer incentives to maintain tier |

---

## Troubleshooting

### Tiers Not Updating

1. Verify automation is **Enabled**
2. Check "Last Recalculation" timestamp
3. Confirm customer has qualifying orders
4. Review tier threshold settings

### Wrong Tier Assigned

1. Check customer's total spending in evaluation period
2. Verify order dates fall within evaluation window
3. Confirm tier thresholds are set correctly
4. Review if manual override was applied

### Automation Not Running

1. Confirm toggle is set to **Enabled**
2. Check for any app errors in Shopify
3. Wait for next scheduled time
4. Contact support if issue persists

### Performance Issues

If recalculation seems slow:

1. This is normal for large customer bases
2. Process runs in background
3. Doesn't affect store performance
4. Check back in 10-15 minutes for results
