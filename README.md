---
description: The complete loyalty and rewards platform for Shopify stores
layout:
  width: wide
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
---

# RewardsPro Documentation

Welcome to RewardsPro – the comprehensive loyalty and rewards platform that turns one-time buyers into lifelong customers.

## What is RewardsPro?

RewardsPro is a Shopify app that helps merchants build customer loyalty through:

| Feature | Description |
|---------|-------------|
| **Tier-Based Rewards** | Create Bronze, Silver, Gold, and Platinum tiers with increasing benefits |
| **Automatic Cashback** | Reward customers with store credit on every purchase |
| **Store Credit System** | Full control over customer balances with audit trails |
| **Customer Portal** | Beautiful widget showing customers their tier status and rewards |
| **Membership Products** | Sell direct tier access as purchasable products |

---

## Quick Start

<table data-view="cards">
<thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead>
<tbody>
<tr>
<td><strong>🚀 Installation</strong></td>
<td>Get RewardsPro installed and configured in under 10 minutes</td>
<td><a href="getting-started/installation.md">Installation Guide</a></td>
</tr>
<tr>
<td><strong>✅ Setup Checklist</strong></td>
<td>Step-by-step checklist to launch your loyalty program</td>
<td><a href="getting-started/quickstart-checklist.md">Quickstart Checklist</a></td>
</tr>
<tr>
<td><strong>🎯 Create Your First Tier</strong></td>
<td>Design your tier structure and set cashback rates</td>
<td><a href="getting-started/first-tier.md">Create First Tier</a></td>
</tr>
</tbody>
</table>

---

## Core Features

### Loyalty Tiers

Create a tiered loyalty program that rewards customers based on their spending.

| Tier | Spend Threshold | Cashback Rate | Benefits |
|------|-----------------|---------------|----------|
| Bronze | $0+ | 2% | Basic rewards |
| Silver | $500+ | 3% | Enhanced rewards |
| Gold | $1,000+ | 5% | Premium rewards |
| Platinum | $2,500+ | 7% | VIP rewards |

**Key Capabilities:**
- Unlimited custom tiers
- Flexible cashback rates (0-100%)
- Annual or lifetime evaluation periods
- Automatic tier progression
- Manual tier assignment for VIPs

📖 [Learn more about Tiers](core-features/membership-tiers.md)

---

### Customer Management

View and manage all your loyalty program members in one place.

**Features:**
- 📋 Customer list with search and filters
- 👤 Detailed customer profiles
- 💰 Store credit balance management
- 📊 Spending history and analytics
- 🔄 Sync customers from Shopify
- 🏷️ Tier assignment and changes

📖 [Learn more about Customer Management](core-features/customers.md)

---

### Orders & Cashback

Automatically process cashback when customers make purchases.

**How it works:**
1. Customer places an order
2. Order is paid → webhook triggers
3. Cashback calculated based on tier rate
4. Store credit added to customer balance
5. Customer notified via widget

**Supported scenarios:**
- ✅ Full order cashback
- ✅ Partial refund handling
- ✅ Multi-currency orders
- ✅ Discount code compatibility

📖 [Learn more about Orders & Cashback](core-features/orders-cashback.md)

---

### Store Credit

A complete store credit system with double-entry ledger and full audit trail.

**Credit Sources:**
| Source | Description |
|--------|-------------|
| Cashback | Automatically earned on purchases |
| Manual Credit | Added by merchant for goodwill |
| Refund to Credit | Convert refunds to store credit |
| Promotional | Campaign bonuses and rewards |

**Features:**
- Real-time balance updates
- Complete transaction history
- Bulk credit adjustments
- Export for accounting

📖 [Learn more about Store Credit](core-features/store-credit.md)

---

### Analytics Dashboard

Track the performance of your loyalty program with comprehensive analytics.

**Metrics Available:**
- 📈 Total members and growth rate
- 💵 Cashback issued and redeemed
- 🎯 Tier distribution breakdown
- 📊 Customer lifetime value
- 🔄 Redemption rates
- 📅 Trend analysis over time

📖 [Learn more about Analytics](core-features/analytics.md)

---

## Advanced Features

