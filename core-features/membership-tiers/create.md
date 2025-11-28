---
description: >-
  Loyalty tiers are the foundation of your rewards program. They automatically
  segment customers based on spending and assign cashback percentages,
  encouraging repeat purchases and higher order values.
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
metaLinks:
  alternates:
    - https://app.gitbook.com/s/yE16Xb3IemPxJWydtPOj/basics/editor
---

# Creating Membership Tiers

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Screenshot 2025-11-18 at 18.27.00.png" alt=""><figcaption></figcaption></figure></div>

### Key Features

* Automatic tier assignment based on customer spending
* Configurable cashback percentages per tier
* Annual or lifetime spending evaluation
* Real-time tier progression tracking
* Complete audit trail of tier changes

***

## Creating Loyalty Tiers

{% stepper %}
{% step %}
### Creating Membership Tiers

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Screenshot 2025-11-18 at 18.18.55.png" alt=""><figcaption></figcaption></figure></div>

1. Navigate to **Membership Tiers** in the main navigation
2. Click the **Add Tier** button (top right corner)
{% endstep %}

{% step %}
### Configure Tier Settings

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Screenshot 2025-11-18 at 18.19.54.png" alt=""><figcaption></figcaption></figure></div>

#### **Tier Name**

* **Purpose**: Customer-facing name displayed throughout the app
* **Examples**: Bronze, Silver, Gold, Platinum, Diamond, VIP
* **Best Practice**: Use recognizable tier names that clearly indicate hierarchy

#### **Minimum Spend Threshold**

* **Purpose**: Spending amount required to reach this tier
* **Format**: Enter amount in your store currency (e.g., 500 for $500)
* **Note**: Customers qualify when their spending equals or exceeds this amount

#### **Cashback Percentage**

* **Purpose**: Percentage of order value returned as store credit
* **Range**: 0% to 100%
* **Example**: 5% means a $100 order earns $5 in store credit
* **Best Practice**: Increase percentages with higher tiers to incentivize progression

#### **Evaluation Period**

* **Annual**: Resets spending calculation every 12 months from first purchase
  * Use when: You want to encourage consistent annual spending
  * Example: Customer must spend $1,000 each year to maintain Gold tier
* **Lifetime**: Calculates total all-time spending
  * Use when: You want to reward long-term loyalty
  * Example: Once a customer spends $5,000 total, they're always Platinum
{% endstep %}

{% step %}
### Save the Tier

1. Review all settings for accuracy
2. Click **Save** to create the tier
3. The tier immediately becomes active for tier calculations

**Result**: New tier appears in the Loyalty Tiers list and is available for customer assignment.
{% endstep %}
{% endstepper %}
