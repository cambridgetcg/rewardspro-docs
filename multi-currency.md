# Multi-Currency Support

RewardsPro supports stores selling in multiple currencies.

## Supported Currencies

RewardsPro supports 33 currencies including:

| Currency | Code | Symbol |
|----------|------|--------|
| US Dollar | USD | $ |
| Euro | EUR | € |
| British Pound | GBP | £ |
| Canadian Dollar | CAD | $ |
| Australian Dollar | AUD | $ |
| Japanese Yen | JPY | ¥ |
| Swiss Franc | CHF | CHF |

## Currency Configuration

### Store Currency

Set your primary currency in **Settings**:
1. Go to **Settings**
2. Select **Currency** dropdown
3. Choose your store's currency
4. Save changes

All store credit balances and thresholds use this currency.

### Display Format

Choose how currency is displayed:
- **Symbol prefix**: $100.00
- **Symbol suffix**: 100.00 USD
- **Locale-aware**: Automatically formats based on region

## Multi-Currency Stores

For stores using Shopify Markets with multiple currencies:

### Order Processing
- Orders are converted to store currency for cashback calculation
- Exchange rates are applied at time of order

### Customer Display
- Widget shows amounts in customer's local currency
- Balances stored in store currency, displayed in customer currency

## Exchange Rates

RewardsPro uses daily exchange rates from a reliable provider:
- Rates updated every 24 hours
- Historical rates preserved for audit
- Accurate to 4 decimal places
