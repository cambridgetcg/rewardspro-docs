---
description: Configure your store's basic information, currency, and timezone
---

# Store Settings

Configure your store's fundamental settings including currency display, timezone, and basic information.

## Accessing Store Settings

1. Go to **Settings** in the main navigation
2. Select the **Store Information** or **Currency** tab

---

## Store Information

### Store Name

Your store's display name used throughout RewardsPro.

| Field | Details |
|-------|---------|
| **Max Length** | 100 characters |
| **Used For** | Dashboard display, reports |
| **Required** | No (defaults to Shopify store name) |

### Store URL

Your store's public website URL.

| Field | Details |
|-------|---------|
| **Format** | Must be a valid URL (e.g., `https://mystore.com`) |
| **Used For** | Widget links, email templates |
| **Required** | No |

### Shop Domain

Your Shopify domain (e.g., `mystore.myshopify.com`).

{% hint style="info" %}
This field is **read-only** and automatically synced from Shopify.
{% endhint %}

---

## Currency Settings

### Store Currency

The primary currency for displaying store credit and cashback amounts.

**Supported Currencies (32 total):**

| Region | Currencies |
|--------|------------|
| **North America** | USD, CAD, MXN |
| **Europe** | EUR, GBP, CHF, SEK, NOK, DKK, PLN, HUF, CZK, RON |
| **Asia Pacific** | JPY, CNY, SGD, HKD, KRW, INR, THB, IDR, PHP, MYR |
| **Other** | AUD, NZD, RUB, BRL, ZAR, AED, TRY, ILS, CLP |

### Currency Display Format

Choose how currency amounts are displayed:

| Format | Example | Best For |
|--------|---------|----------|
| **Symbol** | $100.00 | Most stores, cleaner look |
| **Code** | USD 100.00 | International stores, clarity |

**Examples by currency:**

```
Symbol Format:
  USD: $100.00
  EUR: €100.00
  GBP: £100.00
  JPY: ¥10,000

Code Format:
  USD: USD 100.00
  EUR: EUR 100.00
  GBP: GBP 100.00
  JPY: JPY 10,000
```

{% hint style="warning" %}
**Important**: Currency setting affects display only. Actual cashback is calculated in your Shopify store's currency and converted if needed.
{% endhint %}

---

## Timezone Settings

Your store's timezone is automatically synced from Shopify and cannot be changed in RewardsPro.

### What Timezone Affects

| Feature | Impact |
|---------|--------|
| **Tier Evaluations** | When annual periods reset |
| **Analytics** | Daily/weekly/monthly groupings |
| **Reports** | Timestamp display |
| **Scheduled Tasks** | When automated processes run |

### Viewing Your Timezone

1. Go to **Settings** → **Store Information**
2. Timezone is displayed in the store details section

{% hint style="info" %}
To change your timezone, update it in **Shopify Admin** → **Settings** → **General**. RewardsPro will sync automatically.
{% endhint %}

---

## Best Practices

### Currency Selection

- **Match your Shopify currency** for consistent customer experience
- **Choose symbol format** unless you serve multiple currency regions
- **Consider your customers** - use familiar currency symbols

### After Changing Settings

1. Settings apply immediately to new transactions
2. Existing balances display in the new format
3. Historical data is preserved and re-formatted

---

## Troubleshooting

### Currency Not Updating

1. Refresh the Settings page
2. Clear browser cache
3. Log out and back into the app

### Wrong Timezone

1. Check your Shopify store settings
2. Wait up to 1 hour for sync
3. Contact support if issue persists

### Store Name Not Showing

1. Enter a custom store name in Settings
2. Or let it default to your Shopify store name
