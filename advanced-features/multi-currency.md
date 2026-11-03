---
description: Handle multiple currencies in your loyalty program
---

# Multi-Currency Support

RewardsPro supports 32 store currencies. It works in your store currency: for an order paid in another currency, it uses the amount Shopify records in your store currency.

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
| CHF | Swiss Franc | CHF |
| SEK | Swedish Krona | kr |
| NZD | New Zealand Dollar | NZ$ |
| NOK | Norwegian Krone | kr |
| MXN | Mexican Peso | MX$ |
| SGD | Singapore Dollar | S$ |
| HKD | Hong Kong Dollar | HK$ |
| KRW | South Korean Won | ₩ |
| TRY | Turkish Lira | ₺ |
| INR | Indian Rupee | ₹ |
| RUB | Russian Ruble | ₽ |
| BRL | Brazilian Real | R$ |
| ZAR | South African Rand | R |
| AED | UAE Dirham | د.إ |
| PLN | Polish Zloty | zł |
| DKK | Danish Krone | kr |
| THB | Thai Baht | ฿ |
| IDR | Indonesian Rupiah | Rp |
| HUF | Hungarian Forint | Ft |
| CZK | Czech Koruna | Kč |
| ILS | Israeli Shekel | ₪ |
| CLP | Chilean Peso | CLP$ |
| PHP | Philippine Peso | ₱ |
| RON | Romanian Leu | lei |
| MYR | Malaysian Ringgit | RM |

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
2. Shopify also records it in your base currency, and RewardsPro stores that amount
3. Cashback calculated in base currency
4. Store credit issued in base currency

### Display Currency

Customer-facing elements:

1. Widget shows balance in store currency
2. At checkout, Shopify shows only the store credit balance in the checkout's currency
3. Order history shows original currency

---

## Exchange Rates

RewardsPro doesn't apply exchange rates of its own to cashback, tiers or store credit. For an order paid in another currency, it uses the amount Shopify records in your store currency, converted at Shopify's rate. There are no exchange rate settings in RewardsPro.

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
Shopify's rate: 1 EUR = 1.08 USD
Shopify's amount in USD: $91.80
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

- RewardsPro issues store credit in your **base currency**
- Displayed to customer in **base currency**

### Checkout Application

Shopify shows a customer only the store credit balance that matches the currency of their checkout. A customer checking out in another currency won't see store credit issued in your store currency.

### Example

```
Store credit balance: $50.00 USD
Checkout currency: GBP
Store credit offered at checkout: none
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
- Orders in other currencies counted at Shopify's GBP amount
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

### Credit Balance Mismatch

**Check:**
1. Rounding differences
2. Multiple currency transactions
3. Whether the customer checked out in another currency, where Shopify doesn't show store credit issued in your store currency

**Solution:**
1. Review ledger entries
2. Compare with the customer's store credit in Shopify admin
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

### Checkout Currency

- Tell international customers which currency their store credit is in
- Customers who check out in another currency can't spend store credit issued in your store currency

---

## Related Guides

- [Store Settings](../configuration/store-settings.md) - Currency configuration
- [Analytics](../core-features/analytics.md) - Multi-currency reporting
- [Cashback Rules](../core-features/orders-and-cashback/cashback-calculation-rules.md) - Calculation with currency
