---
description: Configure automatic tier calculation and customer upgrades
---

# Tier Automation

Tier Automation automatically calculates and assigns customer tiers based on their spending. Set it up once, and RewardsPro handles tier upgrades and downgrades without manual intervention.

---

## How It Works

```
Scheduled job runs (e.g., daily at 3 AM UTC)
        ↓
For each customer:
        ↓
Calculate spending (annual or lifetime)
        ↓
Find matching tier by threshold
        ↓
If tier changed: Update assignment
        ↓
Log change in audit trail
        ↓
Continue to next customer
```

---

## Calculation Methods

### Annual Evaluation

Spending is calculated for the **last 12 months**:

| Field | Description |
|-------|-------------|
| **annualSpent** | Sum of order totals in rolling 12 months |
| **netSpent** | annualSpent minus refunds |

**Best for:**
- Seasonal businesses
- Encouraging consistent annual engagement
- Preventing one-time big spenders from permanent VIP

### Lifetime Evaluation

Spending is calculated **all-time**:

| Field | Description |
|-------|-------------|
| **totalSpent** | Sum of all order totals ever |
| **netSpent** | totalSpent minus all refunds |

**Best for:**
- High-ticket item stores
- Long customer relationships
- Rewarding overall loyalty

---

## Enabling Automation

### Step 1: Go to Settings

1. Open RewardsPro
2. Navigate to **Settings** > **Tier Automation**

### Step 2: Enable Recalculation

| Setting | Description |
|---------|-------------|
| **Enable Automatic Tier Recalculation** | Master toggle for automation |

### Step 3: Set Frequency

Choose how often tiers are recalculated:

| Frequency | Best For |
|-----------|----------|
| **Daily** | High-volume stores, immediate upgrades |
| **Weekly** | Most stores, balanced approach |
| **Monthly** | Low-volume, stable customer base |
| **Quarterly** | Large stores, seasonal evaluation |

### Step 4: Save Settings

Click **Save** to activate automation.

---

## Configuration Options

### Shop Settings

| Setting | Type | Description |
|---------|------|-------------|
| `tierRecalculationEnabled` | Boolean | Enable/disable automation |
| `tierRecalculationFrequency` | Enum | DAILY, WEEKLY, MONTHLY, QUARTERLY |
| `tierRecalculationLastRun` | DateTime | Timestamp of last execution |

### Evaluation Period

Set per tier or globally:

| Period | Spending Calculation |
|--------|---------------------|
| `ANNUAL` | Last 365 days |
| `LIFETIME` | All time |

---

## How Tiers Are Determined

### Tier Matching Logic

1. Get customer's spending (annual or lifetime)
2. Sort tiers by `minSpend` descending
3. Find first tier where spending >= minSpend
4. If no match, assign lowest tier (minSpend = 0)

### Example

**Tiers:**
| Tier | minSpend |
|------|----------|
| Platinum | $5,000 |
| Gold | $1,000 |
| Silver | $250 |
| Bronze | $0 |

**Customer spending: $1,500**

Result: Assigned to **Gold** (spending >= $1,000 but < $5,000)

---

## Trigger Types

Tier changes are logged with a trigger type:

| Trigger | Description |
|---------|-------------|
| `ACCOUNT_CREATED` | Initial tier on new customer |
| `PERIODIC_REVIEW` | Scheduled recalculation |
| `SPENDING_MILESTONE` | Immediate upgrade on threshold hit |
| `MANUAL_ADMIN` | Admin manually changed tier |
| `PRODUCT_PURCHASE` | Tier purchased via product |
| `SUBSCRIPTION_STARTED` | Tier subscription began |
| `SUBSCRIPTION_CANCELLED` | Subscription ended |

---

## Scheduled Job Details

### Cron Endpoint

```
POST /api/cron/tier-recalculation
```

### Authorization

Requires `CRON_SECRET` in Authorization header:

```
Authorization: Bearer your-cron-secret
```

### Execution

- **Default time**: Daily at 3 AM UTC
- **Max duration**: 50 seconds (Vercel limit)
- **Batch size**: Configurable per shop

### Job Flow

1. Verify authorization
2. Query all shops with automation enabled
3. For each shop:
   - Get recalculation frequency
   - Check if due for recalculation
   - Process customers in batches
   - Update tier assignments
   - Log changes
