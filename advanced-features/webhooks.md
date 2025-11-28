---
description: Understand webhook integrations and event handling
---

# Webhooks

RewardsPro uses Shopify webhooks to receive real-time updates about orders, customers, and subscriptions. This ensures your loyalty program stays in sync with your store.

---

## How Webhooks Work

```
Event occurs in Shopify (e.g., order paid)
        ↓
Shopify sends webhook to RewardsPro
        ↓
HMAC signature verified for security
        ↓
Webhook data processed
        ↓
Appropriate action taken (e.g., issue cashback)
        ↓
Response sent back to Shopify
```

---

## Registered Webhooks

RewardsPro automatically registers these webhooks when you install the app:

### Order Webhooks

| Webhook | Topic | Purpose |
|---------|-------|---------|
| **Order Paid** | `orders/paid` | Issue cashback when payment completes |
| **Order Created** | `orders/create` | Track new orders for analytics |
| **Order Refunded** | `orders/refunded` | Reverse cashback on refunds |

### Customer Webhooks

| Webhook | Topic | Purpose |
|---------|-------|---------|
| **Customer Created** | `customers/create` | Sync new customers |
| **Customer Updated** | `customers/update` | Keep customer data current |

### Subscription Webhooks

| Webhook | Topic | Purpose |
|---------|-------|---------|
| **Contract Created** | `subscription_contracts/create` | New tier subscription |
| **Contract Updated** | `subscription_contracts/update` | Status changes |
| **Billing Success** | `subscription_billing_attempts/success` | Payment completed |
| **Billing Failure** | `subscription_billing_attempts/failure` | Payment failed |

### App Lifecycle Webhooks

| Webhook | Topic | Purpose |
|---------|-------|---------|
| **App Uninstalled** | `app/uninstalled` | Clean up on uninstall |
| **Scopes Updated** | `app/scopes_update` | Permission changes |
| **Shop Updated** | `shop/update` | Sync shop settings |

### Compliance Webhooks

| Webhook | Topic | Purpose |
|---------|-------|---------|
| **Customers Data Request** | `customers/data_request` | GDPR data export |
| **Customers Redact** | `customers/redact` | GDPR deletion |
| **Shop Redact** | `shop/redact` | Shop data deletion |

---

## Webhook Processing

### Order Paid Webhook

When an order is marked as paid:

1. **Verify HMAC** signature
2. **Check idempotency** (prevent duplicates)
3. **Identify customer** from order
4. **Calculate cashback**:
   - Get customer's current tier
   - Apply tier's cashback percentage
   - Calculate: (subtotal - discounts) × rate
5. **Create ledger entry** (CASHBACK_EARNED)
6. **Update customer balance**
7. **Check tier upgrade** (if real-time enabled)
8. **Log webhook processing**

### Order Refunded Webhook

When a refund is issued:

1. **Verify HMAC** signature
2. **Find original order**
3. **Calculate clawback**:
   - Pro-rata based on refund amount
   - Use original cashback rate
4. **Create ledger entry** (REFUND_CLAWBACK)
5. **Update customer balance**
6. **Optionally issue refund credit**

### Customer Created Webhook

When a new customer is created:

1. **Verify HMAC** signature
2. **Create customer record** in RewardsPro
3. **Assign default tier** (usually base tier)
4. **Log initial assignment**

---

## Security

### HMAC Verification

Every webhook is verified using HMAC-SHA256:

```
HMAC = SHA256(webhook_body, SHOPIFY_WEBHOOK_SECRET)
```

The `X-Shopify-Hmac-SHA256` header must match.

### Headers Validated

| Header | Purpose |
|--------|---------|
| `X-Shopify-Hmac-SHA256` | Signature verification |
| `X-Shopify-Shop-Domain` | Identify source shop |
| `X-Shopify-Topic` | Webhook event type |
| `X-Shopify-Webhook-Id` | Unique webhook ID |
| `X-Shopify-API-Version` | API version used |

### Idempotency

Each webhook is tracked to prevent duplicate processing:

| Field | Purpose |
|-------|---------|
| `webhookId` | Unique Shopify webhook ID |
| `topic` | Webhook topic |
| `processedAt` | When processed |
| `status` | SUCCESS, FAILED, DUPLICATE |

---

## Webhook Endpoints

All webhook endpoints follow the pattern:

```
POST /webhooks/{topic}
```

### Endpoint List

| Endpoint | Topic |
|----------|-------|
| `/webhooks/orders.paid` | orders/paid |
| `/webhooks/orders.create` | orders/create |
| `/webhooks/orders.refunded` | orders/refunded |
| `/webhooks/customers.create` | customers/create |
| `/webhooks/customers.update` | customers/update |
| `/webhooks/subscription-contract.created` | subscription_contracts/create |
| `/webhooks/subscription-billing.success` | subscription_billing_attempts/success |
| `/webhooks/app.uninstalled` | app/uninstalled |
| `/webhooks/compliance` | customers/data_request, etc. |

---

## Monitoring Webhooks

