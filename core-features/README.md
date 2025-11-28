---
icon: cube
description: Essential features for managing your loyalty program
---

# Core Features

RewardsPro provides a complete set of tools to run your loyalty program. This section covers the day-to-day features you'll use to manage tiers, customers, orders, and store credit.

## Feature Overview

<table data-view="cards">
<thead>
<tr>
<th></th>
<th></th>
<th data-hidden data-card-target data-type="content-ref"></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Membership Tiers</strong></td>
<td>Create and manage loyalty tier structure</td>
<td><a href="membership-tiers/create.md">membership-tiers/create.md</a></td>
</tr>
<tr>
<td><strong>Customer Management</strong></td>
<td>View profiles, assign tiers, manage credit</td>
<td><a href="customers-management/customers-page.md">customers-management/customers-page.md</a></td>
</tr>
<tr>
<td><strong>Orders & Cashback</strong></td>
<td>Track orders and cashback processing</td>
<td><a href="orders-and-cashback/orders-page.md">orders-and-cashback/orders-page.md</a></td>
</tr>
<tr>
<td><strong>Store Credit</strong></td>
<td>Issue, track, and manage balances</td>
<td><a href="store-credit/access-store-credits.md">store-credit/access-store-credits.md</a></td>
</tr>
</tbody>
</table>

---

## How It All Works Together

```
Customer places order
        ↓
Order webhook received (instant)
        ↓
Customer's tier identified
        ↓
Cashback calculated: Order Amount × Tier Rate
        ↓
Store credit added to customer balance
        ↓
Ledger entry created (audit trail)
        ↓
Tier progress updated
```

---

## Quick Reference

### Membership Tiers

| Guide | What You'll Learn |
|-------|-------------------|
| [Creating Tiers](membership-tiers/create.md) | Set up tier name, threshold, cashback rate |
| [Editing Tiers](membership-tiers/edit.md) | Modify existing tier settings |
| [Deleting Tiers](membership-tiers/delete.md) | Safely remove unused tiers |
| [Best Practices](membership-tiers/best-practice.md) | Proven tier structures |
| [Mistakes to Avoid](membership-tiers/mistake.md) | Common pitfalls |

### Customer Management

| Guide | What You'll Learn |
|-------|-------------------|
| [Customers Page](customers-management/customers-page.md) | Navigate the customer list |
| [Customer Details](customers-management/customer-details.md) | View full customer profile |
| [Manual Tier Assignment](customers-management/manually-assign-tiers.md) | Override automatic tiers |
| [Edit Store Credit](customers-management/manually-edit-store-credits.md) | Add or deduct credit |

### Orders & Cashback

| Guide | What You'll Learn |
|-------|-------------------|
| [Orders Page](orders-and-cashback/orders-page.md) | View and manage orders |
| [Cashback Processing](orders-and-cashback/cashback-processing.md) | How orders are processed |
| [Calculation Rules](orders-and-cashback/cashback-calculation-rules.md) | Understand the formula |

### Store Credit

| Guide | What You'll Learn |
|-------|-------------------|
| [Access Store Credits](store-credit/access-store-credits.md) | How customers see balance |
| [Refund to Credit](store-credit/refund-to-credit.md) | Handle refunds as credit |
| [Expiration Dates](store-credit/expiration-dates.md) | Configure credit expiry |

---

## Key Data Points

### Customer Profile Includes

- **Contact Info**: Name, email, Shopify ID
- **Financial**: Store credit balance, total spent, annual spent
- **Tier**: Current tier, cashback rate, progress to next tier
- **Activity**: Order count, last order date, cashback earned

### Order Tracking Includes

- **Order Details**: Number, date, products, totals
- **Financial**: Subtotal, discounts, shipping, tax, refunds
- **Cashback**: Tier at order time, rate applied, amount earned
- **Status**: Payment status, fulfillment status, processing status

### Ledger Entry Types

| Type | Description |
|------|-------------|
| `CASHBACK_EARNED` | Cashback from paid orders |
| `MANUAL_ADJUSTMENT` | Admin adds or deducts credit |
| `REFUND_CREDIT` | Credit issued for refund |
| `REFUND_CLAWBACK` | Cashback reversed on refund |
| `ORDER_PAYMENT` | Credit used at checkout |

---

## Common Tasks

### "How do I..."

| Task | Guide |
|------|-------|
| Create my first tier | [Creating Tiers](membership-tiers/create.md) |
| Find a specific customer | [Customers Page](customers-management/customers-page.md) |
| See why cashback was X amount | [Calculation Rules](orders-and-cashback/cashback-calculation-rules.md) |
| Give a customer bonus credit | [Edit Store Credit](customers-management/manually-edit-store-credits.md) |
| Promote a customer to VIP tier | [Manual Tier Assignment](customers-management/manually-assign-tiers.md) |
| Check a customer's order history | [Customer Details](customers-management/customer-details.md) |

---

## Next Steps

- **New to RewardsPro?** Start with [Creating Membership Tiers](membership-tiers/create.md)
- **Need to configure settings?** See [Configuration](../configuration/)
- **Want advanced features?** Check [Advanced Features](../advanced-features/)

