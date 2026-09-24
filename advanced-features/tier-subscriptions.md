---
description: Understand and support existing recurring tier agreements
---

# Existing tier subscriptions

A subscription links a customer and tier to a Shopify contract. Read its status,
price, billing interval, period dates and provider history before acting.
This guide covers existing agreements; app plan offers are [retired](../billing/plans.md).

## Read the lifecycle

| Record or event | What to check |
|---|---|
| Contract | Customer, tier, provider reference and agreed terms |
| Successful renewal | Provider payment, covered period and recorded access |
| Pause or resume | Authorized request, provider status and next billing date |
| Cancellation | Provider confirmation, future billing and remaining paid access |
| Failed payment | Actual attempt and retry records; any agreed grace period |
| Refund | Provider adjustment and the corresponding membership history |

A local status change is not proof that the provider stopped billing or issued a
refund. Confirm the provider result and keep the audit trail. Do not invent a
retry schedule, require a retention offer or create a new charge to test support.

## Customer support

Customers should be able to inspect their agreement and billing history, update
a payment method where the provider supports it, and request cancellation.
Honor the agreement's remaining access and cancellation terms. Check webhook
history when provider and local records disagree.

Related: [tier products](tier-products.md), [webhooks](webhooks.md),
[membership lifecycle](../tier-products/membership-lifecycle.md).

The former setup, pricing and growth playbook is [retired history](../docs/history/retired-commercial-direction-2026-09-24/advanced-features__tier-subscriptions.md.txt).