<table data-view="cards" data-card-size="large">
<thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead>
<tbody>
<tr>
<td><strong>🎫 Tier Products</strong></td>
<td>Sell membership access directly. Create purchasable products that grant instant tier upgrades for a set duration.</td>
<td><a href="advanced/tier-products/">Tier Products</a></td>
</tr>
<tr>
<td><strong>⚡ Automation</strong></td>
<td>Automatic cashback processing, tier progression, and scheduled tasks. Set it and forget it.</td>
<td><a href="advanced/automation/">Automation</a></td>
</tr>
<tr>
<td><strong>🖥️ Customer Portal</strong></td>
<td>Beautiful storefront widget showing tier status, store credit, and progress to next tier.</td>
<td><a href="advanced/customer-portal/">Customer Portal</a></td>
</tr>
<tr>
<td><strong>🔄 Subscriptions</strong></td>
<td>Set up recurring membership billing for predictable revenue and ongoing customer engagement.</td>
<td><a href="advanced/subscriptions.md">Subscriptions</a></td>
</tr>
</tbody>
</table>

---

## Configuration

### Store Settings

Configure RewardsPro for your store:

| Setting | Description |
|---------|-------------|
| **Currency** | Display currency for balances (33 supported) |
| **Timezone** | For reporting and analytics |
| **Evaluation Period** | Annual or lifetime tier calculation |
| **Default Tier** | Tier assigned to new customers |

📖 [Store Settings Guide](configuration/store-settings.md)

---

### Cashback Settings

Fine-tune how cashback is calculated:

| Option | Description |
|--------|-------------|
| **Include Shipping** | Whether shipping costs earn cashback |
| **Include Tax** | Whether taxes earn cashback |
| **Minimum Order** | Minimum order value for cashback |
| **Excluded Products** | Products that don't earn cashback |

📖 [Cashback Configuration](configuration/cashback-settings.md)

---

### Widget Settings

Customize the customer-facing widget:

- Position (bottom-right, bottom-left, custom)
- Colors (match your brand)
- Content (which sections to show)
- Language (EN, FR, ES, DE)

📖 [Widget Configuration](configuration/widget-settings.md)

---

## Technical Reference

<table data-view="cards">
<thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead>
<tbody>
<tr>
<td><strong>📐 Evaluation Periods</strong></td>
<td>Annual vs. lifetime tier calculation explained</td>
<td><a href="reference/evaluation-periods.md">Evaluation Periods</a></td>
</tr>
<tr>
<td><strong>🧮 Cashback Logic</strong></td>
<td>Detailed breakdown of cashback calculations</td>
<td><a href="reference/cashback-logic.md">Cashback Logic</a></td>
</tr>
<tr>
<td><strong>🔗 Webhooks</strong></td>
<td>Shopify webhooks handled by RewardsPro</td>
<td><a href="reference/webhooks.md">Webhooks</a></td>
</tr>
<tr>
<td><strong>🔌 API Endpoints</strong></td>
<td>API reference for integrations</td>
<td><a href="reference/api-endpoints.md">API Endpoints</a></td>
</tr>
<tr>
<td><strong>💱 Multi-Currency</strong></td>
<td>Support for 33 currencies with exchange rates</td>
<td><a href="reference/multi-currency.md">Multi-Currency</a></td>
</tr>
<tr>
<td><strong>📖 Glossary</strong></td>
<td>Definitions of key terms and concepts</td>
<td><a href="reference/glossary.md">Glossary</a></td>
</tr>
</tbody>
</table>

---

## Billing & Plans

RewardsPro offers flexible pricing based on your needs:

| Plan | Orders/Month | Features |
|------|--------------|----------|
| **Free** | Up to 100 | Basic features |
| **Starter** | Up to 500 | All core features |
| **Growth** | Up to 2,000 | Advanced features |
| **Enterprise** | Unlimited | Priority support |

📖 [View Pricing & Plans](billing/plans.md)

---

## Resources

<table data-view="cards">
<thead><tr><th></th><th></th></tr></thead>
<tbody>
<tr>
<td><strong>📝 Changelog</strong></td>
<td>Recent updates and improvements</td>
</tr>
<tr>
<td><strong>🗺️ Roadmap</strong></td>
<td>Upcoming features and timeline</td>
</tr>
<tr>
<td><strong>❓ FAQ</strong></td>
<td>Frequently asked questions</td>
</tr>
<tr>
<td><strong>💬 Support</strong></td>
<td>Contact us at support@rewardspro.io</td>
</tr>
</tbody>
</table>

---

## Need Help?

- **In-App Assistant**: Click "Ask me anything" in any RewardsPro page
- **Email**: support@rewardspro.io
- **Documentation**: You're here! Browse the sidebar for detailed guides

---

<p align="center">
<strong>Ready to boost customer loyalty?</strong><br>
<a href="getting-started/installation.md">Get Started →</a>
</p>
