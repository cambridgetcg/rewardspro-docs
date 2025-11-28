---
description: API reference for RewardsPro integrations
---

# API Endpoints

RewardsPro provides APIs for widget and integration use.

## Widget API

### Get Customer Membership

Retrieves loyalty data for the current customer.

**Endpoint:** `GET /apps/rewardspro/membership`

**Authentication:** Shopify app proxy (HMAC)

**Response:**
```json
{
  "customer": {
    "id": "cust_123",
    "name": "John Smith",
    "email": "john@example.com",
    "tier": {
      "id": "tier_456",
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
      "nextTierName": "Platinum",
      "progress": 50
    }
  }
}
```

### Get Locales

Retrieves translation strings for the widget.

**Endpoint:** `GET /apps/rewardspro/locales/{locale}`

**Parameters:**
- `locale`: Language code (en, fr, es, de)

**Response:**
```json
{
  "widget": {
    "title": "Your Rewards",
    "balance": "Store Credit",
    "tier": "Your Tier",
    "progress": "Progress to {tier}",
    "earn": "Earn {rate}% cashback"
  }
}
```

## Internal APIs

These APIs are used internally by the app.

### Health Check

**Endpoint:** `GET /api/health`

**Response:**
```json
{
  "status": "healthy",
  "database": "connected",
  "timestamp": "2024-01-15T10:30:00Z"
}
```

## Rate Limits

| Endpoint | Limit |
|----------|-------|
| Widget API | 100/minute |
| Locales API | 60/minute |

## Error Responses

### 401 Unauthorized

```json
{
  "error": "Unauthorized",
  "message": "Invalid or missing authentication"
}
```

### 404 Not Found

```json
{
  "error": "Not Found",
  "message": "Customer not found"
}
```

### 500 Server Error

```json
{
  "error": "Internal Server Error",
  "message": "An unexpected error occurred"
}
```

## Security

All API requests require:
- HTTPS connection
- Valid HMAC signature (app proxy)
- Shop domain validation

Never expose API credentials in client-side code.
