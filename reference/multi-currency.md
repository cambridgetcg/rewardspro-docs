---
description: Multi-currency support in RewardsPro
---

# Multi-Currency Support

RewardsPro supports 33 currencies for global stores.

## Supported Currencies

| Currency | Code | Symbol |
|----------|------|--------|
| US Dollar | USD | $ |
| Euro | EUR | € |
| British Pound | GBP | £ |
| Canadian Dollar | CAD | C$ |
| Australian Dollar | AUD | A$ |
| Japanese Yen | JPY | ¥ |
| Swiss Franc | CHF | CHF |
| Chinese Yuan | CNY | ¥ |
| Hong Kong Dollar | HKD | HK$ |
| Singapore Dollar | SGD | S$ |
| And 23 more... | | |

## How Currency Works

### Store Currency

Your primary currency for:
- Tier thresholds
- Store credit balances
- Internal calculations
- Reports and analytics

### Customer Currency

For multi-currency stores:
- Orders in customer's currency
- Converted for calculation
- Display in local currency

## Exchange Rates

### Rate Source

RewardsPro uses reliable exchange rate providers:
- Updated every 24 hours
- Historical rates preserved
- Accurate to 4 decimal places

### Conversion Example

```
Order: €100.00 EUR
Exchange rate: 1 EUR = 1.10 USD
Converted: $110.00 USD

Customer tier: Gold (5%)
Cashback: $5.50 USD
```

## Configuration

### Setting Store Currency

1. Go to **Settings**
2. Select **Currency**
3. Choose from dropdown
4. Save changes

> **Note:** Changing currency doesn't convert existing balances.

### Display Format

Options:
- Symbol prefix: $100.00
- Symbol suffix: 100.00 USD
- Auto format: Based on locale

## Tier Thresholds

All thresholds are in store currency:

| Tier | Threshold (USD) |
|------|-----------------|
| Bronze | $0 |
| Silver | $500 |
| Gold | $1,000 |
| Platinum | $2,500 |

Customer spending is converted to store currency for comparison.

## Best Practices

### Setting Thresholds

Consider purchasing power:
- $500 USD ≈ €455 EUR ≈ £400 GBP
- Adjust thresholds for your market
- Review as rates change

### Customer Communication

- Always show currency symbol
- Be clear about which currency
- Explain conversion if asked
