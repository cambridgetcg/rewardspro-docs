---
description: Shopify webhooks handled by RewardsPro
---

# Webhooks

RewardsPro uses Shopify webhooks to process events in real-time.

## Order Webhooks

### orders/paid

**Trigger:** Order payment is confirmed

**Actions:**
1. Identify customer
2. Calculate cashback
3. Credit account
4. Log transaction

**Required for:** Core cashback functionality

### orders/create

**Trigger:** New order created

**Actions:**
1. Track order for analytics
2. Prepare for payment confirmation

### orders/updated

**Trigger:** Order details change

**Actions:**
1. Check for refund status
2. Update analytics if needed

### orders/cancelled

**Trigger:** Order is cancelled

**Actions:**
1. Reverse cashback if awarded
2. Update order status

### refunds/create

**Trigger:** Refund is processed

**Actions:**
1. Calculate proportional reversal
2. Update customer balance
3. Log adjustment

## Customer Webhooks

### customers/create

**Trigger:** New customer account created

**Actions:**
1. Add to loyalty program
2. Assign default tier
3. Initialize balance at $0

### customers/update

**Trigger:** Customer details change

**Actions:**
1. Sync updated information
2. Update email/name

### customers/delete

**Trigger:** Customer is deleted

**Actions:**
1. Handle data cleanup
2. Maintain audit trail

## App Webhooks

### app/uninstalled

**Trigger:** Store uninstalls RewardsPro

**Actions:**
1. Clean up webhooks
2. Archive data (per policy)
3. Stop all processing

### app_subscriptions/update

**Trigger:** Billing status changes

**Actions:**
1. Update plan status
2. Enable/disable features

## Compliance Webhooks

### customers/data_request

**Trigger:** GDPR data request

**Actions:**
1. Compile customer data
2. Prepare export

### customers/redact

**Trigger:** GDPR deletion request

**Actions:**
1. Anonymize customer data
2. Remove PII

### shop/redact

**Trigger:** Store data deletion

**Actions:**
1. Remove all store data
2. Complete cleanup

## Webhook Security

### HMAC Verification

All webhooks are verified using HMAC:
1. Extract signature from header
2. Calculate expected signature
3. Compare using timing-safe method
4. Reject if mismatch

### Idempotency

Duplicate webhooks are handled:
- Unique identifier per event
- Skip if already processed
- Prevents double-crediting

## Troubleshooting

### Webhook Not Received

1. Check Shopify webhook settings
2. Verify app is installed
3. Check endpoint accessibility

### Processing Failed

1. Review error logs
2. Check customer exists
3. Verify calculation inputs
4. Process manually if needed
