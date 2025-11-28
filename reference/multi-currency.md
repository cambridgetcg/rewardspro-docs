---
description: Multi-currency support in RewardsPro
---

# Multi-Currency Support

RewardsPro supports 32 currencies for global stores, with automatic exchange rate management.

---

## Supported Currencies

### North America
| Code | Currency | Symbol |
|------|----------|--------|
| USD | US Dollar | $ |
| CAD | Canadian Dollar | C$ |
| MXN | Mexican Peso | MX$ |

### Europe
| Code | Currency | Symbol |
|------|----------|--------|
| EUR | Euro | € |
| GBP | British Pound | £ |
| CHF | Swiss Franc | CHF |
| SEK | Swedish Krona | kr |
| NOK | Norwegian Krone | kr |
| DKK | Danish Krone | kr |
| PLN | Polish Zloty | zł |
| HUF | Hungarian Forint | Ft |
| CZK | Czech Koruna | Kč |
| RON | Romanian Leu | lei |

### Asia Pacific
| Code | Currency | Symbol |
|------|----------|--------|
| JPY | Japanese Yen | ¥ |
| CNY | Chinese Yuan | ¥ |
| SGD | Singapore Dollar | S$ |
| HKD | Hong Kong Dollar | HK$ |
| KRW | South Korean Won | ₩ |
| INR | Indian Rupee | ₹ |
| THB | Thai Baht | ฿ |
| IDR | Indonesian Rupiah | Rp |
| PHP | Philippine Peso | ₱ |
| MYR | Malaysian Ringgit | RM |

### Other Regions
| Code | Currency | Symbol |
|------|----------|--------|
| AUD | Australian Dollar | A$ |
| NZD | New Zealand Dollar | NZ$ |
| RUB | Russian Ruble | ₽ |
| BRL | Brazilian Real | R$ |
| ZAR | South African Rand | R |
| AED | UAE Dirham | د.إ |
| TRY | Turkish Lira | ₺ |
| ILS | Israeli Shekel | ₪ |
| CLP | Chilean Peso | CLP$ |

---

## How Currency Works

### Store Currency

Your primary currency set in Shopify, used for:
- Tier thresholds (minSpend values)
- Store credit balances
- Internal calculations
- Reports and analytics

### Customer Currency

For multi-currency Shopify stores:
- Orders captured in customer's local currency
- Converted to store currency for storage
- Cashback calculated in store currency
- Credit balance always in store currency

---

## Exchange Rates

### Rate Source

RewardsPro uses ExchangeRate-API for reliable rates:
- Updated every 24 hours (midnight UTC)
- Accurate to 4 decimal places
- Historical rates preserved for audit

### Rate Storage

| Field | Description |
|-------|-------------|
| `baseCurrency` | Source currency (usually USD) |
| `targetCurrency` | Destination currency |
| `rate` | Exchange rate |
| `fetchedAt` | When rate was retrieved |
| `provider` | Data source |

### Conversion Example

```
Order: €100.00 EUR
Exchange rate: 1 EUR = 1.08 USD
Converted: $108.00 USD

Customer tier: Gold (5%)
Cashback: $5.40 USD (in store currency)
```

---

## Display Format

### Currency Display Type

Two display options:

| Type | Example | Best For |
|------|---------|----------|
| **SYMBOL** | $100.00 | Most stores, cleaner look |
| **CODE** | USD 100.00 | International, clearer |

### Decimal Handling

| Currency | Decimals | Example |
|----------|----------|---------|
| USD, EUR, GBP | 2 | $10.50 |
| JPY, KRW | 0 | ¥1050 |

---

## Tier Thresholds

All thresholds are in store currency:

```
Tier Configuration (USD store):
- Bronze: $0
- Silver: $500
- Gold: $1,000
- Platinum: $2,500

Customer paying in EUR:
- Spent: €850
- Converted: $918 USD
- Result: Qualifies for Silver, not Gold yet
```

---

## Configuration

### Setting Store Currency

1. Go to **Shopify Admin** → **Settings** → **Store details**
2. Set your store currency
3. RewardsPro syncs automatically

### Display Settings

In RewardsPro **Settings** → **Store Information**:
- View current currency
- Choose display format (Symbol or Code)

---

## Best Practices

### Setting Thresholds

Consider purchasing power parity:
- $500 USD ≈ €455 EUR ≈ £400 GBP
- High-cost regions may need adjusted programs
- Review thresholds as rates fluctuate

### Customer Communication

- Always show currency symbol or code
- Be clear about which currency balances are in
- Explain conversion when customers ask

### Exchange Rate Awareness

- Monitor significant currency fluctuations
- Rates update daily - large swings may affect tier status
- Consider rate locks for major promotions

---

## Troubleshooting

### Wrong Currency Displayed

1. Check store currency in Shopify settings
2. Verify RewardsPro sync is current
3. Clear browser cache
4. Check widget configuration

### Exchange Rate Issues

1. Rates update at midnight UTC
2. Check for API errors in logs
3. Manual rate override available if needed

### Balance Mismatch

1. Review conversion rates at time of transaction
2. Check for rounding differences
3. Minor discrepancies may be rounding

---

## Related Guides

- [Store Settings](../configuration/store-settings.md) - Currency configuration
- [Cashback Logic](cashback-logic.md) - Calculation with currency
- [Glossary](glossary.md) - Currency terms
