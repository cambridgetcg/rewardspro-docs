---
description: Safely remove unused tiers from your loyalty program
---

# Deleting Tiers

{% hint style="warning" %}
**Important**: You can only delete tiers that have **0 customers** assigned. If customers are currently in the tier, you must reassign them first.
{% endhint %}

---

## Before Deleting

### Pre-Deletion Checklist

- [ ] **Check customer count**: Tier must show "0 customers"
- [ ] **Reassign customers**: Move any assigned customers to another tier
- [ ] **Review analytics**: Check if this tier has historical value
- [ ] **Export data**: Download tier performance data if needed for records

### Why You Might Delete a Tier

| Reason | Recommendation |
|--------|----------------|
| Consolidating tiers | Merge into fewer, simpler tiers |
| Restructuring program | Part of a planned redesign |
| Unused tier | Never used or no longer relevant |
| Testing tier | Created for testing, now cleanup |

---

## Delete Workflow

{% stepper %}
{% step %}
### Verify No Customers Assigned

1. Go to **Membership Tiers** page
2. Check the **Customers** column for the tier
3. Ensure it shows **0 customers**

If customers are assigned, see [Reassigning Customers](#reassigning-customers-first) below.
{% endstep %}

{% step %}
### Click Delete

1. Find the tier row
2. Click the **Delete** button (trash icon)
{% endstep %}

{% step %}
### Confirm Deletion

1. Review the confirmation modal
2. Verify you're deleting the correct tier
3. Click **Delete** to confirm

**This action cannot be undone.**
{% endstep %}
{% endstepper %}

---

## Reassigning Customers First

If the tier has customers, you must move them before deletion:

### Option 1: Bulk Reassign

1. Go to **Customers** page
2. Filter by the tier you want to delete
3. Select all customers (checkbox)
4. Choose **Bulk Actions** > **Assign Tier**
5. Select the new tier
6. Confirm

### Option 2: Individual Reassign

1. Open each customer's profile
2. Click **Change Tier**
3. Select the new tier
4. Save

### Option 3: Run Tier Recalculation

If you've already adjusted thresholds on other tiers:

1. Go to **Settings** > **Tier Automation**
2. Click **Recalculate All Tiers**
3. Customers will be automatically reassigned based on spending

---

## What Happens After Deletion

| Item | What Happens |
|------|--------------|
| **Tier record** | Permanently deleted |
| **Historical references** | Preserved in order history (tier name at order time) |
| **Tier change logs** | Historical logs retained with tier name |
| **Analytics** | Historical data preserved |

{% hint style="info" %}
**Note**: Deleting a tier doesn't affect historical records. Orders that were placed when customers were in that tier still show the tier name at time of order.
{% endhint %}

---

## Can't Delete a Tier?

### "Tier has customers assigned"

**Solution**: Reassign all customers to another tier first.

### "This is the only tier"

**Solution**: Create at least one other tier before deleting. Your program needs at least one tier for the base level.

### "Tier has active subscriptions"

**Solution**: Cancel or migrate subscriptions before deleting (if using tier subscriptions).