### Webhook Status

View webhook health in **Settings** > **Webhooks**:

| Metric | Description |
|--------|-------------|
| **Registered** | Webhooks configured in Shopify |
| **Success Rate** | % of webhooks processed successfully |
| **Failed (24h)** | Recent failures |
| **Avg Processing Time** | Time to handle webhook |

### Webhook Logs

View recent webhook activity:

| Column | Description |
|--------|-------------|
| **Timestamp** | When received |
| **Topic** | Webhook type |
| **Status** | Success, Failed, Duplicate |
| **Duration** | Processing time (ms) |
| **Shop** | Source shop |

### Error Tracking

Failed webhooks are logged with:

- Error message
- Stack trace (if applicable)
- Webhook payload (sanitized)
- Retry count

---

## Error Handling

### Retry Logic

Shopify retries failed webhooks:

| Attempt | Timing |
|---------|--------|
| 1st retry | 5 minutes |
| 2nd retry | 30 minutes |
| 3rd retry | 2 hours |
| 4th retry | 24 hours |

After all retries fail, webhook is dropped.

### Dead Letter Queue

Permanently failed webhooks are stored:

| Field | Description |
|-------|-------------|
| `webhookId` | Original webhook ID |
| `payload` | Webhook data |
| `error` | Error message |
| `attempts` | Retry count |
| `createdAt` | First failure |

### Manual Reconciliation

For missed webhooks:

1. Go to **Settings** > **Webhooks**
2. Click **Reconcile**
3. Select date range
4. RewardsPro fetches missed events from Shopify API

---

## Common Issues

### Webhooks Not Received

**Symptoms:**
- Orders not showing in RewardsPro
- Cashback not being issued
- Customers not syncing

**Check:**
1. App is installed correctly
2. Webhooks registered (Settings > Webhooks)
3. Shop is active (not paused/closed)
4. No Shopify outage

**Solution:**
1. Re-register webhooks (Settings > Webhooks > Re-register)
2. Run manual sync for missed data
3. Contact support if persists

### Duplicate Processing

**Symptoms:**
- Double cashback issued
- Multiple ledger entries for same order

**Check:**
1. Idempotency check working
2. No app reinstallation issues
3. Network timeouts causing retries

**Solution:**
1. Usually handled automatically
2. Manual ledger adjustment if needed
3. Check webhook logs for duplicates

### Delayed Processing

**Symptoms:**
- Cashback takes hours to appear
- Tier upgrades delayed

**Check:**
1. Webhook queue not backed up
2. No server issues
3. Processing time within limits

**Solution:**
1. Usually resolves automatically
2. Check status page for incidents
3. Run reconciliation if needed

### HMAC Verification Failed

**Symptoms:**
- 401 Unauthorized responses
- Webhooks rejected

**Check:**
1. SHOPIFY_WEBHOOK_SECRET is correct
2. Secret matches Shopify Partners dashboard
3. No whitespace in secret

**Solution:**
1. Re-verify secret in environment variables
2. Regenerate secret if needed
3. Update and redeploy

---

## Webhook Reconciliation

### Automatic Reconciliation

Daily cron job checks for missed webhooks:

```
POST /api/cron/webhook-reconciliation
```

Compares:
- Orders in Shopify vs RewardsPro
- Customers in Shopify vs RewardsPro
- Flags discrepancies for review

### Manual Reconciliation

For specific date ranges:

1. Go to **Settings** > **Data Sync**
2. Select **Orders** or **Customers**
3. Choose date range
4. Click **Sync**
5. Missing items are imported

---

## Best Practices

### Monitoring

- Check webhook status weekly
- Set up alerts for high failure rates
- Review dead letter queue monthly

### Performance

- Webhooks processed in <5 seconds
- Heavy processing is backgrounded
- Timeout = 10 seconds (Shopify limit)

### Recovery

- Use reconciliation for missed events
- Don't rely solely on webhooks
- Periodic full sync recommended

---

## Technical Reference

### Webhook Registration

Webhooks are registered via Shopify GraphQL API:

```graphql
mutation webhookSubscriptionCreate(
  $topic: WebhookSubscriptionTopic!
  $webhookSubscription: WebhookSubscriptionInput!
) {
  webhookSubscriptionCreate(
    topic: $topic
    webhookSubscription: $webhookSubscription
  ) {
    webhookSubscription {
      id
      topic
      endpoint {
        ... on WebhookHttpEndpoint {
          callbackUrl
        }
      }
    }
    userErrors {
      field
      message
    }
  }
}
```

### Response Requirements

Webhooks must return within 5 seconds:

| Response | Meaning |
|----------|---------|
| 2xx | Success, processed |
| 4xx | Rejected, no retry |
| 5xx | Error, will retry |

---

## Related Guides

- [Order Sync](../core-features/orders-and-cashback/cashback-processing.md) - Order processing details
- [Customer Sync](../getting-started/initial-data-sync.md) - Syncing customers
- [Tier Subscriptions](tier-subscriptions.md) - Subscription webhooks
