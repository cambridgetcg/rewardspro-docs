---
description: Automated reporting and insights for your loyalty program
---

# Analytics

RewardsPro automatically tracks and aggregates loyalty program data, providing actionable insights without manual reporting.

## Dashboard Overview

The Analytics dashboard provides at-a-glance metrics:

### Key Performance Indicators

| Metric | Description |
|--------|-------------|
| **Total Members** | Customers enrolled in your program |
| **Active Members** | Customers with purchases in past 90 days |
| **Total Credit Issued** | Lifetime store credit awarded |
| **Credit Redeemed** | Store credit used by customers |
| **Redemption Rate** | % of issued credit that's been used |

### Tier Distribution

Visual breakdown of customers across tiers:

```
Platinum ████░░░░░░░░░░░░░░░░  8%
Gold     ████████░░░░░░░░░░░░ 18%
Silver   ██████████████░░░░░░ 32%
Bronze   ████████████████████ 42%
```

## Automated Reports

### Daily Metrics

Automatically calculated each day:

- New member signups
- Orders processed
- Cashback awarded
- Tier changes (upgrades/downgrades)
- Store credit redemptions

### Weekly Summary

Compiled every Monday:

- Week-over-week comparison
- Top customers by spend
- Tier movement trends
- Credit utilization rate

### Monthly Report

Generated on the 1st of each month:

- Monthly recurring metrics
- Seasonal trend analysis
- Program health score
- Growth rate calculations

## Real-Time Tracking

### Live Dashboard Updates

The following update in real-time:

- ✅ New orders and cashback
- ✅ Store credit balance changes
- ✅ Tier upgrades
- ✅ Customer signups

### Webhook Event Stream

All events are logged with timestamps:

```
[10:32:15] Order #1234 - $150.00 - Gold tier - $7.50 cashback
[10:32:16] Customer upgraded: Silver → Gold
[10:45:22] Store credit redeemed: $25.00
[11:02:33] New customer signup: john@example.com
```

## Metrics Breakdown

### Cashback Metrics

| Metric | Calculation |
|--------|-------------|
| Total Issued | Sum of all cashback ever awarded |
| This Month | Cashback awarded current month |
| Average Rate | Weighted average across all orders |
| By Tier | Breakdown per tier level |

### Customer Metrics

| Metric | Calculation |
|--------|-------------|
| Lifetime Value | Average total spend per customer |
| Active Rate | % customers with recent purchase |
| Churn Risk | Inactive 60+ days |
| Upgrade Rate | % who upgrade within 6 months |

### Credit Metrics

| Metric | Calculation |
|--------|-------------|
| Outstanding | Total unredeemed credit |
| Velocity | Average time to redemption |
| Usage Rate | Orders using store credit |
| Average Use | Typical credit amount per redemption |

## Trend Analysis

### Automatic Trend Detection

RewardsPro identifies:

- **Growth Trends** - Increasing member signups
- **Engagement Drops** - Declining activity
- **Seasonal Patterns** - Recurring spikes/dips
- **Tier Stagnation** - Customers stuck at a tier

### Comparative Analysis

Compare periods automatically:

- This week vs. last week
- This month vs. last month
- This quarter vs. same quarter last year

## Export & Integration

### Data Export

Export analytics data for external analysis:

1. Go to **Analytics**
2. Select date range
3. Choose metrics to include
4. Click **Export CSV**

### Available Export Fields

- Date/time
- Customer ID
- Order ID
- Amount
- Cashback earned
- Tier at time of purchase
- Store credit balance

### API Access (Coming Soon)

Programmatic access to analytics:

```json
GET /api/analytics/summary
{
  "period": "month",
  "metrics": ["revenue", "cashback", "signups"]
}
```

## Alerts & Notifications

### Automated Alerts

Configure alerts for:

| Alert | Trigger |
|-------|---------|
| High Redemption | Credit usage spike |
| Low Engagement | Activity drops 20%+ |
| Processing Error | Webhook failures |
| Milestone | Program reaches goal |

### Alert Channels

Receive alerts via:
- Email to store admin
- Shopify admin notifications
- Slack integration (coming soon)

## Best Practices

### Review Frequency

| Report | Recommended Review |
|--------|-------------------|
| Daily metrics | Glance each morning |
| Weekly summary | Team meeting review |
| Monthly report | Strategic planning |
| Quarterly trends | Program optimization |

### Key Questions to Ask

1. Is our redemption rate healthy? (Target: 40-60%)
2. Are customers progressing through tiers?
3. What's our cashback liability?
4. Which tier drives the most revenue?
5. Are new members engaging quickly?
