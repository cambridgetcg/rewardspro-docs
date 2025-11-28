# Automation

RewardsPro automates key aspects of your loyalty program, reducing manual work while ensuring customers receive their rewards instantly.

## Automatic Cashback

### How It Works

When a customer completes a purchase, RewardsPro automatically:

1. **Receives Order Webhook**: Shopify notifies RewardsPro of the paid order
2. **Identifies Customer**: Matches the order to your customer database
3. **Calculates Cashback**: Applies the customer's tier rate to the order total
4. **Credits Account**: Instantly adds store credit to their balance
5. **Logs Transaction**: Records the transaction with full audit trail

### Cashback Calculation

```
Cashback = Order Subtotal × Tier Cashback Rate
```

**Example**: A Silver tier customer (3% cashback) places a $150 order:
- Cashback = $150 × 0.03 = **$4.50**

### Exclusions

Cashback is calculated on the order subtotal, which excludes:
- Shipping costs
- Taxes
- Tips

Discounts are applied before cashback calculation.

## Automatic Tier Progression

### Upgrade Logic

RewardsPro continuously monitors customer spending and automatically upgrades tiers:

1. Customer spending is tracked in real-time
2. When spend exceeds a tier threshold, upgrade is triggered
3. Customer is moved to the higher tier instantly
4. New cashback rate applies to future purchases

### Evaluation Periods

#### Annual Evaluation
- Reviews spending from the past 12 months
- Recalculates tier status monthly
- Customers can be upgraded or downgraded

#### Lifetime Evaluation
- Tracks total spending since signup
- Customers only move up, never down
- Rewards long-term loyalty

### Tier Change Notifications

When a customer's tier changes:
- Change is logged in the system
- Customer widget updates automatically
- Email notifications (coming soon)

## Webhook Events

RewardsPro responds to the following Shopify webhooks:

### Orders

| Event | Action |
|-------|--------|
| `orders/paid` | Calculate and award cashback |
| `orders/create` | Track order for analytics |
| `orders/refunded` | Option to reverse cashback or convert to credit |

### Customers

| Event | Action |
|-------|--------|
| `customers/create` | Add customer to loyalty program |
| `customers/update` | Sync customer information |
| `customers/delete` | Handle customer data removal |

### App Lifecycle

| Event | Action |
|-------|--------|
| `app/uninstalled` | Clean up store data |
| `shop/update` | Sync store settings |

## Scheduled Tasks

RewardsPro runs scheduled tasks to maintain program health:

### Daily Tasks
- **Tier Recalculation**: Review and update customer tiers based on spending
- **Data Sync**: Ensure customer data is synchronized with Shopify

### Monthly Tasks
- **Usage Tracking**: Calculate monthly order volume for billing
- **Analytics Aggregation**: Compile monthly performance metrics

## Integration with Shopify Flow

RewardsPro events can trigger Shopify Flow automations:

### Available Triggers (Coming Soon)
- Customer tier upgraded
- Customer tier downgraded
- Store credit awarded
- Store credit redeemed
- Spending milestone reached

### Example Flows

**VIP Welcome Email**
```
Trigger: Customer upgraded to Platinum tier
Action: Send email template "VIP Welcome"
```

**Milestone Bonus**
```
Trigger: Customer reaches $1,000 lifetime spend
Action: Add $25 bonus store credit
```

## Best Practices

### Cashback Configuration
- Set reasonable cashback rates (1-10% typical)
- Higher tiers should have meaningfully better rates
- Consider your margins when setting rates

### Tier Thresholds
- Make the first tier upgrade achievable (e.g., $200-500)
- Space tiers to encourage continued engagement
- Top tier should feel exclusive but attainable

### Monitoring
- Review the Analytics dashboard weekly
- Check for unusual patterns in credit issuance
- Monitor tier distribution for healthy progression

## Troubleshooting

### Cashback Not Awarded

1. **Check Order Status**: Cashback only triggers on paid orders
2. **Verify Customer Match**: Customer must have a matching account
3. **Review Webhook Logs**: Check if webhook was received
4. **Manual Award**: Use the customer detail page to manually add credit

### Tier Not Updating

1. **Check Evaluation Period**: Annual evaluation may have different timing
2. **Verify Spending Total**: Ensure order is counted in spend calculation
3. **Manual Override**: Administrators can manually assign tiers

### Webhook Failures

1. **Check App Status**: Ensure RewardsPro is properly installed
2. **Verify Permissions**: App needs order and customer read access
3. **Contact Support**: Persistent issues may need investigation
