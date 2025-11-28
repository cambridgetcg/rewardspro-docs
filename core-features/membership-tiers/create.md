---
description: >-
  Loyalty tiers are the foundation of your rewards program. They automatically
  segment customers based on spending and assign cashback percentages,
  encouraging repeat purchases and higher order values.
---

# Creating Membership Tiers

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Screenshot 2025-11-18 at 18.27.00.png" alt=""><figcaption></figcaption></figure></div>

### Key Features

* Automatic tier assignment based on customer spending
* Configurable cashback percentages per tier (0-100%)
* Annual or lifetime spending evaluation
* Custom icons and colors for branding
* Real-time tier progression tracking
* Complete audit trail of all tier changes

---

## Tier Settings Reference

| Setting | Description | Example |
|---------|-------------|---------|
| **Tier Name** | Customer-facing name | "Gold", "VIP", "Platinum" |
| **Minimum Spend** | Spending threshold to qualify | $500 |
| **Cashback Rate** | Percentage returned as store credit | 5% |
| **Evaluation Period** | Annual or Lifetime | Annual |
| **Icon** | Emoji or icon for display | ⭐, 💎, 👑 |
| **Color** | Hex color for tier badge | #FFD700 |

---

## Creating Loyalty Tiers

{% stepper %}
{% step %}
### Navigate to Membership Tiers

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Screenshot 2025-11-18 at 18.18.55.png" alt=""><figcaption></figcaption></figure></div>

1. Navigate to **Membership Tiers** in the main navigation
2. Click the **Add Tier** button (top right corner)
{% endstep %}

{% step %}
### Configure Core Settings

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Screenshot 2025-11-18 at 18.19.54.png" alt=""><figcaption></figcaption></figure></div>

#### **Tier Name**

* **Purpose**: Customer-facing name displayed in widgets, emails, and admin
* **Examples**: Bronze, Silver, Gold, Platinum, Diamond, VIP
* **Best Practice**: Use recognizable tier names that clearly indicate hierarchy

#### **Minimum Spend Threshold**

* **Purpose**: Spending amount required to reach this tier
* **Format**: Whole number in your store currency (e.g., 500 for $500)
* **Note**: Customers qualify when their spending equals or exceeds this amount
* **Tip**: Set your base tier to $0 so everyone starts earning

#### **Cashback Percentage**

* **Purpose**: Percentage of eligible order value returned as store credit
* **Range**: 0% to 100% (whole numbers)
* **Example**: 5% means a $100 eligible order earns $5 in store credit
* **Best Practice**: Increase percentages with higher tiers to incentivize progression

#### **Evaluation Period**

Choose how customer spending is calculated:

| Period | Behavior | Best For |
|--------|----------|----------|
| **Annual** | Resets every 12 months | Most stores, seasonal products |
| **Lifetime** | Never resets, accumulates forever | Big-ticket items, long relationships |

* **Annual**: Customer must maintain spending each year to keep tier
* **Lifetime**: Once qualified, customer stays at tier permanently
{% endstep %}

{% step %}
### Configure Display Settings (Optional)

Customize how the tier appears to customers:

#### **Icon**

* **Purpose**: Visual identifier shown in widgets and badges
* **Default**: ⭐ (star emoji)
* **Options**: Any emoji (⭐, 💎, 👑, 🏆, 🎖️)

#### **Color**

* **Purpose**: Badge and accent color for the tier
* **Default**: #FFD700 (gold)
* **Format**: Hex color code

**Common Color Schemes:**

| Tier | Suggested Color |
|------|-----------------|
| Bronze | #CD7F32 |
| Silver | #C0C0C0 |
| Gold | #FFD700 |
| Platinum | #E5E4E2 |
| Diamond | #B9F2FF |
{% endstep %}

{% step %}
### Save the Tier

1. Review all settings for accuracy
2. Click **Save** to create the tier
3. The tier immediately becomes active for tier calculations

**Result**: New tier appears in the Membership Tiers list and is available for customer assignment.
{% endstep %}
{% endstepper %}

---

## What Happens Next

After creating a tier:

1. **New customers** are assigned based on their spending when they place orders
2. **Existing customers** are evaluated during the next tier recalculation
3. **Tier badge** appears in the customer widget and admin panels
4. **Cashback rate** is applied to all future qualifying orders

{% hint style="info" %}
**Tip**: Create all your tiers before running an initial data sync. This ensures existing customers are assigned to the correct tier based on their historical spending.
{% endhint %}
