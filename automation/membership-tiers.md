---
description: Automatic tier progression and management based on customer spending
---

# Membership Tiers

RewardsPro automatically manages customer tier assignments based on their spending, upgrading or downgrading customers as they hit spending thresholds.

## Automatic Tier Progression

### How Upgrades Work

When a customer's spending crosses a tier threshold:

1. **Spending Tracked** - Each order updates the customer's total spend
2. **Threshold Check** - System compares spend against tier requirements
3. **Automatic Upgrade** - Customer moves to the higher tier instantly
4. **New Rate Applied** - Higher cashback rate applies to future purchases

### Example Progression

| Tier | Threshold | Cashback | Customer Status |
|------|-----------|----------|-----------------|
| Bronze | $0 | 2% | Started here |
| Silver | $500 | 3% | ✅ Upgraded at $500 spend |
| Gold | $1,000 | 5% | ✅ Upgraded at $1,000 spend |
| Platinum | $2,500 | 7% | Current goal |

## Evaluation Periods

RewardsPro supports two evaluation methods:

### Annual Evaluation

- **Timeframe**: Rolling 12-month window
- **Recalculation**: Monthly or on each order
- **Movement**: Customers can move up OR down
- **Best for**: Encouraging ongoing engagement

**How it works:**
- Only orders from the past 12 months count toward tier qualification
- If spending drops below threshold, customer may be downgraded
- Promotes consistent purchasing behavior

### Lifetime Evaluation

- **Timeframe**: All-time since account creation
- **Recalculation**: On each order
- **Movement**: Customers only move UP, never down
- **Best for**: Rewarding long-term loyalty

**How it works:**
- Every order ever placed counts toward tier qualification
- Once a tier is earned, it's never lost
- Creates a sense of permanent achievement

## Tier Change Events

When a tier changes, RewardsPro:

1. **Updates Database** - New tier assignment is saved
2. **Logs the Change** - Full audit trail with timestamp and reason
3. **Updates Widget** - Customer sees new tier in real-time
4. **Triggers Webhooks** - (Coming soon) For Flow automations

### Tier Change Log

Every tier change is recorded with:
- Previous tier
- New tier
- Change reason (spending threshold, manual assignment)
- Timestamp
- Associated order (if applicable)

## Manual Tier Assignment

Administrators can manually assign tiers for:

- **VIP Customers** - Assign top tier regardless of spend
- **Business Accounts** - Special tier arrangements
- **Promotional Upgrades** - Time-limited tier bumps
- **Corrections** - Fix any assignment errors

### To Manually Assign a Tier:

1. Go to **Customers**
2. Click on the customer
3. Select **Change Tier**
4. Choose the new tier
5. Add a reason (optional)
6. Save

## Configuring Tiers

### Creating a New Tier

1. Navigate to **Membership Tiers**
2. Click **Create Tier**
3. Configure:
   - **Name**: Display name (e.g., "Gold Member")
   - **Minimum Spend**: Threshold to reach this tier
   - **Cashback Rate**: Percentage earned (0-100%)
   - **Color**: Visual identifier

### Best Practices

| Recommendation | Why |
|----------------|-----|
| 3-4 tiers maximum | Easy for customers to understand |
| Achievable first upgrade | $200-500 for first tier up |
| Meaningful rate increases | At least 1-2% between tiers |
| Distinctive names | Create aspiration and status |

## Default Tier

Every store must have a default tier:
- Automatically assigned to new customers
- Cannot be deleted
- Typically your entry-level tier
- Should still offer some benefit (1-2% cashback)

## Tier Notifications

### Customer Communication

Customers are informed of tier changes through:
- **Widget Update** - Real-time tier display
- **Email Notification** - (Coming soon)
- **Progress Indicators** - Show progress to next tier

### Merchant Alerts

Track tier activity in the dashboard:
- Upgrades this week/month
- Downgrades (if using annual evaluation)
- Customers approaching next tier
