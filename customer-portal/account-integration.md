---
description: Integrate RewardsPro into your customer account pages
---

# Account Integration

Display loyalty information directly in your customers' account pages for a seamless experience.

## Account Page Options

### Shopify Customer Accounts

RewardsPro integrates with both account types:

| Account Type | Integration Method |
|--------------|-------------------|
| **Classic Accounts** | Theme block |
| **New Customer Accounts** | Account UI extension |

## Classic Customer Accounts

### Adding the Loyalty Section

1. Go to **Online Store → Themes → Customize**
2. Navigate to **Customer Account** template
3. Add **RewardsPro Account Block**
4. Position in desired location
5. Save

### Available Blocks

| Block | Content |
|-------|---------|
| **Full Dashboard** | Complete loyalty overview |
| **Tier Status** | Current tier and progress |
| **Credit Balance** | Store credit with history |
| **Rewards Summary** | Compact overview card |

### Recommended Layout

```
┌─────────────────────────────────────┐
│ Welcome back, {Customer Name}       │
├─────────────────────────────────────┤
│ ┌─────────────┐ ┌─────────────────┐ │
│ │ Tier Status │ │ Store Credit    │ │
│ │ 🥇 Gold     │ │ Balance: $45.50 │ │
│ │ ████████░░  │ │ [View History]  │ │
│ │ 80% to Plat │ │                 │ │
│ └─────────────┘ └─────────────────┘ │
├─────────────────────────────────────┤
│ Recent Orders                       │
│ ...                                 │
└─────────────────────────────────────┘
```

## New Customer Accounts

### Account UI Extension

RewardsPro provides a dedicated extension for Shopify's new customer accounts:

**Features:**
- Native look and feel
- Full rewards dashboard
- Transaction history
- Tier management

### Installation

The extension is automatically available when RewardsPro is installed. To enable:

1. Go to **Settings → Customer accounts** in Shopify admin
2. Ensure "New customer accounts" is enabled
3. RewardsPro appears automatically in account pages

### Extension Sections

| Section | Description |
|---------|-------------|
| **Profile Block** | Shows in main profile area |
| **Order Extension** | Adds cashback info to orders |
| **Full Page** | Dedicated rewards page |

## Displaying Tier Information

### Tier Badge

Show the customer's current tier:

```liquid
{% if customer %}
  <div class="loyalty-tier">
    <span class="tier-badge tier-{{ customer.metafields.rewardspro.tier }}">
      {{ customer.metafields.rewardspro.tier_name }}
    </span>
  </div>
{% endif %}
```

### Progress Indicator

Show progress to next tier:

| Element | Data |
|---------|------|
| Current spend | `$1,250` |
| Next tier threshold | `$2,500` |
| Progress | `50%` |
| Amount needed | `$1,250 more` |

### Tier Benefits

Display what the current tier offers:

- ✅ 5% cashback on all orders
- ✅ Early access to sales
- ✅ Free shipping over $50
- ✅ Birthday bonus credit

## Store Credit Display

### Balance Card

Prominent display of available credit:

```
┌─────────────────────────┐
│ 💰 Store Credit         │
│                         │
│    $45.50               │
│    Available Balance    │
│                         │
│ [Use at Checkout]       │
└─────────────────────────┘
```

### Transaction History

Show recent credit activity:

| Date | Description | Amount |
|------|-------------|--------|
| Nov 25 | Order #1234 cashback | +$7.50 |
| Nov 20 | Order #1233 cashback | +$12.00 |
| Nov 18 | Used at checkout | -$25.00 |
| Nov 15 | Welcome bonus | +$10.00 |

### Filtering Options

Let customers filter transactions:
- All transactions
- Credits earned
- Credits used
- Date range

## Order History Integration

### Cashback Per Order

Show cashback earned on each order:

```
Order #1234 - November 25, 2024
Total: $150.00
Status: Fulfilled
───────────────────────
🎁 Cashback Earned: $7.50 (5%)
```

### Order Detail Page

On individual order pages, show:
- Cashback amount earned
- Tier at time of purchase
- Credit used (if any)

## Headless / Custom Storefronts

### API Integration

For headless stores, use the API:

```javascript
// Fetch customer loyalty data
const response = await fetch('/apps/rewardspro/membership', {
  headers: {
    'Content-Type': 'application/json'
  }
});

const { customer } = await response.json();

// customer.tier - Current tier info
// customer.storeCredit - Balance and history
// customer.spending - Progress data
```

### Required Data

Ensure you pass customer authentication:
- Shopify customer ID
- Shop domain
- HMAC verification

## Testing Integration

### Test Scenarios

| Scenario | Expected Result |
|----------|-----------------|
| New customer | Default tier, $0 balance |
| Active customer | Current tier, real balance |
| Upgraded customer | New tier badge, updated rate |
| Guest visitor | Login prompt |

### Debug Mode

Enable debug mode to see:
- API responses
- Customer data being fetched
- Any integration errors

## Best Practices

### Placement

- **Above the fold** - Loyalty status visible without scrolling
- **Near orders** - Connect rewards to purchase behavior
- **Consistent location** - Same spot on all account pages

### Performance

- Cache tier data (updates on order)
- Lazy load transaction history
- Use skeleton loading states

### Accessibility

- Proper heading hierarchy
- ARIA labels on interactive elements
- Color contrast compliance
- Screen reader friendly
