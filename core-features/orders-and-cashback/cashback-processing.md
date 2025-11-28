---
description: Configure how cashback is calculated and awarded on customer orders
---

# Cashback Processing

RewardsPro offers two modes for processing cashback: **Automatic** and **Manual**. Choose the mode that fits your business needs.

## Processing Modes

| Mode | Description | Best For |
|------|-------------|----------|
| **Automatic** | Cashback awarded instantly when order is paid | Most stores, hands-off operation |
| **Manual** | Review and approve each order before awarding | High-value items, fraud-prone categories |

---

## Automatic Mode

Automatic cashback mode calculates and awards store credit instantly when an order is marked as paid.

{% stepper %}
{% step %}
### Enable Auto Processing

<figure><img src="../.gitbook/assets/Feature Manage On.png" alt="Feature Manager with Auto Processing enabled"><figcaption>Toggle Auto Processing ON in Feature Manager</figcaption></figure>

1. Go to **Dashboard** or **Settings**
2. Find **Feature Manager**
3. Enable **Auto Cashback Processing**

{% endstep %}

{% step %}
### Verify Loyalty Engine Status

<figure><img src="../.gitbook/assets/Loyalty Engine Status.png" alt="Loyalty Engine Status showing active processing"><figcaption>Check that the Loyalty Engine is actively processing</figcaption></figure>

The status indicator shows:
- 🟢 **Active**: Processing orders automatically
- 🟡 **Paused**: Temporarily stopped
- 🔴 **Error**: Check configuration

{% endstep %}

{% step %}
### Monitor Processed Orders

<figure><img src="../.gitbook/assets/Auto Processed Orders.png" alt="Orders list showing automatically processed cashback"><figcaption>Orders are processed and credited automatically</figcaption></figure>

Auto-processed orders show:
- ✅ Cashback amount awarded
- ✅ Customer balance updated
- ✅ Transaction in ledger

{% endstep %}
{% endstepper %}

### Automatic Processing Flow

```
Order Created → Payment Confirmed → Webhook Received → 
Cashback Calculated → Credit Issued → Customer Notified
```

**Timeline:**
| Step | Timing |
|------|--------|
| Order paid | T+0 |
| Webhook received | T+0 to 30s |
| Cashback calculated | < 1 second |
| Credit issued | Immediate |
| Customer sees balance | Real-time |

---

## Manual Mode

Manual cashback mode requires you to review and approve each order before store credit is issued.

{% stepper %}
{% step %}
### Enable Manual Mode

<figure><img src="../.gitbook/assets/Feature Manager.png" alt="Feature Manager with Manual mode"><figcaption>Toggle Auto Processing OFF for manual review</figcaption></figure>

1. Go to **Feature Manager**
2. Disable **Auto Cashback Processing**
3. Orders will now queue for review

{% endstep %}

{% step %}
### Review Pending Orders

<figure><img src="../.gitbook/assets/Manual Processing 1.png" alt="Pending orders awaiting cashback approval"><figcaption>Orders waiting for cashback approval</figcaption></figure>

Pending orders display:
- Order details and total
- Customer tier and rate
- Calculated cashback amount
- **Approve** or **Reject** buttons

{% endstep %}

{% step %}
### Approve and Issue Credit

<figure><img src="../.gitbook/assets/Manual Processing 2.png" alt="Cashback approval confirmation"><figcaption>Review and confirm the cashback amount</figcaption></figure>

Before approving:
1. Verify order is legitimate
2. Confirm customer identity
3. Check calculated amount
4. Click **Approve** to issue credit

{% endstep %}
{% endstepper %}

### When to Use Manual Mode

| Scenario | Why Manual |
|----------|------------|
| **High-value products** | Verify before large cashback |
| **Fraud-prone category** | Review suspicious orders |
| **New program launch** | Monitor initial transactions |
| **B2B orders** | May have special rates |
| **Custom calculations** | Need to adjust amounts |

---

## Switching Between Modes

### From Manual to Automatic

1. Process any pending orders first
2. Enable Auto Processing
3. New orders will process automatically

### From Automatic to Manual

1. Disable Auto Processing
2. New orders will queue for review
3. Already-processed orders are not affected

---

## Processing Indicators

### Order Status Badges

| Badge | Meaning |
|-------|---------|
| ✅ **Processed** | Cashback awarded |
| ⏳ **Pending** | Awaiting review (manual mode) |
| ⏸️ **Held** | Flagged for review |
| ❌ **Rejected** | Cashback denied |
| 🔄 **Reversed** | Cashback reversed (refund) |

### Dashboard Metrics

Monitor processing health:
- Orders processed today
- Total cashback issued
- Pending queue size (manual mode)
- Failed processing count

---

## Error Handling

### Common Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| **Not processing** | Auto mode disabled | Enable in Feature Manager |
| **Customer not found** | No account | Order processes when account created |
| **$0 cashback** | Excluded products | Check exclusion rules |
| **Delayed processing** | Webhook queue | Usually clears within minutes |

### Manual Intervention

If an order fails to process:
1. Go to **Orders** page
2. Find the order
3. Click **Process Cashback**
4. Confirm the calculated amount

---

## Best Practices

### For Automatic Mode

✅ **Do:**
- Monitor dashboard daily
- Set up error notifications
- Review large cashback amounts
- Audit transactions weekly

### For Manual Mode

✅ **Do:**
- Process orders promptly
- Set daily review schedule
- Document rejections
- Track approval times

### General

❌ **Don't:**
- Leave orders pending too long
- Ignore processing errors
- Skip fraud checks
- Forget to verify customer accounts