4. Return summary

---

## Manual Override Protection

When a tier is manually assigned by an admin:

| Setting | Behavior |
|---------|----------|
| **Protected** (default) | Automation skips this customer |
| **Not Protected** | Automation can override |

### How It Works

1. Admin manually assigns customer to tier
2. `TierChangeLog` created with `MANUAL_ADMIN` trigger
3. Customer marked as manually assigned
4. Automated recalculation skips this customer

### Clearing Override

To allow automation again:
1. Open Customer Details
2. Go to Tier tab
3. Click **Reset to Automatic**
4. Customer included in next recalculation

---

## Dry Run Mode

Test recalculation without making changes:

### In Settings

1. Go to **Settings** > **Tier Automation**
2. Click **Run Dry Run**
3. Review proposed changes
4. Decide whether to apply

### Dry Run Output

Shows:
- Total customers evaluated
- Customers who would upgrade
- Customers who would downgrade
- Customers unchanged

---

## Tier Change Logging

Every tier change creates a log entry:

### TierChangeLog Fields

| Field | Description |
|-------|-------------|
| `customerId` | Affected customer |
| `previousTierId` | Old tier (null if first) |
| `newTierId` | New tier |
| `changeType` | INITIAL_ASSIGNMENT, UPGRADE, DOWNGRADE |
| `triggerType` | What caused the change |
| `spendingAtChange` | Customer spending at time |
| `metadata` | Additional context (JSON) |
| `createdAt` | When change occurred |

### Viewing Logs

1. Open Customer Details
2. Go to **Tier Changes** tab
3. View chronological history

Or in Analytics:
1. Go to **Analytics** > **Tier Movement**
2. Filter by date range
3. Export if needed

---

## Best Practices

### Frequency Selection

| Store Type | Recommended |
|------------|-------------|
| High volume (100+ orders/day) | Daily |
| Medium volume (10-100/day) | Weekly |
| Low volume (<10/day) | Monthly |
| Seasonal | Quarterly with manual reviews |

### Threshold Tuning

Review tier thresholds periodically:

1. Check tier distribution in Analytics
2. Aim for pyramid shape:
   - Base tier: 40-50% of customers
   - Mid tiers: 30-40%
   - Top tier: 5-15%
3. Adjust thresholds if distribution is off

### Communication

When customers upgrade or downgrade:

- **Upgrades**: Celebrate! Send email about new benefits
- **Downgrades**: Handle sensitively, explain how to regain tier

---

## Troubleshooting

### Customers Not Upgrading

**Check:**
1. Automation is enabled
2. Frequency allows recalculation
3. Customer spending meets threshold
4. Customer not manually assigned

**Solution:**
Run manual recalculation or check individual customer.

### Wrong Tier Assigned

**Check:**
1. Tier thresholds are correct
2. Evaluation period matches expectation
3. Order spending is synced
4. Refunds properly deducted

**Solution:**
Verify customer spending in Customer Details.

### Automation Not Running

**Check:**
1. Cron job is configured
2. CRON_SECRET is set
3. No errors in logs
4. Last run date

**Solution:**
Check Vercel cron logs or manually trigger job.

### Mass Unexpected Changes

**Check:**
1. Threshold wasn't accidentally changed
2. Evaluation period wasn't switched
3. Large data sync didn't occur

**Solution:**
Review recent settings changes, consider restoring.

---

## Advanced: Real-Time Upgrades

For immediate tier upgrades on order completion:

### How It Works

1. Customer places order
2. Order webhook fires
3. Check if spending crosses threshold
4. If yes: Upgrade immediately
5. Don't wait for scheduled job

### Configuration

```
Settings > Tier Automation > Real-Time Upgrades
```

| Setting | Description |
|---------|-------------|
| **Enable Real-Time** | Upgrade on order completion |
| **Upgrade Only** | Only upgrade, never downgrade in real-time |

---

## Related Guides

- [Creating Tiers](../core-features/membership-tiers/create.md) - Set up tier thresholds
- [Customer Details](../core-features/customers-management/customer-details.md) - View tier history
- [Analytics](../core-features/analytics.md) - Tier distribution metrics
