# API Integration

RewardsPro provides APIs for integrating with external systems and custom applications.

## Customer Widget API

The customer-facing widget retrieves data through a secure API endpoint.

### Endpoint

```
GET /apps/rewardspro/membership
```

### Authentication

Requests are authenticated using Shopify's app proxy HMAC verification. The widget automatically handles this when embedded in your storefront.

### Response

```json
{
  "customer": {
    "name": "John Smith",
    "email": "john@example.com",
    "tier": {
      "name": "Gold",
      "color": "#FFD700",
      "cashbackRate": 5
    },
    "storeCredit": {
      "balance": 45.50,
      "currency": "USD"
    },
    "spending": {
      "total": 1250.00,
      "period": "annual",
      "nextTierAt": 2500.00,
      "nextTierName": "Platinum"
    }
  }
}
```

## Localization API

Support multiple languages in the customer widget.

### Endpoint

```
GET /apps/rewardspro/locales/{locale}
```

### Supported Locales

- `en` - English (default)
- `fr` - French
- `es` - Spanish
- `de` - German

## Security

All API communications use:
- HTTPS encryption
- HMAC signature verification
- Shop-scoped data isolation

Never expose API credentials in client-side code.
