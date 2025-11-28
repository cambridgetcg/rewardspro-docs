---
description: Shopify webhooks handled by RewardsPro
---

# Webhooks

RewardsPro uses Shopify webhooks to process events in real-time. All webhooks are automatically registered when you install the app.

---

## Order Webhooks

### orders/paid

**Trigger:** Order payment is confirmed

**Actions:**
1. Identify customer from order email
2. Calculate eligible amount (subtotal - discounts)
3. Apply customer's tier cashback rate
4. Create ledger entry (CASHBACK_EARNED)
5. Update customer balance
6. Update customer spending totals
7. Check for tier upgrade milestone

**Data Stored:**
- Order details (ID, amounts, dates)
- Cashback calculation data
- Tier at time of order
- Processing timestamp

### orders/create

**Trigger:** New order created in Shopify

**Actions:**
1. Track order for analytics
2. Associate with customer
3. Prepare for payment confirmation

**Note:** Cashback is NOT issued on create - only on paid status.

### orders/refunded

**Trigger:** Refund is processed

**Actions:**
1. Find original order
2. Calculate proportional clawback:
   - Full refund: 100% of original cashback reversed
   - Partial refund: (refund amount / order total) × original cashback
3. Create ledger entry (REFUND_CLAWBACK)
4. Update customer balance
5. Update customer netSpent

**Example:**
```
Original Order: $100, Cashback: $5.00
Refund: $40 (40% of order)
Clawback: $5.00 × 0.40 = $2.00
```

---

## Customer Webhooks

### customers/create

**Trigger:** New customer account created in Shopify

**Actions:**
1. Create customer record in RewardsPro
2. Assign default (base) tier
3. Initialize store credit at $0
4. Create tier change log (INITIAL_ASSIGNMENT)

### customers/update

**Trigger:** Customer details changed in Shopify

**Actions:**
1. Update email, name, tags
2. Sync other metadata
3. Maintain existing tier and balance

---

## Subscription Webhooks

### subscription_contracts/create

**Trigger:** New tier subscription created

**Actions:**
1. Create TierSubscription record
2. Link to customer
3. Set initial status (PENDING or ACTIVE)

### tier-subscription/billing

**Trigger:** Subscription billing attempt completed

**Actions:**
1. Update billing status
2. On success: Renew tier access
3. On failure: Track failed attempt count
4. Update nextBillingDate

### tier-subscription/cancelled

**Trigger:** Subscription cancelled

**Actions:**
1. Update subscription status to CANCELLED
2. Create tier change log (SUBSCRIPTION_CANCELLED)
3. Evaluate tier based on spending (may downgrade)

---

## App Webhooks

### app/uninstalled

**Trigger:** Store uninstalls RewardsPro

**Actions:**
1. Clean up webhook registrations
2. Mark shop as inactive
3. Preserve data per retention policy

### app/scopes_update

**Trigger:** App permissions changed

**Actions:**
1. Update stored scopes
2. Re-register webhooks if needed

### app_subscriptions/update

**Trigger:** RewardsPro plan subscription changes

**Actions:**
1. Update billing status
2. Enable/disable features based on plan
3. Update usage quotas

### subscriptions/approaching-cap

**Trigger:** Usage approaching plan limit

**Actions:**
1. Log warning
2. Notify merchant
3. Track for analytics

---

## Shop Webhooks

### shop/update

**Trigger:** Store settings changed in Shopify

**Actions:**
1. Sync store name, URL
2. Update currency if changed
3. Sync timezone

---

## Compliance Webhooks (GDPR)

### customers/data_request

**Trigger:** Customer requests their data (GDPR)

**Actions:**
1. Compile all customer data
2. Include orders, ledger entries, tier history
3. Prepare export file

### customers/redact

**Trigger:** Customer requests data deletion (GDPR)

**Actions:**
1. Anonymize personal information
2. Remove email, name
3. Preserve anonymized transaction history

### shop/redact

**Trigger:** 48 hours after app uninstall

**Actions:**
1. Delete all shop data
2. Remove customer records
3. Clear settings and configuration

---

## Webhook Security

### HMAC Verification

All webhooks are verified using HMAC-SHA256:

```
1. Extract X-Shopify-Hmac-SHA256 header
2. Calculate: HMAC-SHA256(raw_body, webhook_secret)
3. Compare using timing-safe method
4. Reject request if mismatch
```

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

- Webhook ID stored on first processing
- Duplicate webhooks skipped
- Prevents double-crediting cashback

---

## Webhook Endpoints

| Endpoint | Topic |
|----------|-------|
| `/webhooks/orders.paid` | orders/paid |
| `/webhooks/orders.create` | orders/create |
| `/webhooks/orders.refunded` | refunds/create |
| `/webhooks/customers.create` | customers/create |
| `/webhooks/customers.update` | customers/update |
| `/webhooks/tier-subscription.created` | subscription_contracts/create |
| `/webhooks/tier-subscription.billing` | subscription_billing_attempts/* |
| `/webhooks/tier-subscription.cancelled` | subscription_contracts/update |
| `/webhooks/app.uninstalled` | app/uninstalled |
| `/webhooks/app.scopes_update` | app/scopes_update |
| `/webhooks/app-subscriptions-update` | app_subscriptions/update |
| `/webhooks/shop.update` | shop/update |
| `/webhooks/compliance` | customers/data_request, customers/redact, shop/redact |

---

## Retry Behavior

Shopify retries failed webhooks:

| Attempt | Timing |
|---------|--------|
| 1st retry | 5 minutes |
| 2nd retry | 30 minutes |
| 3rd retry | 2 hours |
| 4th retry | 24 hours |

After all retries fail, webhook is dropped.

### Response Requirements

| Response Code | Meaning |
|---------------|---------|
| 2xx | Success, processed |
| 4xx | Rejected, no retry |
| 5xx | Error, will retry |

---

## Troubleshooting

### Webhooks Not Received

1. **Check app installation** - Ensure app is properly installed
2. **Verify webhook registration** - View in Shopify Admin > Settings > Notifications
3. **Check endpoint accessibility** - Ensure your app URL is reachable
4. **Review Shopify status** - Check for platform outages

### Cashback Not Issued

1. **Order status** - Must be "paid" not just "created"
2. **Customer exists** - Customer account required
3. **Tier assigned** - Customer must have a tier
4. **Processing errors** - Check app logs

### Duplicate Processing

1. **Idempotency check** - Should prevent duplicates
2. **Network timeouts** - Can cause retries
3. **Manual reconciliation** - May be needed in edge cases

---

## Related Guides

- [Cashback Logic](cashback-logic.md) - How cashback is calculated
- [Evaluation Periods](evaluation-periods.md) - Tier calculation timing
- [Data Models](data-models.md) - Data structure reference
