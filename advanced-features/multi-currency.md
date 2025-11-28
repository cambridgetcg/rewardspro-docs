---
description: Handle multiple currencies in your loyalty program
---

# Multi-Currency Support

RewardsPro supports 33 currencies with automatic exchange rate management, allowing international stores to operate seamlessly.

---

## Supported Currencies

| Code | Currency | Symbol |
|------|----------|--------|
| USD | US Dollar | $ |
| EUR | Euro | € |
| GBP | British Pound | £ |
| CAD | Canadian Dollar | C$ |
| AUD | Australian Dollar | A$ |
| JPY | Japanese Yen | ¥ |
| CNY | Chinese Yuan | ¥ |
| INR | Indian Rupee | ₹ |
| BRL | Brazilian Real | R$ |
| MXN | Mexican Peso | MX$ |
| KRW | South Korean Won | ₩ |
| SGD | Singapore Dollar | S$ |
| HKD | Hong Kong Dollar | HK$ |
| NZD | New Zealand Dollar | NZ$ |
| SEK | Swedish Krona | kr |
| NOK | Norwegian Krone | kr |
| DKK | Danish Krone | kr |
| CHF | Swiss Franc | CHF |
| PLN | Polish Zloty | zł |
| CZK | Czech Koruna | Kč |
| ZAR | South African Rand | R |
| RUB | Russian Ruble | ₽ |
| TRY | Turkish Lira | ₺ |
| ILS | Israeli Shekel | ₪ |
| AED | UAE Dirham | د.إ |
| SAR | Saudi Riyal | ر.س |
| MYR | Malaysian Ringgit | RM |
| THB | Thai Baht | ฿ |
| IDR | Indonesian Rupiah | Rp |
| PHP | Philippine Peso | ₱ |
| VND | Vietnamese Dong | ₫ |
| TWD | Taiwan Dollar | NT$ |
| PKR | Pakistani Rupee | Rs |

---

## How Currency Works

### Store Base Currency

Your store's base currency is set in Shopify:

1. Used for all internal calculations
2. Store credit stored in base currency
3. Tier thresholds in base currency
4. Analytics reported in base currency

### Order Currency

When an order is placed:

1. Order total captured in customer's currency
2. Converted to base currency for storage
3. Cashback calculated in base currency
4. Store credit issued in base currency

### Display Currency

Customer-facing elements:

1. Widget shows balance in store currency
2. Checkout applies credit in store currency
3. Order history shows original currency

---

## Exchange Rates

### Automatic Updates

Exchange rates are updated daily:

| Setting | Value |
|---------|-------|
| **Provider** | ExchangeRate-API |
| **Frequency** | Daily at midnight UTC |
| **Fallback** | Cached rates if API unavailable |

### Exchange Rate Data

| Field | Description |
|-------|-------------|
| `baseCurrency` | Source currency (usually USD) |
| `targetCurrency` | Destination currency |
| `rate` | Exchange rate |
| `fetchedAt` | When rate was retrieved |
| `provider` | Data source |

### Manual Override

To set custom rates:

1. Go to **Settings** > **Currency**
2. Click **Exchange Rates**
3. Edit specific rates
4. Save changes

{% hint style="warning" %}
Manual rates won't auto-update. Use sparingly.
{% endhint %}

---

## Configuration

### Setting Store Currency

1. In Shopify: **Settings** > **Store details** > **Store currency**
2. RewardsPro syncs automatically
3. Verify in **Settings** > **General**

### Currency Display Options

| Setting | Options | Description |
|---------|---------|-------------|
| **Format** | Symbol / Code | Show "$" or "USD" |
| **Position** | Before / After | "$10" or "10 USD" |
| **Decimal Places** | 0-4 | Precision level |
| **Thousands Separator** | , . space | 1,000 or 1.000 |

### Rounding Rules

| Currency | Decimals | Example |
|----------|----------|---------|
| USD, EUR, GBP | 2 | $10.50 |
| JPY, KRW | 0 | ¥1050 |
| KWD, BHD | 3 | 10.500 KWD |

---

## Multi-Currency Orders

### Conversion Example

**Scenario:** Store base = USD, Customer pays in EUR

```
Order total: €85.00
Exchange rate: 1 EUR = 1.08 USD
Converted total: $91.80 USD
Customer tier: Gold (5% cashback)
Cashback: $4.59 USD
```

### Tier Threshold Evaluation

Thresholds are always in base currency:

```
Tier: Gold = $1,000 minimum
Customer's EUR spending = €850
Converted to USD = $918
Result: Not yet Gold tier
```

---

## Store Credit in Multi-Currency

### Balance Storage

- Store credit always stored in **base currency**
- Displayed to customer in **base currency**
- Applied at checkout in **order currency**

### Checkout Application

When customer uses store credit:

1. Balance checked (base currency)
2. Converted to order currency at current rate
3. Applied to order total
4. Remaining balance updated

### Example

```
Store credit balance: $50.00 USD
Order currency: GBP
Exchange rate: 1 USD = 0.79 GBP
Available to apply: £39.50 GBP
```

---

## Reporting

### Analytics Currency

All analytics displayed in store base currency:

- Total revenue
- Cashback issued
- Store credit outstanding
- Customer spending totals

### Export Options

When exporting data:

| Option | Description |
|--------|-------------|
| **Base Currency** | All values in store currency |
| **Original Currency** | Values in transaction currency |
| **Both** | Both columns included |

---

## Common Scenarios

### Scenario 1: US Store, International Customers

- Base currency: USD
- Customer pays in EUR
- Order converted to USD for storage
- Cashback calculated in USD
- Credit balance in USD

### Scenario 2: Multi-Region Store

- Base currency: USD
- Sell in USD, EUR, GBP
- All orders converted to USD
- Single credit balance per customer
- Thresholds in USD

### Scenario 3: Non-USD Base Currency

- Base currency: GBP
- Exchange rates fetched vs GBP
- All calculations in GBP
- Display in GBP

---

## Troubleshooting

### Wrong Currency Displayed

**Check:**
1. Store currency in Shopify settings
2. RewardsPro synced correctly
3. Browser locale not overriding

**Solution:**
1. Verify Shopify settings
2. Re-sync shop settings
3. Clear cache

### Exchange Rate Issues

**Check:**
1. Rates updating daily
2. No API errors in logs
3. Fallback rates available

**Solution:**
1. Check exchange rate logs
2. Manually update if needed
3. Verify API key

### Credit Balance Mismatch

**Check:**
1. Conversion rates at time of transaction
2. Rounding differences
3. Multiple currency transactions

**Solution:**
1. Review ledger entries
2. Check conversion rates used
3. Minor differences may be rounding

---

## Best Practices

### Consistent Communication

- Always mention currency in customer communications
- Use "USD" not just "$" for clarity
- Show conversion on receipts

### Threshold Planning

- Set thresholds in base currency
- Consider purchasing power parity
- May need region-specific programs for fairness

### Exchange Rate Awareness

- Monitor significant currency fluctuations
- Consider rate locks for promotions
- Review rates during major conversions

---

## Related Guides

- [Settings](../configuration/general-settings.md) - Currency configuration
- [Analytics](../core-features/analytics.md) - Multi-currency reporting
- [Cashback Rules](../core-features/orders-and-cashback/cashback-calculation-rules.md) - Calculation with currency
