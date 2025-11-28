---
description: Modify existing tier settings and understand the impact on customers
---

# Editing Existing Tiers

{% hint style="info" %}
### When to Edit

* Updating spending thresholds for better segmentation
* Adjusting cashback rates based on profitability
* Changing tier names or branding (icon, color)
* Fine-tuning after analyzing program performance
{% endhint %}

---

## How to Edit a Tier

{% stepper %}
{% step %}
### Locate the Tier

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Screenshot 2025-11-18 at 19.49.09.png" alt=""><figcaption></figcaption></figure></div>

1. Go to **Membership Tiers** page
2. Find the tier you want to modify
3. Click the **Edit** button on that row
{% endstep %}

{% step %}
### Modify Settings

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Screenshot 2025-11-18 at 19.52.57.png" alt=""><figcaption></figcaption></figure></div>

**Editable Fields:**

| Field | Can Edit? | Impact |
|-------|-----------|--------|
| Tier Name | Yes | Updates display everywhere |
| Minimum Spend | Yes | May trigger tier recalculation |
| Cashback Rate | Yes | Applies to future orders only |
| Icon | Yes | Visual change only |
| Color | Yes | Visual change only |

Click **Save** when done.
{% endstep %}
{% endstepper %}

---

## Impact on Customers

### Cashback Rate Changes

| Change | Effect |
|--------|--------|
| **Increase rate** | Customers earn more on future orders |
| **Decrease rate** | Customers earn less on future orders |
| **Past orders** | Not affected - uses rate at time of order |

{% hint style="warning" %}
Cashback rates are locked at time of order. Changing a tier's rate only affects **future** orders, not historical ones.
{% endhint %}

### Threshold Changes

| Change | What Happens |
|--------|--------------|
| **Lower threshold** | More customers may qualify for this tier |
| **Raise threshold** | Some customers may no longer qualify |

**After threshold changes:**
1. Run tier recalculation to update assignments
2. Customers are reassigned based on their current spending
3. Tier change logs record all movements

### Best Practices

- **Review customer distribution** before changing thresholds
- **Communicate changes** to customers if rates decrease
- **Make changes during off-peak hours** to minimize confusion
- **Test with one tier first** before making program-wide changes

---

## Evaluation Period Changes

{% hint style="danger" %}
**Caution**: Changing evaluation period affects ALL customers and should rarely be done after launch.
{% endhint %}

| Change | Effect |
|--------|--------|
| Annual → Lifetime | All historical spending counts; customers may upgrade |
| Lifetime → Annual | Only last 12 months count; customers may downgrade |

**Recommendation**: Set your evaluation period before launching and avoid changing it. If you must change:

1. Export current tier distribution
2. Communicate the change to customers
3. Make the change during low-activity period
4. Monitor tier assignments closely afterward

---

## Audit Trail

All tier edits are logged:

- **What changed**: Field and new value
- **When**: Timestamp of edit
- **Who**: Admin who made the change

View the full history in **Analytics** > **Tier Changes**.

