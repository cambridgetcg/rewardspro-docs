---
icon: book-open
description: Technical documentation for developers and advanced users
---

# Reference

In-depth technical documentation covering how RewardsPro works under the hood, data structures, and integrations.

## Quick Links

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
<td><strong>Glossary</strong></td>
<td>Complete definitions of all terms</td>
<td><a href="glossary.md">glossary.md</a></td>
</tr>
<tr>
<td><strong>Data Models</strong></td>
<td>Technical data structure reference</td>
<td><a href="data-models.md">data-models.md</a></td>
</tr>
<tr>
<td><strong>Cashback Logic</strong></td>
<td>How cashback amounts are calculated</td>
<td><a href="cashback-logic.md">cashback-logic.md</a></td>
</tr>
<tr>
<td><strong>Webhooks</strong></td>
<td>Event notifications and processing</td>
<td><a href="webhooks.md">webhooks.md</a></td>
</tr>
<tr>
<td><strong>Evaluation Periods</strong></td>
<td>Annual vs Lifetime tier calculations</td>
<td><a href="evaluation-periods.md">evaluation-periods.md</a></td>
</tr>
<tr>
<td><strong>Multi-Currency</strong></td>
<td>32 supported currencies and exchange rates</td>
<td><a href="multi-currency.md">multi-currency.md</a></td>
</tr>
</tbody>
</table>

---

## Technical Reference

### Glossary
Complete definitions of all terms used in RewardsPro:
- Tier types and changes
- Ledger entry types
- Subscription statuses
- All enums and values

### Data Models
Detailed breakdown of all data structures:
- Customer, Tier, Order models
- Store credit ledger system
- Subscription and product models
- Field types and relationships

### Cashback Logic
Detailed breakdown of cashback calculation:
- Formula and components
- What's included/excluded
- Rounding rules and edge cases
- Multi-currency handling

### Evaluation Periods
Understanding tier qualification calculation:
- **Annual evaluation**: Rolling 12-month spending
- **Lifetime evaluation**: All-time cumulative spending
- Best practices for choosing the right approach

---

## Integration

### API Endpoints
Available endpoints for custom integrations:
- Widget membership API
- Localization endpoints
- Health check

### Webhooks
Event-driven notifications (14 webhook types):
- Order processing events
- Customer lifecycle
- Subscription changes
- Compliance (GDPR)

---

## Multi-Currency

### 32 Supported Currencies
How RewardsPro handles different currencies:
- Exchange rate management
- Display formatting options
- Conversion examples

---

{% hint style="info" %}
**Developer?** Start with [Data Models](data-models.md) for the technical structure, then review [Webhooks](webhooks.md) for integration details.
{% endhint %}
