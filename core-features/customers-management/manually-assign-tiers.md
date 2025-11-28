---
description: Override automatic tier assignment for VIP customers or special cases
---

# Manually Assign Tiers

While RewardsPro automatically assigns tiers based on spending, you can manually override tier assignments for VIP customers, business accounts, or special circumstances.

## When to Use Manual Assignment

| Scenario | Example |
|----------|---------|
| **VIP Onboarding** | New high-value customer gets Platinum immediately |
| **Business Accounts** | B2B customers get special tier rates |
| **Promotional Upgrades** | Contest winners get temporary upgrade |
| **Customer Recovery** | Goodwill upgrade for service issues |
| **Migration** | Moving from another loyalty program |

## Assignment Process

{% stepper %}
{% step %}
### Find the Customer

<figure><img src="../.gitbook/assets/Find Customer.png" alt="Customers page with search and filter options"><figcaption>Use search or filters to locate the customer</figcaption></figure>

**Options to find customers:**
- **Search**: Enter name or email
- **Filter by tier**: Show specific tier members
- **Browse**: Use pagination to scroll through list

{% endstep %}

{% step %}
### Assign the New Tier

<figure><img src="../.gitbook/assets/Assign Tier.png" alt="Tier assignment modal with dropdown and options"><figcaption>Select the new tier and configure options</figcaption></figure>

**Configuration options:**

| Field | Description |
|-------|-------------|
| **New Tier** | Select tier from dropdown |
| **Permanent Override** | Prevent automatic changes |
| **Reason** | Required note for audit trail |

**Permanent Override explained:**
- ✅ **Enabled**: Customer stays in this tier regardless of spending
- ❌ **Disabled**: Customer can still be upgraded/downgraded by system

{% endstep %}

{% step %}
### Verify & Notify

After assignment:
- ✅ Success toast confirms the change
- ✅ Tier badge updates immediately
- ✅ Change logged in Tier Changes tab
- 📧 (Optional) Send customer notification

**Verify the change:**
1. Check the customer's tier badge updated
2. Review Tier Changes tab for audit entry
3. Confirm cashback rate is correct

{% endstep %}
{% endstepper %}

## Override Options

### Permanent Override

When enabled:
- Customer **will not** be automatically upgraded or downgraded
- Only manual changes can modify their tier
- Useful for: VIP agreements, business accounts

When disabled:
- System can still upgrade customer if they meet higher tier threshold
- System can downgrade if using annual evaluation and spend drops
- Useful for: Temporary promotions, one-time goodwill

### Reason Notes

Always provide a reason:
- Required for audit trail
- Helps other admins understand the change
- Useful for dispute resolution

**Good examples:**
- "VIP customer agreement - 12 month Platinum access"
- "Service recovery - upgraded per manager approval"
- "B2B partner account - Gold tier per contract"

**Poor examples:**
- "Changed" (no context)
- "Test" (looks unprofessional in audit)

## Bulk Tier Assignment

For multiple customers:

1. Go to **Customers** page
2. Select multiple customers (checkboxes)
3. Click **Bulk Actions** → **Assign Tier**
4. Select tier and enter reason
5. Confirm

**Use cases:**
- Migrating customers from another program
- Promotional tier upgrades for a group
- Correcting batch assignment errors

## Best Practices

### Do's ✅

- Always include a meaningful reason
- Use permanent override for contracted agreements
- Notify customers of their new status
- Review manual assignments periodically

### Don'ts ❌

- Override without documentation
- Forget to verify the change
- Use for testing (use test customers instead)
- Override then forget to review later

## Impact of Manual Assignment

### Immediate Effects

| Effect | Timing |
|--------|--------|
| New cashback rate | Immediate |
| Widget update | Next page load |
| Tier badge | Immediate |

### Historical Data

- Past cashback is **not** recalculated
- Previous tier history is **preserved**
- Change is **logged** with timestamp

## Removing Overrides

To restore automatic tier management:

1. Open customer details
2. Click **Change Tier**
3. Select appropriate tier based on their spending
4. **Disable** Permanent Override
5. Add reason: "Returning to automatic tier management"
6. Save

The customer will now be subject to automatic tier calculations again.
